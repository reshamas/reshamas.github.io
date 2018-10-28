

<p>
<img src="../assets/images/fl1_rs_camel.jpg" width="50%" height="50%" />
</p>


## Intro

The third iteration of the [fastai course]((http://course.fast.ai)), Practical Deep Learning for Coders, began this week.  I am one of 2,000 International Fellows for the course which means we are able to join remotely and tuition-free.  We have access to live videos and the [fastai Discourse Forums](https://forums.fast.ai).  The live, [in-person, course](https://www.usfca.edu/data-institute/certificates/deep-learning-part-one) is at University of San Francisco (USF), where about 300 students are attending.  

The course uses the recent release of [fastai version 1.0](http://www.fast.ai/2018/10/02/fastai-ai/) and PyTorch 1.0, which are both cutting edge. The MOOC is set to be released in early 2019.  

### Work In Progress

The fastai library and documentation are being updated as the course progresses.  Patience is important as students share progress as well as glitches encountered.  Anyone is welcome to contribute to the library, as it is open source.  Learning to search the Forums and google errors are important skills to master. 

💡Therefore, it is of upmost interest to be working with the latest version of the fastai library:  `git pull`


## New York City (NYC) Study Group
I participated in last year's (Fall 2017 version 2) online course.  Due to mobility issues related to my ankle, I was unable to meet NYC participants in person.  Since then, I had ankle surgery this past spring.  I am now mobile enough to meet NYC fastai learners in person!

Each region, based on timezone, has study groups.  The NYC study group met, for the first time, for this course, this past Monday, just a few hours prior to the first livestream lesson (22-Oct-2018).  The lectures are live at 9:30pm to midnight (EST). Special thanks to IBM and Galvanize for providing the space.  One of our members, German, had met [Soumith Chintala](https://twitter.com/soumithchintala) at an event and invited Soumith to our study group.  It was a real treat to meet and chat with the creator of [PyTorch](https://pytorch.org).  There were 10 of us in the study group, so we had a casual 2-hour discussion, taking the opportunity to meet everyone in person and ask Soumith any questions we had about PyTorch, its development and its future.  NYC is an amazing place to live and which permits us access to resources and people. What a privilege to live in this bustling city!

<p float="left">
<img src="../assets/images/fl1_soumith.jpg" width="45%" height="45%"  style="padding:1px;border:thin solid black;" />
<img src="../assets/images/fl1_nyc_group.jpeg" width="45%" height="45%"  style="padding:1px;border:thin solid black;" />
</p>
<p>
</p>


## Lesson 1 Homework
In the course last year, I mainly watched the videos, created documentation and followed the Forums discussion.  This time, I was excited about entering the course with some familiarity and being better prepared to do the assignments.  The documentation and tutorials that are available in this iteration make the course significantly more accessible.  Before I began training a neural net on my own dataset, I did the following:  

### Preparation / Homework:  parts completed ✅
- Google Cloud setup
  - Get GPU going
- read lesson1 notebook
- read [Lesson 1 notes](https://forums.fast.ai/t/deep-learning-lesson-1-notes/27748)
- read tutorial on creating own Image dataset using Google Images
- read fastai documentation
- run lesson1-pets Jupyter notebook, which was presented in Lecture 1, to ensure all code runs without errors

When I ran into errors, I would search the Forums or Google it.  I was able to proceed!

💡<a style="color:red">Reading the documentation and class notes and notebook prior to work is an invaluable investment.  It saves hours of time troubleshooting coding issues.</a>

### Dataset

Our Lesson 1 homework is to obtain our own data and train a classifier to distinguish between two objects.  I am enchanted by camels, ever since my trip to Morocco nearly 15 years ago!  So, I chose [camels](https://www.google.com/search?tbm=isch&source=hp&biw=1706&bih=838&ei=7eDUW4uLK4WD5wKttJiYDQ&q=camels&oq=camels&gs_l=img.3..0l8j0i10j0.1393.2039..2176...0.0..0.60.325.6......2....1..gws-wiz-img.....0.6Uxdn2rWHp4) and [horses](https://www.google.com/search?tbm=isch&source=hp&biw=1706&bih=838&ei=7eDUW4uLK4WD5wKttJiYDQ&q=horses&oq=horses&gs_l=img.3..0l10.1513.2223..2416...0.0..0.57.317.6......1....1..gws-wiz-img.....0.kzRPHplRFRU).

<p float="left">
<img src="../assets/images/fl1_camel.jpeg" width="45%" height="45%" style="padding:1px;border:thin solid black;" />
<img src="../assets/images/fl1_horse.jpeg" width="45%" height="50%" style="padding:1px;border:thin solid black;" />
</p>
<p>
</p>

I began with a small sample, only 50 images in each class. URLS of images, in a `.csv` file, were downloaded to my local computer using [Google Images](https://images.google.com).  I uploaded the files to [Google Cloud Platform](https://images.google.com) (GCP) using the `scp` (Secure Copy) command.  

This is how the urls are stored in the text file:  
<p>
<img src="../assets/images/fl1_horses_txt.png" width="90%" height="90%"  style="padding:1px;border:thin solid black;" />
</p>

I converted the file to `.txt` so it would be consistent with what was used in the course notebooks.  I also renamed the files and moved them to the appropriate folders.  
 
 
### Google Cloud Platform
This was my first time using Google Cloud Platform (GCP).  Previously, I have used AWS, but since I ran out of credits, I decided to give GCP a try.  It certainly helps to have some experience with one cloud platform.  I attempted to upload the urls text file from my local computer up to GCP using commands I had previously used with AWS, but received an error.  A quick search in Google yielded that I needed to update my code:
- AWS:  `scp -r urls_horses.txt ubuntu@111.11.111.411:`
- GCP:  `gcloud compute scp urls_horses.txt jupyter@my-fastai-instance:~`

<p>
<img src="../assets/images/fl1_gcp1.png" width="80%" height="80%" />
</p>

Based on my recent use of GCP, it looks like many commands begin with `gcloud` or `gcloud compute`.

```bash
gcloud --version
gcloud auth login
gcloud compute ssh --zone=us-west2-b jupyter@my-fastai-instance -- -L 8080:localhost:8080
gcloud compute scp urls_horses.txt jupyter@my-fastai-instance:~
```

### Result for Camels / Horses
I used a small dataset, about 80 images.  I used a CNN pre-trained model, and trained for 4 epochs (number of passes through the data). The architecture used was resnet34.  Below are my results:  
```python
learn = ConvLearner(data, models.resnet34, metrics=error_rate)
learn.fit_one_cycle(4)
```
```bash
Total time: 00:35
epoch  train_loss  valid_loss  error_rate
1      1.220116    0.686683    0.285714    (00:09)
2      0.807073    0.375571    0.103896    (00:07)
3      0.640212    0.295698    0.051948    (00:09)
4      0.556612    0.225274    0.051948    (00:08)
```
The **error rate** was **5.2%**, which is pretty good!

Next, since this was a pre-trained model, I can train the last layers by unfreezing them, finding a learning rate and more learning.  
```python
learn.unfreeze()
learn.lr_find(stop_div=False)
learn.recorder.plot()
learn.fit_one_cycle(2, max_lr=slice(1e-4,1e-3))
```
```bash
Total time: 00:17
epoch  train_loss  valid_loss  error_rate
1      0.169633    0.141895    0.064935    (00:09)
2      0.138307    0.179179    0.038961    (00:08)
```
The **error rate** is now reduced to **3.9%**.  

A closer look at the classification shows that only 3 images were mis-classified, and for all 3, they were predicted to be horses, but were actually camels.  

Here is the confusion matrix.  
- 36 camels were classified correctly
- 38 horses were classified correctly
- 3 camels were misclassified as horses

<p>
<img src="../assets/images/fl1_camels_confusion.png" width="60%" height="60%" style="padding:1px;border:thin solid black;"/>
</p>

Here we can see the first row shows the 3 missclassified images.  The first image has the highest loss, where we see the man holding the camel's head. 
The numbers at the top of the images represent, in this order:  
- prediction label
- actual label
- loss
- probability it was predicted

<p>
<img src="../assets/images/fl1_camels_class.png" width="95%" height="95%" style="padding:1px;border:thin solid black;"/>
</p>


In retrospect, it is quite easy to tell the difference between camels and horses.   Let's challenge the neural network with something more difficult to discern, even for a human...

---

## Classifier for Elephants:  African vs Asian
Elephants are one of my favorite animals.  This is the closest I ever came to an elephant, while on a safari in South Africa.

<p>
<img src="../assets/images/fl1_south_africa.png" width="76%" height="75%" style="padding:1px;border:thin solid black;"/>
</p>

I remember learning in school that there are two different types.  I cannot visually distinguish between the two types.  

I learned, after reading [What’s the Difference Between Asian and African Elephants?
](https://www.britannica.com/story/whats-the-difference-between-asian-and-african-elephants), that's it's all in the **ears**.

>Asian and African elephants can be differentiated most easily by their **ears, their head shape, and their tusks**.
The easiest way to distinguish African elephants from Asian elephants is to look at the ears. African elephants have much larger ears that look sort of like the continent of Africa, while Asian elephants have smaller, round ears. Elephants’ ears dissipate their body heat, and African elephants need to dissipate more heat than Asian elephants, since they live in a hotter climate (that’s getting even hotter with climate change). African elephants and Asian elephants also differ in head shape. African elephants have rounded heads, while Asian elephants have a twin-domed head, which means there’s a divot line running up the head. Finally, you can look at the tusks. Both male and female African elephants can have tusks, but only male Asian elephants can grow them. It’s important to note, however, that not all male Asian elephants nor all African elephants necessarily develop tusks.

Let's see how well a CNN classifier does in differentiating the two types of elephants!

### PART A:  Getting Data Ready

#### Step 1:  **Download URLs** (on local computer)
	- for [african elephants](https://www.google.com/search?tbm=isch&source=hp&biw=1706&bih=773&ei=NuLVW_vZKeKGggfj5JzwDw&q=african+elephants&oq=african+elephants&gs_l=img.3..0l10.2032.4335..4430...0.0..0.80.943.17......0....1..gws-wiz-img.x6tVGnm8lj0)
    		- this will put `download.csv` file in `Downloads` folder
		- Rename to:  `african.csv`
	- for [asian elephants](https://www.google.com/search?tbm=isch&source=hp&biw=1706&bih=773&ei=TOLVW4GiI8Ob_QbqwqOwBg&q=asian+elephants&oq=asian+elephants&gs_l=img.3..0l10.1085.3027..3092...0.0..0.65.837.15......0....1..gws-wiz-img.U3fVVgzco34 )
    		- this will put `download.csv` file in `Downloads` folder
		- Rename to:  `asian.csv`

#### Step 2:  **Upload both URLs file to GCP** (on local computer)

```bash
gcloud compute scp /Users/reshamashaikh/Downloads/african.csv jupyter@my-fastai-instance:~/tutorials/data
gcloud compute scp /Users/reshamashaikh/Downloads/asian.csv jupyter@my-fastai-instance:~/tutorials/data
```

>my example

```bash
% gcloud compute scp /Users/reshamashaikh/Downloads/african.csv jupyter@my-fastai-instance:~/tutorials/data
No zone specified. Using zone [us-west2-b] for instance: [my-fastai-instance].
Enter passphrase for key '/Users/reshamashaikh/.ssh/google_compute_engine': 
african.csv                                                                 100%   72KB 197.2KB/s   00:00    
% gcloud compute scp /Users/reshamashaikh/Downloads/asian.csv jupyter@my-fastai-instance:~/tutorials/data
No zone specified. Using zone [us-west2-b] for instance: [my-fastai-instance].
Enter passphrase for key '/Users/reshamashaikh/.ssh/google_compute_engine': 
asian.csv                                                                   100%   80KB 236.1KB/s   00:00    
% 
```

#### Step 3:  Log back into GCP

```bash
% gcloud compute ssh --zone=us-west2-b jupyter@my-fastai-instance -- -L 8080:localhost:8080                
Enter passphrase for key '/Users/reshamashaikh/.ssh/google_compute_engine': 
```

#### Step 4:  Go to appropriate `data` directory on GCP

```
jupyter@my-fastai-instance:~/tutorials/data$ pwd
/home/jupyter/tutorials/data
```

#### Step 5:  Convert to `.txt` files & Rename files

```bash
cat african.csv | tr  ',' '\n' > urls_african.txt
cat asian.csv | tr  ',' '\n' > urls_asian.txt
```

#### Step 6:  View the first 10 rows of the file

```bash
head urls_african.txt
head urls_asian.txt
```

>my example

```bash
jupyter@my-fastai-instance:~/tutorials/data$ head urls_african.txt 
https://media.buzzle.com/media/images-en/gallery/mammals/elephants/1200-elephants-performing-tricks-before-trainer.jpg
https://africageographic.com/wp-content/uploads/2017/03/Satao-II-a-6695-Dex-Kotze.jpg
https://i.pinimg.com/736x/17/34/95/173495e502ec35d16b24070a6d0cbb14--happy-elephant-cute-baby-elephant.jpg
https://i.pinimg.com/originals/57/39/13/573913e131f653e8b4600bba4a1e828b.jpg
https://c402277.ssl.cf1.rackcdn.com/photos/885/images/carousel_small/African_Elephant_7.27.2012_whytheymatter_HI_58709.jpg?1345580947
http://d2ouvy59p0dg6k.cloudfront.net/img/108954_374154.jpg
https://news.nationalgeographic.com/content/dam/news/photos/000/306/30651.ngsversion.1421960098780.adapt.1900.1.jpg
https://kids.sandiegozoo.org/sites/default/files/2017-07/elephant-tusks.jpg
https://nails.newsela.com/s3/newsela-media/article_media/2018/01/elem-es-african-elephant-dfbc68c5.jpg?crop=0%2C93%2C1366%2C860&height=496&width=885
https://elephantconservation.org/iefImages/2009/12/afele1.jpg
jupyter@my-fastai-instance:~/tutorials/data$
```

### PART A:  Working with the data
1.  Back to Jupyter notebook
- I began by making a copy of my `reshama_camels_clean.ipynb`.  Will call this project:  `reshama_elephants.ipynb`
```bash
cd /home/jupyter/course-v3/nbs/dl1/dl_fastai
cp reshama_camels_clean.ipynb reshama_elephants.ipynb
```

>my example

```bash
jupyter@my-fastai-instance:~/course-v3/nbs/dl1/dl_fastai$ pwd
/home/jupyter/course-v3/nbs/dl1/dl_fastai
jupyter@my-fastai-instance:~/course-v3/nbs/dl1/dl_fastai$ ls
lesson1-camels-reshama.ipynb  README.md                   reshama_camels.ipynb
lesson1-pets-reshama.ipynb    reshama_camels_clean.ipynb
jupyter@my-fastai-instance:~/course-v3/nbs/dl1/dl_fastai$ cp reshama_camels_clean.ipynb reshama_elephants.ipynb
```

I used 378 images.  After running the pre-trained CNN resnet34 model, these are the results.  Unsurprisingly, it did not perform as well as on the camels/horses data.  However, it is much more accurate than what I would predict, which would be 50%.  The error rate for this classifier is **29.9%**

<p>
<img src="../assets/images/fl1_elephant1.png" width="76%" height="75%" style="padding:1px;border:thin solid black;"/>
</p>

After unfreezing last layers and re-running the neural net, the error improved to **25.4%**.
```bash
Total time: 00:18
epoch  train_loss  valid_loss  error_rate
1      0.343066    0.696139    0.164179    (00:08)
2      0.334749    1.065531    0.253731    (00:10)
```

Here's a visual on some of the misclassified images, dispelling the myth that deep learning is a black box and non-interpretable:
1.  In the middle image, both types of elephants are present.  So, it is unsurprising this image was misclassified.  
2.  In the lower left and lower right images, ears are missing in the image.  Since that is the key difference in differentiating between the two, it is unsurprising.
3.  In the top right image, the ears are hidden behind the splashing water.


<p>
<img src="../assets/images/fl1_elephant_predict.png" width="76%" height="75%" style="padding:1px;border:thin solid black;"/>
</p>


This is the confusion matrix:  
- 12 and 38 African/Asian elephants were labeled correctly
- 9 and 8 African/Asian elephants were misclassified, respectively

<p>
<img src="../assets/images/fl1_elephant_cm.png" width="76%" height="75%" style="padding:1px;border:thin solid black;"/>
</p>

After unfreezing the model and training some more, the error rate reduced to **19.4%**.  Making progress!
```bash
Total time: 00:16
epoch  train_loss  valid_loss  error_rate
1      0.239210    0.705375    0.223881    (00:07)
2      0.255059    0.636563    0.194030    (00:08)
```

#### Next steps
- I used about 400 images.  I can re-run the neural networks with a larger sample and see if the error rate decreases.
- I will try different architectures, such as resnet50.  


---

## Tweets
<p>
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Full house at the first class of <a href="https://twitter.com/hashtag/DeepLearning4Coders?src=hash&amp;ref_src=twsrc%5Etfw">#DeepLearning4Coders</a> + 3k students live steaming from all over the world <a href="https://twitter.com/DataInstituteSF?ref_src=twsrc%5Etfw">@DataInstituteSF</a> <a href="https://twitter.com/fastdotai?ref_src=twsrc%5Etfw">@fastdotai</a> <a href="https://twitter.com/jeremyphoward?ref_src=twsrc%5Etfw">@jeremyphoward</a> <a href="https://twitter.com/math_rachel?ref_src=twsrc%5Etfw">@math_rachel</a> <a href="https://t.co/2xcjecGcy4">pic.twitter.com/2xcjecGcy4</a></p>&mdash; Ignacio López-Francos (@iglpzfr) <a href="https://twitter.com/iglpzfr/status/1054589335956144128?ref_src=twsrc%5Etfw">October 23, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</p>


<p>
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Excited for the start of the new deep learning course! <a href="https://twitter.com/DataInstituteSF?ref_src=twsrc%5Etfw">@DataInstituteSF</a> <a href="https://t.co/Ai0fKanRaJ">pic.twitter.com/Ai0fKanRaJ</a></p>&mdash; Rachel Thomas (@math_rachel) <a href="https://twitter.com/math_rachel/status/1054545291825696768?ref_src=twsrc%5Etfw">October 23, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</p>

<p>
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Thanks to <a href="https://twitter.com/TheEconomist?ref_src=twsrc%5Etfw">@TheEconomist</a> for recognizing our work at <a href="https://t.co/GEOZuodrZj">https://t.co/GEOZuodrZj</a>, where we&#39;re doing what we can to being real diversity to AI.<br><br>Apparently the writers reached out to many to research this story &amp; got unanimously glowing feedback - so thanks all!<a href="https://t.co/F7WuMJnbIv">https://t.co/F7WuMJnbIv</a> <a href="https://t.co/NVXgbmKj5z">pic.twitter.com/NVXgbmKj5z</a></p>&mdash; Jeremy Howard (@jeremyphoward) <a href="https://twitter.com/jeremyphoward/status/1055626641601253376?ref_src=twsrc%5Etfw">October 26, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</p>

<p>
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">New release of fastprogress for fastai. Prettier and completely coded in HTML so it doesn&#39;t rely on widgets anymore which means an easier installation and compatibility with Colab ^^ <a href="https://t.co/G003usVe79">pic.twitter.com/G003usVe79</a></p>&mdash; Sylvain Gugger (@GuggerSylvain) <a href="https://twitter.com/GuggerSylvain/status/1055571427653500934?ref_src=twsrc%5Etfw">October 25, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</p>




