# Debugging CV Algorithms for custom image types in Visual Studio

Let's say you have a custom image type, e.g. Image<unsigned short,4> for a 4-channel unsigned short image.
When programming in visual studio, you really want to be able to see your image to tell if your algorithms are working. To do that you want to install [Image Watch from Microsoft Research] (http://research.microsoft.com/en-us/um/redmond/groups/ivm/imagewatchhelp/imagewatchhelp.htm). You also want a custom natvis file, which is described in the linked document.

I installed Image Watch in Visual Studio using the `Tools\\Extension and Updates` menu.

This project shows a simple natvis file which does the job for a custom image. I dropped it in C:\Users\samson\Documents\Visual Studio 2013\Visualizers . Every time you start a debugging session that file is reloaded.

My image for this project was: `template <class T, unsigned int Cdepth> class Image` . IT has member variables: `width_, height_ and data_`

You can see in the file how to deal with templates, and what variables need to be defined. The alternate names don't seem to do anything, but I left them in.

# Some Notes
`unique_ptr<Image>` myvar; does not work automatically. But, you can go into the Watch and look at myvar._Myptr
