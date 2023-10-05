# IEEE-CIS-Fraud-Detection
XGB Fraud

In this kernel, we build two XGB models. The first model does not use the magic features and achieves LB 0.95. The second model uses the magic features and achieves LB 0.96. In the appendix, we demonstrate how to increase LB further with post processing.

Reading one million rows of data from disk and engineering features takes 5 minutes using Pandas and CPU. Alternatively if we use RAPIDS cuDF and GPU, it takes only 20 seconds! CPU times are displayed beneath code blocks below and GPU 15x speed up is demonstrated here.

The Magic Feature - UID¶
We will now create and use the MAGIC FEATURES. First we create a UID which will help our model find clients (credit cards). This UID isn't perfect. Many UID values contain 2 or more clients inside. However our model will detect this and by adding more splits with its trees, it will split these UIDs and find the single clients (credit cards).
