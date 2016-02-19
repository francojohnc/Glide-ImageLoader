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

