# Glide-ImageLoader
![alt tag](https://github.com/francojohnc/Glide-ImageLoader/blob/master/Screenshot_2016-02-19-00-29-07.png)

if you have existing android application, and use image loader function from any kind of liraries such as volley piccaso etc.
then if you wan't to change the library you already use to better library, its to hard, all codes you call from existing library you need to change one by one.
this is the better way to do that, 

#####syntax

ImageLoader imageLoader = new ImageLoader(this);
 imageLoader.setImageUrl("http://inthecheesefactory.com/uploads/source/glidepicasso/cover.jpg");
 imageLoader.setImageView(imageView);
 imageLoader.setProgressBar(pb);
 imageLoader.load();
