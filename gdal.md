# GDAL

## Opening a file in a Zip archive

You have to prepend the file path with `/vsizip/` and append it with the path to the shapefile in the archive.

For example, consider this file:


```
zipinfo data/source/parcels/ParcelInfo.zip
```

with these contents:

```
Archive:  data/source/parcels/ParcelInfo.zip
Zip file size: 49839839 bytes, number of entries: 32
-rw-a--     2.0 fat        5 t- stor 21-May-18 07:17 Mkt_Areas.cpg
-rw-a--     2.0 fat     2224 t- defN 21-May-18 07:17 Mkt_Areas.dbf
-rw-a--     2.0 fat      473 t- defN 21-May-18 07:17 Mkt_Areas.prj
-rw-a--     2.0 fat      268 b- defN 21-May-18 07:17 Mkt_Areas.sbn
-rw-a--     2.0 fat      132 b- defN 21-May-18 07:17 Mkt_Areas.sbx
-rw-a--     2.0 fat    21300 b- defN 21-May-18 07:17 Mkt_Areas.shp
-rw-a--     2.0 fat   123010 t- defN 21-May-18 07:17 Mkt_Areas.shp.xml
-rw-a--     2.0 fat      212 b- defN 21-May-18 07:17 Mkt_Areas.shx
-rw-a--     2.0 fat        5 t- stor 21-May-18 07:16 PageIndex.cpg
-rw-a--     2.0 fat   865179 t- defN 21-May-18 07:16 PageIndex.dbf
-rw-a--     2.0 fat      473 t- defN 21-May-18 07:16 PageIndex.prj
-rw-a--     2.0 fat    35980 b- defN 21-May-18 07:16 PageIndex.sbn
-rw-a--     2.0 fat     2100 b- defN 21-May-18 07:16 PageIndex.sbx
-rw-a--     2.0 fat  4638152 b- defN 21-May-18 07:16 PageIndex.shp
-rw-a--     2.0 fat   125979 t- defN 21-May-18 07:16 PageIndex.shp.xml
-rw-a--     2.0 fat    30044 b- defN 21-May-18 07:16 PageIndex.shx
-rw-a--     2.0 fat        5 t- stor 21-May-18 07:21 ParcelBoundary.cpg
-rw-a--     2.0 fat 25013106 t- defN 21-May-18 07:21 ParcelBoundary.dbf
-rw-a--     2.0 fat      473 t- defN 21-May-18 07:20 ParcelBoundary.prj
-rw-a--     2.0 fat  2321372 b- defN 21-May-18 07:21 ParcelBoundary.sbn
-rw-a--     2.0 fat    47212 b- defN 21-May-18 07:21 ParcelBoundary.sbx
-rw-a--     2.0 fat 121744916 b- defN 21-May-18 07:21 ParcelBoundary.shp
-rw-a--     2.0 fat    24832 t- defN 21-May-18 07:21 ParcelBoundary.shp.xml
-rw-a--     2.0 fat  2021348 b- defN 21-May-18 07:21 ParcelBoundary.shx
-rw-a--     2.0 fat        5 t- stor 21-May-18 07:16 SubPoly.cpg
-rw-a--     2.0 fat   875490 t- defN 21-May-18 07:16 SubPoly.dbf
-rw-a--     2.0 fat      473 t- defN 21-May-18 07:16 SubPoly.prj
-rw-a--     2.0 fat    18604 b- defN 21-May-18 07:16 SubPoly.sbn
-rw-a--     2.0 fat      772 b- defN 21-May-18 07:16 SubPoly.sbx
-rw-a--     2.0 fat  3890308 b- defN 21-May-18 07:16 SubPoly.shp
-rw-a--     2.0 fat    14687 t- defN 21-May-18 07:16 SubPoly.shp.xml
-rw-a--     2.0 fat    15972 b- defN 21-May-18 07:16 SubPoly.shx
32 files, 161835111 bytes uncompressed, 49836473 bytes compressed:  69.2%
```

If I want to use GDAL tools like `ogrinfo` on the `ParcelBoundary.shp` shapefile in the archive, I have to specify it's path as `/vsizip/data/source/parcels/ParcelInfo.zip/ParcelBoundary.shp`, e.g.

```
ogrinfo -so /vsizip/data/source/parcels/ParcelInfo.zip/ParcelBoundary.shp ParcelBoundary
```

Source: [GDAL Virtual File Systems (compressed, network hosted, etc…): /vsimem, /vsizip, /vsitar, /vsicurl, …](https://gdal.org/user/virtual_file_systems.html) (GDAL documentation)
