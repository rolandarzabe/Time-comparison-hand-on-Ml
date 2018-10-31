# Time comparison-hand-on-ML

I'm going through each chapter of the book "Hands-on Machine Learning with Scikit-Learn & TensorFlow" trying to replicate the code and check the outputs for myself. Here are two Jupyter Notebooks one is the one I did going step by step reading the book, the other one is the original version (sort of) I copied from Aurélien Géron's Github repository for the book, chapter 2:
https://github.com/ageron/handson-ml

I'm trying to estimate the time I would need to train models, so I decided to run the notebook in my laptop (4 cores, no GPU) and in Google Colab (CPU and GPU)

As you can notice inside the notebooks I added time measurements for the different "fit" processes like linear regression, desicion tree and random forest also the correspondent cross validations and performed the timing for Grid Search and Random Search with the Random Forest Regressor.

I used the "time" package to make the measurements, initializing before the fit method is called and after it's done, subtracted the start time from the end and get the lapse time. In the end of the notebook, I sumarized the time it took for each calculation.


Two very strange things happen: 

My training time (for my notebook version) in my laptop was between 25 and 30 min for the whole notebook, when I run it in Google Colab with CPU only it was better than mine, for a few minutes (about 4).
When I run it with the GPU execution enviroment, the results were about 10% to 14% better, but I found it odd since the GPU in Colab is very powerful.
I run the training several times in my laptop and also Colab but the results were the same. So I switched to the original Jupyter notebook from Aurélien Géron's Github repository. I removed the graphics, some notes and added the time measurements and run it in Colab with GPU, and the results are very different from mine. It took about 1/4 of the time to train, basically, the same models and the same Cross validations and the same Grid and Random search (I see no difference between the code it's been timing). What I am missing here?  


Second: The Random Searh takes much longer (like 3 times) than the time it takes to perform the Grid Search. The Grid search performs 90 models iterations and the Random Search performs about half of that, and that is consistent in both notebooks my version and the original from Aurelien Geron, How is it possible to take longer?


My version's times:

Linear Regression: 5.383306980133057,
Decision Tree Reg: 7.044358968734741,
Random Forest: 16.985894441604614,
Cross Val Linear Regression: 2.60886812210083,
Cross Val Decision Tree Reg: 17.805492401123047,
Cross Val Random Forest: 94.48191714286804,
Grid Search Random Forest: 324.1061816215515,
Random Search Random Forest: 815.0301121221873,



Original version (Aurélien Geron's)

Linear Regression: 3.3887457847595215,
Decision Tree Reg: 4.96132755279541,
Random Forest: 18.24065443284604321,
Cross Val Linear Regression: 5.0362162590026855,
Cross Val Decision Tree Reg: 6.812582492828369,
Cross Val Random Forest: 18.022871255874634,
Grid Search Random Forest: 57.98131060600281,
Random Search Random Forest: 211.35021710395813,


Most likely I'm missing something very basic. All credits for this example, I'm poorly performing, go to Aurélien Géron and his amazing book.
