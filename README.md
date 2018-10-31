# Time comparison-hand-on-ML

I'm going through each chapter of the book "Hands-on Machine Learning with Scikit-Learn & TensorFlow" trying to replicate the code and check the outputs for myself. Here are two Jupyter Notebooks one is the one I did going step by step reading the book, the other one is the original version (sort of) I copied from Aurélien Géron's Github repository for the book, chapter 2:
https://github.com/ageron/handson-ml

I'm trying to estimate the time I would need to train models, so I decided to run the notebook in my laptop (4 cores, no GPU) and in Google Colab (CPU and GPU)

As you can notice inside the notebooks I added time measurements for the different "fit" processes like linear regression, desicion tree and random forest also the correspondent cross validations and performed the timing for Grid Search and Random Search with the Random Forest Regressor.

I used the "time" package to make the measurements, initializing before the fit method is called and after it's done, subtracted the start time from the end and get the lapse time. In the end of the notebook, I sumarized the time it took for each calculation.


<B>Two very strange things happened: </B>

<S>First:<S> My training time (for my notebook version) in my laptop was between 25 and 30 min for the whole notebook, when I run it in Google Colab with CPU only it was better than mine, for a few minutes (about 4).
When I run it with the GPU execution enviroment, the results were about 10% to 14% better, but I found it odd since the GPU in Colab is very powerful.
I run the training several times in my laptop and also Colab but the results were the same. So I switched to the original Jupyter notebook from Aurélien Géron's Github repository. I removed the graphics, some notes and added the time measurements and run it in Colab with GPU, and the results are very different from mine. It took about 1/4 of the time to train, basically, the same models and the same Cross validations and the same Grid and Random search (I see no difference between the code it's been timing). What I am missing here?  


<S>Second:</S> The Random Searh takes much longer (like 3 times) than the time it takes to perform the Grid Search. The Grid search performs 90 models iterations and the Random Search performs about half of that, and that is consistent in both notebooks my version and the original from Aurelien Geron, How is it possible to take longer?


<B>My version's times:</B>

Linear Regression: 5.38,
Decision Tree Reg: 7.04,
Random Forest: 16.98,
Cross Val Linear Regression: 2.60,
Cross Val Decision Tree Reg: 17.80,
Cross Val Random Forest: 94.48,
Grid Search Random Forest: 324.10,
Random Search Random Forest: 815.03,



<B>Original version (Aurélien Geron's)</B>

Linear Regression: 3.38,
Decision Tree Reg: 4.96,
Random Forest: 18.24,
Cross Val Linear Regression: 5.03,
Cross Val Decision Tree Reg: 6.81,
Cross Val Random Forest: 18.02,
Grid Search Random Forest: 57.98,
Random Search Random Forest: 211.35,


<B>*** I had to install scikit learn 0.20.0 because for some reason google colab's was outdated (0.19.2)
    You will notice a different order in the notebooks, this is because the book is different from the Git repository, but the code is essentially the same. 
    Please ignore the notes inside my version, some won't make sense since are crops from my personal notes.
    I tried to preserve all the code related in the original version, the results seem the same for the outputs.
    I run the notebooks several times to confirm the results and they were pretty consistent.
    Please ignore "t6" just is the code for instanciate the model, it doesn't appear in the original notebook</B>


Most likely I'm missing something very basic. All credits for this example, I'm poorly performing, go to Aurélien Géron and his amazing book.
