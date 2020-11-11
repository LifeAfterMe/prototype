# prototype READ.ME
[Live Prototype](https://lifeafterme.github.io/prototype/)

## About the model
Use this model to explore content structures and interactions.  The [Live Prototype](https://lifeafterme.github.io/prototype/) is generated using Jekyll and custom content and templates (structure and logic). The presentation is minimal to help focus on the application structure and identify UI patterns.

## Customization

### \_subjects collection
A collection of Subjects and their credentials/data.  

Use a separate markdown (.md) file for each individual wallet. Jekyll will add the subject to the wallet.  Vision is that each wallet can be modelled as YAML data following some schema or schemas.

### \_holders collection
A collection of Holders and their data.

> placeholder for details about holders....

### \_data
JSON files for declaring data to be used in content generation.  Vision is this would include instructions and credential schemas.

```
  \
    _data\
      afterlife-rules\  
        us\  /* national rules by id/type and state. uses 2 letter country code */
          - passport.yaml  /* rules for US passports */
          - ssn.yaml  /* rules for type social securit */
          ...
          \ca  /* state rules by id/type and city(county?).  Uses 2 letter state code */
             - driversLicense.yaml
             - vehicleRegistration.yaml
             - businessLicense.yaml
             - deed.yaml
             ...
             \{city name} /* rules by id/type */
                - marriageLicense.yaml
                - deathCertificate.yaml
        - {type}.yaml /* general rules by types  */
```

> Example object reference: __data.afterlife-rules.us.passport__

* [Rules schemas](rules-schemas.md)
* [Document schemas](document-schemas.md)



### templates
* /\_templates/subject.html.  For the view of subject and their credentials

### \_includes
template components
* __meta-head.html__ and __meta-end.html__  For HTML meta data and structure
* __global-header.html__ For product id and global navigation.
* __global-footer.html__ For product id and global legal and help info.


## How it works  
Model uses a static site generator called Jekyll.  

* Content and data:  [YAML](https://www.w3schools.io/file/yaml-cheatsheet-syntax/) and [Markdown](https://www.markdownguide.org/cheat-sheet/).  Markdown files consist of metadata in YAML frontmater and body content of markdown, html, and/or liquid tags.
* Templates use [Liquid](https://jekyllrb.com/docs/liquid/) templating language
* [Jekyll Docs](https://jekyllrb.com/docs/)
