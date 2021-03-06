<p align="center">
    <a href="https://github.com/cod-ed/simulate">
        <img src="https://raw.githubusercontent.com/cod-ed/assets/handwrite/logo.svg" width=40%>
        </img>
    </a>
</p>

[![Tests](https://github.com/cod-ed/handwrite/workflows/Tests/badge.svg)](https://github.com/cod-ed/handwrite/actions)
[![PyPI version](https://img.shields.io/pypi/v/handwrite.svg)](https://pypi.org/project/handwrite)
[![Gitter chat](https://badges.gitter.im/gitterHQ/gitter.svg)](https://gitter.im/codEd-org/handwrite)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

# Handwrite - Type in your Handwriting!

Ever had those long-winded assignments, that the teacher always wants handwritten?
Is your written work messy, cos you think faster than you can write?
Now, you can finish them with the ease of typing in your own font!

<p align="center">
        <img src="https://raw.githubusercontent.com/cod-ed/assets/handwrite/handwrite.gif">
        </img>
</p>

Handwrite makes typing written assignments efficient, convenient and authentic.

Handwrite generates a custom font based on your handwriting sample, which can easily be used in text editors and word processors like Microsoft Word & Libre Office Word!

Handwrite is also helpful for those with dysgraphia.

# Installing

1. Install [fontforge](https://fontforge.org/en-US/)

2. Install [Potrace](http://potrace.sourceforge.net/)

3. Install handwrite:

   ```console
   pip install handwrite
   ```

# Usage

## Creating your Handwritten Sample

1. Take a printout of the [sample form](https://github.com/cod-ed/handwrite/raw/main/handwrite_sample.pdf).

2. Fill the form using the image below as a reference.

3. Scan the filled form using a scanner, or Adobe Scan in your phone.

4. Save the `.jpg` image in your system.

Your form should look like this:

<p align="center">
        <img src="https://raw.githubusercontent.com/cod-ed/assets/handwrite/handwrite_filled_form.jpg" width=50%>
        </img>
</p>

## Creating your font

1. Make sure you have installed `handwrite`, `potrace` & `fontforge`.

2. In a terminal type `handwrite [PATH TO IMAGE or DIRECTORY WITH IMAGES] [OUTPUT DIRECTORY]`.
   (You can also type `handwrite -h`, to see all the arguments you can use).

3. (Optional) Config file containing custom options for your font can also be passed using
   the `--config [CONFIG FILE]` or `--config [DIRECTORY WITH CONFIG FILES]` argument.

   <blockquote>
   Note:

   - If passing a directory, make sure to rename the config files to the corresponding sheet names.
   - If a single config file is passed for multiple inputs, that config will be used for all the inputs.
   - If no config file is provided for an input then the [default config file](handwrite/default.json) is used.
   </blockquote>

3. Your font will be created as `OUTPUT DIRECTORY/OUTPUT FONT NAME.ttf`. Install the font in your system.

4. Select your font in your word processor and get to work!

Here's the end result!

<p align="center">
        <img src="https://raw.githubusercontent.com/cod-ed/assets/handwrite/handwrite_sentence.png">
        </img>
</p>

# Development

## Linux

1. Install Potrace using apt

   ```console
   sudo apt-get install potrace
   ```

2. Install fontforge

   ```console
   sudo apt-get install fontforge
   ```

   Since the PPA for fontforge is no longer maintained, apt might not work for some users. The preferred way to install is using the AppImage from: https://fontforge.org/en-US/downloads/

3. Clone the repository or your fork

   ```console
   git clone https://github.com/cod-ed/handwrite
   ```

4. (Optional) Make a virtual environment and activate it

   ```console
   python -m venv .venv
   source .venv/bin/activate
   ```

5. In the project directory run:

   ```console
   pip install -e .[dev]
   ```

6. Make sure the tests run:

   ```console
   python setup.py test
   ```

7. Install pre-commit hooks before contributing:

   ```console
   pre-commit install
   ```

You are ready to go!

## Windows

1. Install [Potrace](http://potrace.sourceforge.net/#downloading) and make sure it's in your PATH.

2. Install [fontforge](https://fontforge.org/en-US/downloads/) and make sure scripting is enabled.

3. Clone the repository or your fork

   ```console
   git clone https://github.com/cod-ed/handwrite
   ```

4. (Optional) Make a virtual environment and activate it

   ```console
   python -m venv .venv
   .venv\Scripts\activate
   ```

5. In the project directory run:

   ```console
   pip install -e .[dev]
   ```

6. Make sure the tests run:

   ```console
   python setup.py test
   ```

7. Install pre-commit hooks before contributing:

   ```console
   pre-commit install
   ```

You are ready to go!

## Credits and Reference

1. [Potrace](http://potrace.sourceforge.net/) algorithm and package has been immensely helpful.

2. [Fontforge](https://fontforge.org/en-US/) for packaging and adjusting font parameters.

3. [Sacha Chua's](https://github.com/sachac) [project](https://github.com/sachac/sachac-hand/) proved to be a great reference for fontforge python.

4. All credit for svgtottf converter goes to this [project](https://github.com/pteromys/svgs2ttf) by [pteromys](https://github.com/pteromys). We made a quite a lot of modifications of our own, but the base script idea was derived from here.
