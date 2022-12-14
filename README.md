# Content Based Video Retrieval for Pattern Matching Video Clips (Code)

The latex report of this dissertation can be found online at the following URL: [https://github.com/Adamouization/Content-Based-Video-Retrieval-Dissertation](https://github.com/Adamouization/Content-Based-Video-Retrieval-Dissertation)

## Abstract

This project presents the design concepts and implementation steps of a content-based retrieval system for videos. Nowadays, unstructured data grows at exponential rates, and content-based retrieval systems can help improve the problem. Most of this unorganised data originating from social networks exists in the form of videos, which is why the task of retrieving videos from large databases is an important one.

The project was originally inspired by the famous music-matching mobile application *Shazam*, with the aim to create a similar system for matching movies in order to address the previously mentioned issue. However, an application of this scope has natural limitations due to the colossal size that a database of movies would occupy and the legal issues of employing copyrighted movies for an application. Therefore, this dissertation aims to create a prototype version of the system and later explore potential improvements to overcome these limitations.

Ultimately, a functional system was built by combining multiple methods into one pipeline and tested with a database of 50 short videos along with various videos recorded through mobile phones, resulting in correct matches reaching accuracies of 93\%. To increase the realism of the tests, the recorded queries replicated videos of poor quality with shaking hand motions and inadequate framing to imitate what user-recorded videos would look like, which the system managed to cope with at the cost of some accuracy. The results were then compared to an online experiment conducted to establish ground truth, which required participants to play the role of the video matching system. To complete the pipeline, a feature-length movie was used to test how it could be condensed into one still per shot.

## Project Structure

```
.
????????? app                 // source root
???   ????????? main.py             // program entry point, parses console arguments
???   ????????? histogram.py        // generates, averages and stores histograms
???   ????????? video_operations.py // query video operations
???   ????????? helpers.py          // general helper functions
???   ????????? config.py           // global variables
????????? footage             // database videos
????????? recordings          // query videos
????????? results             // figures, plots and csv files depicting results
????????? requirements.txt    // pip installation file
```

## Installation

* Clone the project
```
cd ~/Projects
git clone https://github.com/Adamouization/Content-Based-Video-Retrieval-Code
cd Content-Based-Video-Retrieval-Code
```

* Create a new virtual environment with Python 3

`virtualenv -p python3 ~/Environments/Content-Based-Video-Retrieval-Code`

* activate the virtual environment

`source ~/Environments/Content-Based-Video-Retrieval-Code/bin/activate`

* Install project dependencies

`pip install -r requirements.txt`

## Usage

```
python app/main.py --model <model> --mode <mode> (--showhists) (--debug)
```

where:

* `--model` indicates the histogram model to use. Can be "all", "gray", "rgb" or "hsv". The "all" option will use the 3 histogram models to train/test the system.
* `--mode` indicates the mode to run in. Can be "train", "test" or "segment".
* `--showhists` is an optional flag. If the flag is set, all of the generated histograms will be displayed.
* `--debug` is an optional flag. If the flag is set, additional logs will be printed for debugging purposes.

Examples:

* To train the system and hide generated histograms: `python app/main.py --model all --mode test`
* To test the system and display generated histograms: `python app/main.py --model all --mode train --showhists`
* To train the system with RGB only: `python app/main.py --model rgb --mode train`
* To test the system with HSV only in debug mode: `python app/main.py --model hsv --mode test --debug`
* To segment a video using shot boundary detection: `python app/main.py --mode segment`

## TODO Project Boards

* [Project Presentation](https://github.com/Adamouization/Content-Based-Video-Retrieval-Code/projects/1) (18/02/2019)
* [Project Final Code](https://github.com/Adamouization/Content-Based-Video-Retrieval-Code/projects/2) (07/05/2019)
* [Project Future Improvements](https://github.com/Adamouization/Content-Based-Video-Retrieval-Code/projects/3) (post hand-in)

## License

* see [LICENSE](https://github.com/Adamouization/Content-Based-Video-Retrieval-Code/blob/master/LICENSE) file

## Contact
* email: adam@jaamour.com
* LinkedIn: [www.linkedin.com/in/adamjaamour](https://www.linkedin.com/in/adamjaamour/)
* website: www.adam.jaamour.com
* twitter: [@Adamouization](https://twitter.com/Adamouization)
