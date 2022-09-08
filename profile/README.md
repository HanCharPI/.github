# HanChar Project

HanChar is a mobile application that is designed to recognize Japanese Kanji based on the user strokes and provide additional information of the selected kanji. 

HanChar uses machine learning to recognize images and return the best 8 possible results to the user, where a selected result displays some information such as meaning, pronunciations, stroke order and example words (with audio).

This is the integrative project Team 3 of Tecnologico de Monterrey, required as academic research for graduation in Computer Science. 

Each repository has its own installation instructions (currently only available in Spanish).

## Preview

If preview is not available, you can check it out in [Google Cloud](https://storage.googleapis.com/hanchar/preview.mp4).

https://user-images.githubusercontent.com/47795404/188935406-da8c62f3-e269-417f-9012-8312f184991c.mp4

## Front end

A hybrid mobile application designed with React Native, using [Expo](https://expo.dev/) as the development platform.
- Used [Ant Design RN](https://rn.mobile.ant.design/) as the main framework for the app components.
- For the canvas drawing, @MarangoniEduardo's [Expo Draw](https://github.com/MarangoniEduardo/expo-draw) library was adapted to the app.
- Due to licensing fees, the app is not published either on iOS App Store or Android Google Play.

> ⚠️ Due to the constant updates from Expo framework, the repository's package version will not work in latest Expo versions. Please refer to [this repository](https://github.com/feriosch/han-character-app-46) if interested in building.

## Back end

A PHP Laravel application providing HTTP endpoints for the front end app to communicate with the ML model and to obtain aditional information of the characters.
- Used [MySQL](https://www.mysql.com/) for secure authentication to the API.
- Used KanjiAlive's free [API](https://rapidapi.com/KanjiAlive/api/learn-to-read-and-write-japanese-kanji/details) for kanji information (e.g. pronunciation, meaning, examples).
- Though not presented in the front end app, used [Voice RSS](https://www.voicerss.org/) for individual on and kun pronunciations. 

> ℹ️ To save server costs, back end and ML servers are turned off most of the time. Please contact [@feriosch](https://github.com/feriosch) if you are interested in running the environment.

## ML Model

A Convulsional Neural Network (CNN) machine learning model for visual analysis. Trained with kanji images from writers, returning the top 8 results for a scope of ~1000 characters.
- Training data was obtained from [**ETL-8G Character Database**](http://etlcdb.db.aist.go.jp/). Electrotechnical Laboratory, Japanese Technical Committee for Optical Character Recognition, ETL Character Database, 1973-1984.
- The model was built using [Tensorflow Keras 2.4](https://www.tensorflow.org/versions/r2.4/api_docs/python/tf) for Python, using [Flask](https://flask.palletsprojects.com/en/2.2.x/) for communication with the backend.
- The preprocessing, data visualization and model training is explained in a [Jupyter](https://jupyter-notebook.readthedocs.io/en/latest/) notebook in the repository.

> ℹ️ The .h5 models are ignored in the repository. If interested in .h5 files, please contact [@feriosch](https://github.com/feriosch).
