# Open Refine Template Lane College Scrapbook


## Template

#### Prefix

```
<?xml version="1.0" encoding="UTF-8"?>
<modsCollection xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
```
####Body

```
<mods>
<identifier type="local">{{cells["Identifier"].value}}</identifier>

{{if(isBlank(cells['title'].value), '', '<titleInfo><title>' + cells["title"].value + '</title></titleInfo>')}} 

{{if(isBlank(cells['date_approximate'].value), '', '<originInfo><dateCreated qualifier="approximate">' + cells['date_approximate'].value + '</dateCreated><dateCreated encoding="edtf" qualifier="approximate">' + cells['date_approximate'].value + '</dateCreated>' + '</originInfo>')}}

{{if(isBlank(cells['abstract'].value), '', '<abstract>' + cells["abstract"].value + '</abstract>')}}

{{if(isBlank(cells['Creator'].value), '', '<name><namePart>' + cells['Creator'].value + '</namePart><role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/cre">Creator</roleTerm></role></name>')}}

<physicalDescription><form authority="aat" valueURI="{{cells['form_URI'].value}}">{{cells['form'].value}}</form>
{{if(isBlank(cells['Extent'].value), '', '<extent>' + cells["Extent"].value + '</extent>')}}
</physicalDescription>

{{if(isBlank(cells['subject'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject_URI'].value + '"><topic>' + cells['subject'].value + '</topic></subject>')}}

{{if(isBlank(cells['subject2'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject2_URI'].value + '"><topic>' + cells['subject2'].value + '</topic></subject>')}}

<subject authority="naf" valueURI="{{cells['subject_geo_URI'].value}}"><name><namePart>{{cells['subject_geo'].value}}</namePart></name></subject>

<typeOfResource>{{cells['typeOfResource'].value}}</typeOfResource>
{{if(isBlank(cells['typeOfResource2'].value), '', '<typeOfResource>' + cells['typeOfResource2'].value + '</typeOfResource>')}}

{{if(isBlank(cells['Language'].value), '', '<language><languageTerm type="text" authority="iso639-2b">' + cells['Language'].value + '</languageTerm></language>')}}
{{if(isBlank(cells['Language 2'].value), '', '<language><languageTerm type="text" authority="iso639-2b">' + cells['Language 2'].value + '</languageTerm></language>')}}

<relatedItem displayLabel="Project" type="host"><titleInfo><title>Lane College Scrapbook</title></titleInfo></relatedItem>

<relatedItem displayLabel="Collection" type="host">
<titleInfo>
<title>Lane College Scrapbook</title>
</titleInfo>
<identifier>MS-3976</identifier>
</relatedItem>

<location><physicalLocation valueURI="http://id.loc.gov/authorities/names/no2014027633">University of Tennessee, Knoxville. Special Collections</physicalLocation></location>

<recordInfo><recordContentSource valueURI="http://id.loc.gov/authorities/names/n87808088">University of Tennessee, Knoxville. Libraries</recordContentSource></recordInfo>

<accessCondition type="use and reproduction" xlink:href="{{cells['rights_URI'].value}}">{{cells['rights'].value}}</accessCondition>
</mods>

```

#### Suffix

```
</modsCollection>
```