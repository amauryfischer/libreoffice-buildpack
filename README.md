# Fully working LibreOffice buildpack 🎉

Shamefully simple, and utilising an official AppImage copy of LibreOffice with its dependencies directly from the vendor... a working buildpack for LibreOffice 6.x (others possibly supported via a config file) on the heroku-18 stack (others possibly supported but you may be asking for trouble if you try), after a lot of trial & error.

Made with love (and out of frustration with incompatibility between LibreOffice 6 and bare-bone heroku-18) by [@geomic](https://github.com/geomic), and with enhancements contributed in kind by [@vesatoivonen](https://github.com/vesatoivonen).

Particularly useful if you use the `libreconv` gem for document conversion to PDF in Ruby on Rails applications, and results in a manageable slug size (which will likely keep you under heroku's soft limit as an added bonus) when compared with other options.

If you need the additional capabilities of headless LibreOffice 6, particularly for closer conversion of Office files to accurate PDFs, this buildpack is for you.

Add a `.buildpacks` file to your project with this buildpack and the one(s) you wish to use

```
https://github.com/Soulou/libreoffice-buildpack
https://github.com/Scalingo/<language>-buildpack
```

Optionally, create a `LibreOfficeAppImage` file in your application repository to change the installed version to something other than the latest `fresh`.
The file should contain only the full URL of a LibreOffice AppImage, from the [official links found here](https://libreoffice.soluzioniopen.com/).
For example the latest `still` can be installed with:
```
https://libreoffice.soluzioniopen.com/stable/still/LibreOffice-still.basic-x86_64.AppImage
```

Redeploy your project after committing the above, et voilà...!
