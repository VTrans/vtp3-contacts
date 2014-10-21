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