# gpx_analyzer
Reads .gpx files and presents an analysis of the content. Optimized for ski data from Maprika.

# Subfunction "ReadGPX"
Imports gpx file from Maprika and populates arrays:
input file.gpx
return latitude,longitude, elevation, time

# Subfunction "ToMetric"
Convert latitue and longitude to meters
input latitude, longitude
return latMet, longMet

# Subfunction "SetZero"
Recalculate arrays to have lowest value 0
input latMet, longmet
return latMet, longmet

# Subfunction "Filter"
Some kind of digital low pass filter to remove single outliers
input latMet, longmet, elevation
return latMetFlt, longmetFlt, elevationFlt

# Subfunction "FindSlopes"
Split arrays into one piece per slope, defined as a continous run with negative elevation change
inout latMetFlt, longmetFlt, elevationFlt, time
return latMetFlt1, latMetFlt2 etc.

# Subfunction "FindLifts"
Split arrays into one piece per lift, defined as a continous run with positive elevation change
inout latMetFlt, longmetFlt, elevationFlt, time
return latMetFlt1b, latMetFlt2b etc.

# Subfunction "PlotRun"
Plot of latitue, longitude and elevation
