# Python wrapper for Stanford NER

The unofficial cross-platform Python wrapper for the <b>state-of-art</b> named entity recognition library from Stanford University.

Input: `Google bought IBM for 10 dollars. Mike was happy about this deal.`

Output:

```
Google              	ORGANIZATION
IBM                 	ORGANIZATION
10 dollars          	MONEY
Mike                	PERSON
```

NOTE: It works well on Linux and Ubuntu but it's unclear for Windows.

## About Stanford NER

Named Entity Recognition (NER) labels sequences of words in a text which are the names of things, such as person and company names, or gene and protein names. It comes with well-engineered feature extractors for Named Entity Recognition, and many options for defining feature extractors. Included with the download are good named entity recognizers for English, particularly for the 3 classes (PERSON, ORGANIZATION, LOCATION).

More information can be found here : https://nlp.stanford.edu/software/CRF-NER.shtml

## Installation

First of all, make sure Java 1.8 is installed. Open a terminal and run this command to check:

```bash
java -version
```

If this is not the case and if your OS is Ubuntu, you can install it this way:

```bash
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java8-installer
```

## Getting set up

1. Create a virtual environment: `virtualenv env`
2. Enter that virtual environment: `source env/bin/activate`
3. Install the requirements: `pip install -r requirements.txt`
4. Run the Flask server: `python main.py`

**Note:** If you have any issues running the Flask server, for example: "the flask module isn't found", then delete your pre-existing virtual environment folder and create a new one. Follow steps 1-4 again. This should (hopefully) resolve the issue.

### Command

For best use, convert the text to uppercase and submit it to NER.

The code can be executed by the command line or by sending a curl request.

With the `main.py` server running, you can execute the folowing curl request.

```python
curl -G --data-urlencode "text=GOOGLE BOUGHT IBM FOR 10 DOLLARS. MIKE WAS HAPPY ABOUT THIS DEAL." http://127.0.0.1:5000/ner
```

### Output

```
Google              	ORGANIZATION
IBM                 	ORGANIZATION
10 dollars          	MONEY
Mike                	PERSON
```

## Support

Just open an issue. Any contributions are welcomed!
