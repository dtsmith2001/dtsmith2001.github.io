# Current Project

My current project is to investigate computer vision using deep learning, and learn more about TensorFlow and Keras. I've set up an AWS free account and started reading the documentation to learn more about the service, and how to set things up.

A friend advised me to start with the [diabetic retinopathy detection](https://www.kaggle.com/c/diabetic-retinopathy-detection) competition. Although the competition is closed, he advised me it's not difficult to get good results, but more difficult to get great results. I'm also interested in investigating [universal adversarial perturbation](https://arxiv.org/abs/1610.08401) and see if I can improve the results by expanding the number of images.

Another interesting blog post covers [compressing and regularizing deep neural networks](https://www.oreilly.com/ideas/compressing-and-regularizing-deep-neural-networks).

Sebastian Ruder's article on [gradient descent optimization algorithms](http://sebastianruder.com/optimizing-gradient-descent/index.html) is very interesting.

## Tasks

- [x] Created AWS account
- [x] Identified promising project (see below)
- [x] AWS [documentation review](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/get-set-up-for-amazon-ec2.html)
- [ ] Download and install Anaconda 3, TensorFlow, and Keras
- [ ] Further investigate the two minute warning for shutting down an instance when bidding on compute time
- [ ] Learn how to process the images themselves
- [ ] Paper reviews

## Pre-modeling the Data

I'd also like to create a classifier which helps determine if an image is off-center or blurred. I suspect this kind of feature, fed to the deep learning network, could help with detection.

# AWS Spot Termination Notices

Amazon now gives you a two minute warning for spot termination notices. Spot instances are only activated or run when the spot price falls below your pre-selected limit. When the spot price rises, the instance is terminated. Before the instance terminates, you need to save your results, log files, etc.

There is a [simple way](https://blog.fugue.co/2015-01-06-spot-termination-notices.html) to detect the termination notice. However, I'd like to write a Python 3 module that would handle this in a graceful way, including ```job lib.dump``` on my model, save log files, record the record just used in the fit process, etc. That way, the instance could recover on its own and continue the neural network fit.

# Python

I added [timed rotation log handlers with compression](http://stackoverflow.com/questions/8467978/python-want-logging-with-log-rotation-and-compression) to my [Python learning](https://github.com/dtsmith2001/python-learning-code) repository.

I am [monitoring my memory usage](http://pythonforbiologists.com/index.php/measuring-memory-usage-in-python/) using the ```resource``` package. It only works on Posix systems, however. I am displaying the maximum memory used during the lifetime of the program, which is very useful when doing grid searches or large number of trees with larger data sets.

And I've also figured out how to [use Jupyter notebooks remotely using ssh tunneling](http://www.datasciencebytes.com/bytes/2015/12/18/using-jupyter-notebooks-securely-on-remote-linux-machines/). It's very simple, and allows me to move my work off my Windows 10 laptop onto a RedHat box with a lot more memory. I've had problems lately running out of memory.

# Dotfiles

I'm slowly working on my Linux and OS X dotfiles. This is a particular pain point for me, as I am tired of setting up dotfiles at new jobs. So check out [my dotfiles](https://github.com/dtsmith2001/configuration).

# Jupyter Add-Ons

## [jupyter-themer](https://github.com/transcranial/jupyter-themer)

I use [jupyter-themer](https://github.com/transcranial/jupyter-themer) to make my notebooks more readable. In particular, I was inspired by @brandon-rhodes style sheets found in his [Pandas tutorial from PyCon 2015](https://github.com/brandon-rhodes/pycon-pandas-tutorial). I prefer striped tables myself, so I looked around a bit. I don't know anything about CSS, but I did find a whole [list of examples](http://www.w3schools.com/css/css_table.asp). I made my own stylesheet using Brandon's and added the striped table example. jypyter-themer then copied the style sheet and I'm good to go. I sent a pull request to the maintainer for the ```hover table``` layout. You can how install this layout yourself. Beware, if you modify the CSS, you must reinstall jupyter-themer again before you can activate it.

One other thing I learned from @brandon-rhodes talk was to use the plot method for DataFrame rather than matplotlib directly. Oh, and I also use seaboard with the ggplot2 theme in my Jupyter notebooks.

## [bash-kernel](https://github.com/takluyver/bash_kernel)

Enough said.

# [Effective Pandas](https://leanpub.com/effective-pandas) by @TomAugspurger

I’ve read parts of this book (which is based on a series or blog posts), and learned a lot. I particularly like method chaining with automatic logging and the pipelines and categorically chapters. Oh, the [notebooks are available](https://github.com/TomAugspurger/modern-pandas).

I wish more authors would turn a series of blog posts into books!

# Spark and Cassandra

[Spark and Cassandra](https://academy.datastax.com/resources/getting-started-apache-spark-and-cassandra?unit=getting-started-apache-spark-and-cassandra) are a good alternative to Hadoop as the back-end, especially since Cassandra is familiar to SQL users.

# Debugging RESTful API's with [Postman](https://www.getpostman.com)

I've had occasion recently to debug API calls, and a colleague (thanks, Anna!) suggested I use Postman. Well, it's good. In fact, it's very good. And you can create test suites from your history to facilitate automated testing. The test suite also serves as a good collection of examples for documentation.

# PCA and y-Aware Scaling

Nina Zumel wrote a series of blog posts on y-aware PCA and feature scaling. PCA does not take into account the predicted variable.

1. [Principal Components Regression, Pt.1: The Standard Method](http://www.win-vector.com/blog/2016/05/pcr_part1_xonly/)
2. [Principal Components Regression, Pt. 2: Y-Aware Methods](http://www.win-vector.com/blog/2016/05/pcr_part2_yaware/)
3. [y-aware scaling in context](http://www.win-vector.com/blog/2016/06/y-aware-scaling-in-context/)

# Finis

My [repository list](https://github.com/dtsmith2001?tab=repositories) is public, so feel free to look over it.
