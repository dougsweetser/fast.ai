# Getting imagesets with kaggle-cli (Unofficial client)

Install kaggle-cli and configure it

 https://github.com/floydwch/kaggle-cli
 
 http://wiki.fast.ai/index.php/Kaggle_CLI
 
 These instructions based largely off http://forums.fast.ai/t/how-to-download-data-for-lesson-2-from-kaggle-for-planet-competition/7684

`pip install kaggle-cli`

 You'll need to sign up for and confirm an account at kaggle.com, preferably not using a social media account. 
 You'll also need to accept competition rules on kaggle.com, and potentially imageset rules. I needed to click many confirmations.

`kg config –u <your email address> -p <your password> -c <competition> `

 <competition name> comes from the kaggle url, so https://www.kaggle.com/c/foo has a competition name of 'foo'

---

## Planet dataset - lesson 2
https://www.kaggle.com/c/planet-understanding-the-amazon-from-space

 first time:
`kg config –u <your email address> -p <your password> -c planet-understanding-the-amazon-from-space`

 Note, the planet data is 34GB compressed if you include the tiff archives, or 1.5GB without. We don't really need the tiff archives, but if you really want everything, you can do:

`kg download`

 If you don't want to use all that disk space, you can use the -f flag to download individual files. These are the ones we need.
```
kg download -f test-jpg-additional.tar.7z
kg download -f test-jpg.tar.7z
kg download -f test_v2_file_mapping.csv.zip
kg download -f train-jpg.tar.7z
kg download -f train_v2.csv.zip
```

---

## Stanford Cars Dataset - lesson 2
 can be downloaded straight from a link at https://www.kaggle.com/jessicali9530/stanford-cars-dataset (2GB)
 in theory, this should also work, but I ran into beautifulsoup errors

`kg dataset -o jessicali9530 -d stanford-cars-dataset`

---

## digit-recognizer - lesson 2
 kaggle-cli is already configured, so I don't need to pass it my credentials any more 

`kg download -c digit-recognizer`
