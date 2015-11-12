# Debugging CV Algorithms for custom image types in Visual Studio

Let's say you have a custom image type, e.g. Image<unsigned short,4> for a 4-channel unsigned short image.
When programming in visual studio, you really want to be able to see your image to tell if your algorithms are working. To do that you want to use Image Watch from Microsoft Research (http://research.microsoft.com/en-us/um/redmond/groups/ivm/imagewatchhelp/imagewatchhelp.htm ). You also want a custom natvis file.

This project shows a simple natvis file which does the job. I dropped it in C:\Users\samson\Documents\Visual Studio 2013\Visualizers . Every time you start a debugging session that file is reloaded.

My image for this project was: template <class T, unsigned int Cdepth> class Image

You can see in the file how to deal with 

# Some Notes
unique_ptr<ImageType> myvar; does not work. But, you can go into the Watch and look at myvar._Myptr
