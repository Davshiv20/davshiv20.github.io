+++
title = "Book Review: Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow"
date = 2025-09-10
draft = false
categories = ["books"]
+++

**Author:** Aurélien Géron  
**Edition:** 3rd Edition  
**Published:** 2022

---

I am going to be posting my learnings from each chapter.

### Chapter 1: The Machine Learning Landscape

#### Overview

- Before we start, I'd like to admit that I have tried to start reading this book many times, but it is only today that I found the will, time, and patience to officially start it.  
  This chapter gives a solid introduction to *machine learning*, but with no abstraction. The author plunges you into the world of machine learning and intelligent systems, which motivates me to continue reading.

---

#### Some facts from the Chapter

- The author provides many examples which establish how machine learning is all about building **systems** that can **learn** and create context from data. Learning is measured by the ratio of how the **performance P** increases, with some **experience E**, on some **task T**.
- The importance and requirements of machine learning are discussed, especially for **complex systems** for which we have no algorithmic solution or for which the environment is dynamic or ever changing. Machine learning exists to replace long lists of hand-tuned rules, providing an approach to improve itself and, in a sense, productize itself.
- The book gives detailed examples on the use cases of machine learning, from filtering emails to self-governed gaming, showing the wide array of tasks where machine learning is implemented.
- **Supervised Learning** (labelled data), **Unsupervised Learning** (unlabelled data), and **Semi-supervised Learning** (learning and then labelling) are explained. **Batch Learning** (non-incremental, offline learning) and **Online Learning** (incremental) are introduced.
- **Instance-based learning** (where the system memorizes training data) and **model-based learning** (where the system learns by measuring similarities and making predictions) are introduced.
- The **Machine Learning Life Cycle** is explored, along with the challenges encountered at each step. The importance of choosing relevant data and balancing the size of the dataset is emphasized. Concepts such as **feature extraction** and **dimensionality reduction** are also mentioned.
- The concepts of **overfitting** and **underfitting** are introduced. Overfitting occurs when a model becomes too closely aligned to a portion of the data, capturing noise and irrelevant details instead of general patterns. Underfitting happens when the model is too simple to capture the nuances of the dataset, leading to poor performance on both training and test data.
- Some methods are described, such as **hyperparameter tuning**, **cross-validation**, and **model selection**, which are important for good machine learning practices.
- The chapter ends with the classic question of how to find the best model for a particular dataset that performs well in production or testing environments. The answer involves making **assumptions** and, of course, many more technical considerations that will be discussed in later chapters.

---

### My Thoughts

I really like how the author encourages active engagement and requires the reader to truly grapple with the technical concepts, rather than simply presenting everything in an overly simplified manner. I've only read one chapter so I can't say for sure, but I can assume that this chapter provides a solid foundation for the rest of the book. It's fair to say that I am excited to dive in further and write better content on it as I proceed.

---

### Further Reading

- [Official Book Website](https://homl.info/)
- [Scikit-Learn Documentation](https://scikit-learn.org/)
- [TensorFlow Documentation](https://www.tensorflow.org/)
- [Keras Documentation](https://keras.io/)
