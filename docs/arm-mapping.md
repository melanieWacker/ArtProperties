# Art Properties to ARM Mapping
=====================================================
# DRAFT

*Note*: Art Properties column headings do NOT reflect the original element name. These have been adjusted to support easier data mapping from the spreadsheet.

*To-Do*: Change URIs to RWOs, SHACL for Application Profile

<a>Mapping</a>
----------------------
| CUL ArtProperties      | ARM conversion        | Spreadsheet Conversion Note
|:-------------|:-------------|:-------------|
|Work_URI   |rdf:type [a bf:Work] AND <WorkIURI> bf:hasInstance <InstanceURI>   |Not contained in original data. Placeholder URIs generated to support BIBFRAME data model.
|Work_Title   |arm_hasPreferredTitle [a bf:Title ; mainTitle “title value” ] .   |Original data included only 1 title. Values for copied into Instance Title and Item Title to support BF data model
|Work_Alternative_Title   | bf:title [a bf:Title ; mainTitle “title value” ] .  |   
|creator   |arm:hasActivity [a arm:Activity ; bf:agent [a bf:Agent ; rdf:value “value” ] ]  . | 
|creator_URI   |arm:hasActivity [a arm:Activity ; bf:agent <URI> .   | 
|Qualifier   |arm:Activity ; armhasAttribution [a arm:Attribution ; bf:note [a bf:Note ; rdf:value “value” ] ].   | 
|Role   |arm:hasActivity ; rdf:type   | 
|Creator_Notes   |bf:agent [a bf:Agent ; bf:note [a bf:Note ; rdf:value “value” ] ] .   |Separated out from Notes-Public
|Instance_Corporate Creator   |arm:hasActivity [a arm:Activity ; bf:agent [a bf:Organization ; rdf:value “value” ] ] .   | 
|Instance_Corporate Creator Identifier   |arm:hasActivity [a arm:Activity ; bf:agent <URI> ] .   | 
|Instance_Corporate Qualifier   |arm:Activity ; armhasAttribution [a arm:Attribution ; bf:note [a bf:Note ; rdf:value “value” ] ].   | 
|Instance_Corporate Role   |arm:hasActivity ; rdf:type   | 
|Date   |arm:hasActivity [a arm:Activity ; bf:originDate “value” ] .   | 
|Century   |arm:hasActivity [a arm:Activity ; bf:originDate “value” ] .   | 
|EDTF Date Range  |arm:hasActivity [a arm:Activity ; bf:originDate “value”^^edtf:edtf ] .   | Was in separate earliest and latest date columns in original data
|Creation Location Label   |arm:hasActivity [a arm:Activity ; arm:atLocation [a bf:Place ; rdf:value “value” ] .   |Original data includes hierarchy 
|Creation Location Getty Identifier   |arm:hasActivity [a arm:Activity ; arm:atLocation <URI> ] .   |Reconciled by metadata staff
|Country   |arm:hasActivity [a arm:Activity ; arm:atLocation [a bf:Place ; rdf:value “value” ] .   | 
|Country Identifier   |arm:hasActivity [a arm:Activity ; arm:atLocation <URI> ] .   |Reconciled by metadata staff
|Classification Primary Getty Label   |bf:genreForm [a bf:GenreForm ; rdf:value “value” ] .   | 
|Classification Primary Getty Identifier   |bf:genreForm <URI> .   |Reconciled by metadata staff 
|Classification Secondary Getty Label   |bf:genreForm [a bf:GenreForm ; rdf:value “value” ] .   | 
|Classification Secondary Getty Identifier   |bf:genreForm <URI> .   |Reconciled by metadata staff 
|Work Type Getty Label   |bf:genreForm [a bf:GenreForm ; rdf:value “value” ] .   | 
|Work Type Getty Identifier   |bf:genreForm <URI> .   | 
|Description   |bf:summary [a bf:Summary ; rdf:value ] .   | 
|Portrait Subject   |bf:subject [a bf:Person ; rdf:value “value” ] .   | 
|Portrait Subject Identifier   |bf:subject <URI>  .   | 
|Genre Type Getty Label   |bf:genreForm [a bf:GenreForm ; rdf:value “value” ] .   | 
|Genre Type Getty Identifier   |bf:genreForm <URI> .   | 
|Period   |arm:hasStylePeriod [a arm:StylePeriod ; rdf:value “value” ] .   |To-do: Needs reconciliation to aat
|Culture   |arm:hasStylePeriod [a arm:StylePeriod ; rdf:value “value” ] .   |To-do: Needs reconciliation to aat
|Instance_URI   |rdf:type [a bf:Instance] . AND <InstanceURI> bf:instanceOf <WorkURI> AND <Instance URI> bf:hasItem <Item URI> |Not contained in original data. Placeholder URIs generated to support BIBFRAME data model. 
|Instance_Title   |arm_hasPreferredTitle [a bf:Title ; mainTitle “title value” ] .   |Original data included only 1 title. Values for copied into Instance Title and Item Title to support BF data model 
|Medium/Support   |arm:hasMaterial [a crm:57_Material ;  rdf:value “value” ] .   | 
|Dimensions   |measure:hasMeasurementGroup [a measure:MeasurementGroup ; hasMeasurement [a measure:Measurement; rdf:value “value” ] .   | To-do: Separate out into components to take advantage of full measurement model
|Copyright Information   |bf:copyrightRegistration [a bf:CopyrightRegistration ; rdf:value “value” ] .   | 
|Item_URI   | rdf:type [a bf:Item ] . AND <Item URI> bf:itemOf <Instance URI> . |Not contained in original data. Placeholder URIs generated to support BIBFRAME data model.
|Item_Title   |arm_hasPreferredTitle [a bf:Title ; mainTitle “title value” ] .   |Original data included only 1 title. Values for copied into Instance Title and Item Title to support BF data model.
|Accession Number   | bf:identifier [a arm:Accession Number rdf:value “value” ] . AND ch:hasCustodialHistory [a ch:CustodialHistory ; bf:hasPart [a ch:CustodialEvent ; ch:accessions [a arm:AccessionNumber ; rdf:value “value] ] ] . |
| Inscription/Signature  | arm:markedBy [a arm:Inscription ; rdf:value “value” ] .  | 
| Marks  | arm:markedBy [a arm:Watermark ; rdf:value “value” ] .  | Separated out from Notes-Public
| Item_notes  | bf:Item ; bf:note [a bf:Note ; rdf:value “value”] .  | Separated out from Notes-Public
| Exhibitions  | arm:hasExhibition [a arm:Exhibition ; bf:partOf [a schema:ExhibitionEvent ; bf:note [a bf:Note ; rdf:value ] ] .  | 
| Provenance  | ch:hasCustodialHistory [a ch:CustodialHistory ; bf:hasPart [a ch:CustodialEvent ; bf:note [a bf:Note ; rdf:value “value” ] ] ] .  | 
| Donor  |ch:CustodialHistory ; bf:hasPart [a ch:Donation ; arm:hasActivity [a ch:DonorActivity ; bf:agent [bf:Agent ; rdf:value “value” ] ] ] .   | 
|Donor Identifier   |## ch:CustodialHistory ; bf:hasPart [a ch:Donation ; arm:hasActivity [a ch:DonorActivity ; bf:agent <URI> ] ] .   | 
|Donor Qualifier   |## ch:Donation ; arm:hasActivity [a ch:DonorActivity ; bf:note [a bf:Note ; rdf:value “value” ] ] .   | 
|Credit Line  |## ch:DonorActivity ; bf:agent [a bf:Agent ; bf:note [a bf:Note ; rdf:value “value” ] ] .   | 
|Acquisition Date   |## ch:CustodialEvent ; arm:hasActivity [a ch:AcquisitionActivity ; bf:date “value” ] .   | 
|Condition Rank   |arm:hasActivity [a arm:ConditionAssesmentActivity; frapo:hasOutput [a ConditionAssessment ; arm:describes [a arm:PhysicalCondition ; rdf:value “value” ] ] ].  AND arm:hasPhyicalCondition [a arm:PhysicalCondition ; rdf:value "value" ] . | 
|Condition Description   |## arm:physicalCondition [a arm:PhysicalCondition ; rdf:value “value” ] .   | 
|Condition Date   |arm:hasActivity [a arm:ConditionAssesmentActivity; bf:date “value” ] .   |    
|Conservation   |arm:hasActivity [a arm:ConservatorActivity ; bf:note [a bf:Note ; rdf:value “value” ] .   | 
|Repository   |arm:hasActivity [a arm:RepositoryActivity ; bf:agent [a bf:Organization ; rdf:value “value” ] .   | Added. Not in original data
|Repository_Identifier   |arm:hasActivity [a arm:RepositoryActivity ; bf:agent <URI> .   |Added. Not in original data
|Campus Location   |arm:hasActivity [a arm:RepositoryActivity ; arm:atLocation [a bf:Place ; rdf:value “value” ] .
|Building Location  |arm:hasActivity [a arm:RepositoryActivity ; arm:atLocation [a bf:Place ; rdf:value “value” ] .
