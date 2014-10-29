vtp3-contacts
=============
###[Contacts Map](http://vtrans.maps.arcgis.com/apps/webappviewer/index.html?id=22c56fb498d147319f17860c5ed00796)
#User Story
- "who do I call?"
- "?"


###Contact Map Development

1. Created View of District and Construction Contacts, Contact_Const comes from warehouse  and is refEmployeeInfo joined to refConstructionRegions, 
Contact_Dist comes from refDistrictTable.
2. Imported Views into GDB_ASSETS to be joined with GDB_Assets.ASSETS_ADMIN.Boundary_Construction_Regions, GDB_Gen.VTRANS_ADMIN.Boundary_OPSDistrictTowns and GDB_Gen.VTRANS_ADMIN.MATS_District_Mileages.
3. Export joined features from GDB-GEN to GDB_Assets in order to edit.
4. Joined exported layers GDB_Assets.ASSETS_ADMIN.MATS_Dist_Mile_Contacts, GDB_Assets.ASSETS_ADMIN.Boundary_ConstReg_Contacts, GDB_Assets.ASSETS_ADMIN.Boundary_OPSDistrictTowns_Contacts with contacts views created above.
5. Appended Features to include contact information and deleted all unnecessary fields.
6. Romoved background and outline symbology to all layers in order to be invisable in AGO map.
7. Set Pop-up title to display layer name and major boundary for that layer.
8. Configured all pop-ups to only display contact information.
9. manually entered email adresses for GDB_Assets.ASSETS_ADMIN.MATS_Dist_Mile_Contacts and GDB_Assets.ASSETS_ADMIN.Boundary_OPSDistrictTowns_Contacts layers.
10. Re-published ContactMap Link above with minor changes to Pop-up Titles and display.
11. Develop Web Application Complete
12. [Here it is so far, just click around](http://vtrans.maps.arcgis.com/apps/webappviewer/index.html?id=22c56fb498d147319f17860c5ed00796)
13. Added States/Provinces Boundary backgorund layer for popping VT look.
14. Set filter on States/Provinces Boundary to ("postal" is not "VT") and Fill Transperency to 70%.

###Geoprocessing Results
1. Researched multiple ArcMap geoprocessing tools in efforts of combining GDB_Assets.ASSETS_ADMIN.Boundary_OPSDistrictTowns_Contacts, GDB_Assets.ASSETS_ADMIN.Boundary_ConstReg_Contacts and GDB_Assets.ASSETS_ADMIN.MATS_Dist_Mile_Contacts into one "Contacts" Layer.
2. Tools and methods explored were as follows:
	- (Successful) Tool Used (Union), Input features were Boundary_OPSDistrictTowns_Contacts (polygon) and Boundary_ConstReg_Contacts (polygon). Allowes both existing polygon data to be combined into one feature (all attributes were kept). 
	- (Successful) Tool Used (Buffer), Input feature was MATS_Dist_Mile_Contacts (line) and one meter offset was assigned. Select buffer segments created and export out as own featureclass.
	- (Successful) Tool Used (Advanced Editing Tool, Construct Polygon), Began editing on MATS_Dist_Mile_Cont_Poly (line) and used Boundary_OPSDistrictTowns_Contacts (polygon) as template to create polygon of MATS_Dist_Mile_Cont_Poly then export to featureclass.
	- (Failure) Tool Used (Merge), Input Datasets were Boundary_OPSDistrictTowns_Contacts, Boundary_ConstReg_Contacts and MATS_Dist_Mile_Cont_Polygon. Merged fine but results were unsatisfactory. Creates Individual features between any enclosed route segment. 
	- (Failure) Tool Used (Union), Same results as above.
	- (Failure) Tool Used (Spatial Join), Same results as above.   
	- (Successful) Only logical outcome for creating a "polyline" from Route Feature was to export the results from the Spatial Join and save the MATS_Dist_Mile_Cont_Polygon as its own feature with all contact info associated with each segment. This resulted in a rather odd segmentation of the feature but overall was succesful.

3. I believe there are too many variables within the data in order to perform a proper spatial merge without heavily modifying the attribute table to account for the number of boundary intersect conflicts. i.e  "MATS_Dist_Mile_Contacts" Route Features are asigned to individual districts but crosses Regional and District Boundaries.
