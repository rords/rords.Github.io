

## Rutgers Object Rearrangement Data Set (RORDS)
Object rearrangement is a critical robot skill, with broad applicability in logistics, industrial, and service domains. For example (see the figure below), store shelves often need to be tidied up to better service customers, which is done through object rearrangement. For single robot prehensile manipulation, assuming that one object is manipulated at a time, the aim is to find the optimal manipulation ordering based on a given objective, e.g., finding the least number of times objects must be grasped, moved, and subsequently released. 

<p align="center">
<img src="https://user-images.githubusercontent.com/53358252/136677096-a91984d4-18a8-4956-9357-ff067db8f035.png" alt="grocery" height="200"/>
<img src="https://user-images.githubusercontent.com/53358252/136677099-9d4308a5-693a-40f9-80c3-31197bfcf177.png" alt="rearrangement" height="200"/>
</p>

To abstract away complex robot geometric and dynamic constraints, here, it is assumed that an object move movement action is comprised of (1) lifting an object in place above its support surface, (2) move the object among other objects, collision-free, to another location in the workspace, and (3) placing the object down (see videos below for examples). As the number of objects grows, the size of the solution space grows exponentially, since a rearrangment plan can be viewed as an ordered object sequence. Natually, any combinatorial algorithm for taming the associate combinatorial explosion needs to deal with the trade-off between computation speed and solution quality. This begs the question: could a data-driven approach be taken that provide us with fast and high-quality solutions? 

With the question, we set up the Rutgers Object Rearrangement Data Set (RORDS), with the hope that next generation rearrangement algorithms can be developed based on machine-learning. In this initial release, three data sets, with increasing difficulty, are provided that correspond to three manipulation planning challenges. These challenges are listed below. 

<br>

## Challenge 1
The first set of instances contains ones that are monotone and ones that are not. An instance is monotonic if each object is moved no more than once. In other words, zero or one action is required for each object. Below, a monotone insance and a non-monotone instance are illustrated. 

### A Monotone Example
<video width="100%" src="https://user-images.githubusercontent.com/53358252/136675854-2900ca07-c02f-4509-bb53-e96804a66c01.mp4" data-canonical-src="https://user-images.githubusercontent.com/53358252/136675854-2900ca07-c02f-4509-bb53-e96804a66c01.mp4" controls="controls" muted="muted" class="d-block rounded-bottom-2 width-fit" style="max-height:640px;">
</video>


### A Non-Monotone Example
<video width="100%" src="https://user-images.githubusercontent.com/53358252/136675858-c40e9e7a-60ed-4bd9-8523-aa3fc67c6a4c.mp4" data-canonical-src="https://user-images.githubusercontent.com/53358252/136675858-c40e9e7a-60ed-4bd9-8523-aa3fc67c6a4c.mp4" controls="controls" muted="muted" class="d-block rounded-bottom-2 width-fit" style="max-height:640px;">
</video>

<br>

## Challenge 2
In the second set of instances, the question to be answered is whether a non-monotone rearrangement problem can become monotone after a (specific) single object *o* is moved away to an *external* buffer location. In the example below, o1 blocks o2 from the goal and o2 blocks o1 from the goal as well. Therefore, moving either o1 or o2 away from the workspace can make the rearrangement problem monotone.

<video width="100%" src="https://user-images.githubusercontent.com/53358252/136678280-00df289a-d4cc-4a9a-8eeb-e7f065472c8f.mp4" data-canonical-src="https://user-images.githubusercontent.com/53358252/136678280-00df289a-d4cc-4a9a-8eeb-e7f065472c8f.mp4" controls="controls" muted="muted" class="d-block rounded-bottom-2 width-fit" style="max-height:640px;">
</video>


<br>

## Challenge 3
The third set of instances increases the difficulty by further moving the buffer location to the be within the workspace. That is, given a specific object *o* and a buffer location *b* in the workspace, predict whether there is a rearrangement plan where *o* moves twice and uses *b* as the intermediate pose while other objects move only once (directly to their respective goal poses). In the example below, yellow discs B1 and B2 represent the predefined buffer locations. The problem can be solved by moving o1 to B1 or moving o2 to B2.

<video width="100%" src="https://user-images.githubusercontent.com/53358252/136678284-2a5240e1-1f7a-40a5-82e3-9fe0a518642b.mp4" data-canonical-src="https://user-images.githubusercontent.com/53358252/136678284-2a5240e1-1f7a-40a5-82e3-9fe0a518642b.mp4" controls="controls" muted="muted" class="d-block rounded-bottom-2 width-fit" style="max-height:640px;">
</video>


## Submit your Works
We provide the dataset in the form a kaggle competition. To download the dataset or participate in the challenge, go to this [kaggle link](https://www.kaggle.com/t/a2ab98062a174f40a5544760902bf79a). 

If you are interested in submitting your solution entry, [this notebook](https://www.kaggle.com/gaokai2021/offline-notebook-for-input-output) provides a submission guide with an offline notebook. If you want to submit with Kaggle's notebook editor, please refer to [this document](https://www.kaggle.com/docs/notebooks#using-the-notebooks-editor).

For further information, you may refer to [this file](/files/Rearrangement_Challenge.pdf).



