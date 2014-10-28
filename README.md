vtp3-contacts
=============

"who do I call?"

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
