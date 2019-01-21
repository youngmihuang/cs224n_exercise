# CS224n_exercise
- Stanford 2019 CS224n:Natural Language Processing with Deep Learning: [course link](http://web.stanford.edu/class/cs224n/index.html)

## Schedule
| Due Date | Assignment                         | Done |
| :------- | ---------------------------------- | ---- |
| 1/15     | Assignment1: exploring word vector | V    |
| 1/22     | Assignment2: word2vec              | V    |
| 1/29     | Assignment3                        |      |
| 2/7      | Assignment4                        |      |
| 2/21     | Assignment5                        |      |



## Issue 

(close) 2019/1/20: **TA just update the test result of this example.**

The DIFFERENCE is: if you test the results before running on Stanford Sentiment Treebank as I did, you will get LOSS= 16.15119285363322; once you run `python run.py` and turn back running `python word2vec.py`, you will get LOSS = 14.3018669327. Be careful!

--Original topic--

In `assignment2/word2vec.py`,  my result of loss, gradCenterVec, gradOutsideVecs using **Skip-Gram with negSamplingLossAndGradient**,  not close to the expected value as TA given, can anyone give me some advice? Is there any tiny problem that I ignored?  Thanks.  

```
Skip-Gram with negSamplingLossAndGradient
Your Result:
Loss: 16.15119285363322
Gradient wrt Center Vectors (dJ/dV):
 [[ 0.          0.          0.        ]
 [ 0.          0.          0.        ]
 [-4.54650789 -1.85942252  0.76397441]
 [ 0.          0.          0.        ]
 [ 0.          0.          0.        ]]
 Gradient wrt Outside Vectors (dJ/dU):
 [[-0.69148188  0.31730185  2.41364029]
 [-0.22716495  0.10423969  0.79292674]
 [-0.45528438  0.20891737  1.58918512]
 [-0.31602611  0.14501561  1.10309954]
 [-0.80620296  0.36994417  2.81407799]]

Expected Result: Value should approximate these:
Loss: 14.3018669327
Gradient wrt Center Vectors (dJ/dV):
 [[ 0.          0.          0.        ]
 [ 0.          0.          0.        ]
 [-3.86035429 -2.8660339  -0.9739887 ]
 [ 0.          0.          0.        ]
 [ 0.          0.          0.        ]]
 Gradient wrt Outside Vectors (dJ/dU):
 [[-0.30559455  0.14022886  1.06668785]
 [-0.12708467  0.05831563  0.44359323]
 [-0.45528438  0.20891737  1.58918512]
 [-0.73739425  0.33836976  2.57389893]
 [-0.64496237  0.29595533  2.25126239]]
```

- Furthermore, I search the concept of **negative sampling in NLP** and I am considering of the problem as following: the way to calculate loss using the positive samples (bcz they used the 1 - negative probability) , make sense or not?  **Yes**