# what is [Glide-ImageLoader](http://inthecheesefactory.com/blog/get-to-know-glide-recommended-by-google/en)
![alt tag](https://github.com/francojohnc/Glide-ImageLoader/blob/master/Screenshot_2016-02-19-00-29-07.png)

if you have existing android application, and use image loader function from any kind of liraries such as volley piccaso etc.
then if you wan't to change the library you already use to better library, its to hard, all codes you call from existing library you need to change one by one.
this is the better way to do that, and this is the stucture i use for my many projects.
if you wan't to improve this structure fill free to contribute

##syntax

#####Load Image
 ImageLoader imageLoader = new ImageLoader(this);
 imageLoader.setImageUrl("http://inthecheesefactory.com/uploads/source/glidepicasso/cover.jpg");
 imageLoader.setImageView(imageView);
 imageLoader.load();
 
#####Load Image with ProgressBar
 ImageLoader imageLoader = new ImageLoader(this);
 imageLoader.setImageUrl("http://inthecheesefactory.com/uploads/source/glidepicasso/cover.jpg");
 imageLoader.setProgressBar(pb);
 imageLoader.setImageView(imageView);
 imageLoader.load();
 
#####Load Image with Resize
 ImageLoader imageLoader = new ImageLoader(this);
 imageLoader.setImageUrl("http://inthecheesefactory.com/uploads/source/glidepicasso/cover.jpg");
 imageLoader.setImageView(imageView);
 imageLoader.setSize(800,800);
 imageLoader.load();
 
#####Load Image with Callback Listener
 imageLoader.setListener(your listener);
 
## and this is the core of the structure from ImageLoader class you can change this line of codes dynamically
 
 ```
   public void load() {
        this.ownListener = this;
        if (imageView != null && progressBar != null) {
            imageView.setVisibility(View.GONE);
            progressBar.setVisibility(View.VISIBLE);
        }
        //you can change this dynamically
        //http://inthecheesefactory.com/blog/get-to-know-glide-recommended-by-google/en
        Glide.with(context)
                .load("http://inthecheesefactory.com/uploads/source/glidepicasso/cover.jpg")
                .into(imageView);
        Glide.with(context)
                .load(imageUrl)
                .listener(new RequestListener<String, GlideDrawable>() {
                    @Override
                    public boolean onException(Exception e, String model, Target<GlideDrawable> target, boolean isFirstResource) {
                        ownListener.onError();
                        return false;
                    }
                    @Override
                    public boolean onResourceReady(GlideDrawable resource, String model, Target<GlideDrawable> target, boolean isFromMemoryCache, boolean isFirstResource) {
                        ownListener.onSuccess();
                        return false;
                    }
                }).centerCrop().override(targetWidth, targetHeight).into(imageView);
    }
```
