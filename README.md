# gpx2shp_lv03

## Purpose
gpx2shp_lv03 is an Avenue script used within ArcView GIS to translate GPX files into shapefiles in Swiss coordinates LV03. In addition, various information is calculated, such as the time duration, the ascent/descent and the average speed.

## Background
ESRI's ArcView GIS is a rather old (1995 – 2002), but for many purposes still useful GIS application. Due to its age it's very fast on modern hardware and has full support for the still widely used vector data format shape (SHP).

Avenue is ArcView's built-in object oriented scripting language. "By using Avenue, you can customize the program and further extend its power", describes Amir H. Razavi the language's purpose in his 1999 book \[1\].

The GPS Exchange Format (GPX) was first released in 2002, about the same time the last ArcView release was published. ArcView has never supported this format, but since it's a plain text format it's quite easy to import it using a few Avenue scripts.

GPX files store waypoints in geographic coordinates (WGS 1984). To be able to use the point data easily together with Swiss maps, gpx2shp_lv03 transforms the coordinates into projected Swiss coordinates LV03 using the formula described in \[2\]

## System requirements
An ArcView GIS 3.x installation is required.

## Installation
Download the repository into your desired directory:

```
cd <directory>
git clone https://github.com/ABoehlen/gpx2shp_lv03
cd gpx2shp_lv03
```

* Open ArcView GIS with a new empty project.
* Create 3 new scripts and load the contents of the 3 AVE files into them. Their name must match the script name (without the extension .ave).
* Compile the scripts
* Create a new "Button" for the type "View" and connect it to the script "gpx2shp_lv03"
* Create a new "View". You should now see your new button in the button list.
* Save the project for further use.

## Usage

Make sure that the GPX files you want to convert hava a newline after each element. If you are not sure how this should look, take a look at the attached test file `test.gpx`.

If only one GPX file is to be converted, simply click on your new button, choose the GPX file in the first dialogue and the name and storage location for the shapefile in the second dialogue. Once the conversion is complete, you can add the new shapefile using Add Theme.

To convert multiple GPX files, hold down the Shift key while clicking on the new button. Then select the directory where the GPX tracks are stored, click OK and set the storage directory for the new shapefiles and press OK again. All GPX files in the specified directory will then be converted.

## License

This project is licensed under the MIT License - see the LICENSE file for details

## Literature
\[1\] Razavi, Amir H.: ArcView GIS Developer's Guide, 1999

\[2\] Bundesamt für Landestopografie swisstopo: Formeln und Konstanten für die Berechnung der Schweizerischen schiefachsigen Zylinderprojektion und der Transformation zwischen Koordinatensystemen, 2008, pp. 11 (in German): https://cms.geo.admin.ch/www.swisstopo.admin.ch/archives/cms2007/internet/swisstopo/de/home/topics/survey/sys/refsys/switzerland.parsysrelated1.24280.downloadList.42086.DownloadFile.tmp/refsysd.www.pdf
