# bat-country
<img src="initial_images/fear_and_loathing/fal_01.jpg?raw=true" style="max-width: 300px;"/><br/>
<img src="examples/output/fear_and_loathing/conv2_3x3_fal_01.jpg?raw=true" style="max-width: 300px;"/>
> We can't stop here, this is bat country. &mdash; Raoul Duke

The `bat-country` package is an **easy to use**, **highly extendible**, **lightweight Python module** for **inceptionism** and **deep dreaming** with Convolutional Neural Networks and Caffe. My contributions here are honestly pretty minimal. All the real research has been done by the [Google Research Team](http://googleresearch.blogspot.com/2015/06/inceptionism-going-deeper-into-neural.html) &mdash; I'm simply taking the [IPython Notebook](https://github.com/google/deepdream/blob/master/dream.ipynb), turning it into a Python module, while keeping in mind the importance of extensibility, such as custom step functions.

If you're looking for a more advanced CNN visualization tool, check out Justin Johnson's [cnn-vis](https://github.com/jcjohnson/cnn-vis) library.

## Installation
The `bat-country` packages requires [Caffe, an open-source CNN implementation from Berkeley](http://caffe.berkeleyvision.org/), to be already installed on your system. I detail the steps required to get Caffe up and running on your system in the [official bat-country release post](http://www.pyimagesearch.com/2015/07/06/bat-country-an-extendible-lightweight-python-package-for-deep-dreaming-with-caffe-and-convolutional-neural-networks/). An excellent alternative is to use the [Docker image](https://github.com/VISIONAI/clouddream) provided by Tomasz of Vision.ai. Using the Docker image will get you up and running quite painlessly.

After you have Caffe setup and working, `bat-country` is a breeze to install. Just use pip:

<pre>$ pip install bat-country</pre>

You can also install `bat-country` by pulling down the repository and using `setup.py`:

<pre>$ git clone https://github.com/jrosebr1/bat-country.git
$ pip install -r requirements.txt
$ python setup.py install</pre>

## A simple example
As I mentioned, one of the goals of `bat-country` is simplicity. Provided you have already installed Caffe and `bat-country` on your system, it only takes 3 lines of Python code to generate a deep dream/inceptionism image:

<pre># we can't stop here...
bc = BatCountry("caffe/models/bvlc_googlenet")
image = bc.dream(np.float32(Image.open("/path/to/image.jpg")))
bc.cleanup()</pre>

After executing this code, you can then take the `image` returned by the `dream` method and write it to file:

<pre>result = Image.fromarray(np.uint8(image))
result.save("/path/to/output.jpg")</pre>

And that's it!

For more information on `bat-country`, along with additional code examples, head over to the the official announcement post on the PyImageSearch blog:

[http://www.pyimagesearch.com/2015/07/06/bat-country-an-extendible-lightweight-python-package-for-deep-dreaming-with-caffe-and-convolutional-neural-networks/](http://www.pyimagesearch.com/2015/07/06/bat-country-an-extendible-lightweight-python-package-for-deep-dreaming-with-caffe-and-convolutional-neural-networks/)

## Some visual examples
Below are a few example images generated using the `bat-country` package:

<img src="initial_images/fear_and_loathing/fal_03.jpg?raw=true" style="max-width: 500px;"/><br/>
<img src="examples/output/fear_and_loathing/inception_4c_output_fal_03.jpg?raw=true" style="max-width: 500px;"/><br/><br/>

<img src="initial_images/the_matrix/matrix_01.jpg?raw=true" style="max-width: 500px;"/><br/>
<img src="examples/output/the_matrix/conv2_3x3_matrix_01.jpg?raw=true" style="max-width: 500px;"/><br/><br/>

<img src="initial_images/jurassic_park/jp_06.jpg?raw=true" style="max-width: 500px;"/><br/>
<img src="examples/output/jurassic_park/conv2_3x3_jp_06.jpg?raw=true" style="max-width: 500px;"/><br/><br/>

<img src="initial_images/jurassic_park/jp_01.jpg?raw=true" style="max-width: 500px;"/><br/>
<img src="examples/output/jurassic_park/conv2_3x3_jp_01.jpg?raw=true" style="max-width: 500px;"/><br/><br/>

<img src="initial_images/jurassic_park/jp_03.jpg?raw=true" style="max-width: 500px;"/><br/>
<img src="examples/output/jurassic_park/conv2_3x3_jp_03.jpg?raw=true" style="max-width: 500px;"/><br/><br/>