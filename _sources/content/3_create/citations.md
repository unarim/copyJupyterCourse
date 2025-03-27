# Adding Citations and Bibliographies

To include citations in your course website, begin by creating a BibTeX file to store your references. Then, link it in the `_config.yml` file to ensure it's recognized. Once set up, you can easily add citations and generate a bibliography to enhance your course content.

## Create a Bibliography

Create a new file in your repository and save it with the `.bib` extension to create a BibTeX file. 

![Image of how to name the bibtex file](../../static/bib-file-name.jpg)

Then, add your references to the file and click on "Commit changes".

![Image of the newly created bibtex file with one example reference.](../../static/bib-file.png)


## Edit the Config File

Open the `_config.yml` file and specify your BibTeX file as the source for citations by adding the following lines under the "sphinx: config:" 
```
bibtex_bibfiles:
  - references.bib
``` 
Please ensure the correct indentation.

![Image of the config.yml file, in which the BibTeX file is included as described.](../../static/config_bibtex.png)

## Add a Citation
Now, you can include your citations into your text. Here is an example:

```
{cite}`munafo2017manifesto`
```

Result:
{cite}`munafo2017manifesto`

## Add a Bibliography 

To add a bibliography, you need to use the `{bibliography}` directive at the end of your page: 
````
```{bibliography}
```
````
At the end of this page, you will see an example bibliography.


## Next Section:
In the next section, you will learn how to integrate feedback questions.

----

**References**
```{bibliography} 
```

