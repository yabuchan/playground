# App based on Semantic Parsing

## Where do I go next?

- If you're new to semantic parsing, you can learn more from the [background
  reading section of the tutorial](TUTORIAL.md).
- Install SEMPRE using the instructions under **Installation** below.
- Walk through the [tutorial](TUTORIAL.md)
  to get a hands-on introduction to semantic parsing through SEMPRE.
- Read the complete [documentation](DOCUMENTATION.md)
  to learn about the different components in SEMPRE.

# Installation

## Requirements

You must have the following already installed on your system.

- Java 8 (not 7)
- Ant 1.8.2
- Ruby 1.8.7 or 1.9
- wget

Other dependencies will be downloaded as you need them.  SEMPRE has been tested
on Ubuntu Linux 12.04 and MacOS X.  Your mileage will vary depending on how
similar your system is.

## Easy setup

1. Clone the GitHub repository:

        git clone https://github.com/percyliang/sempre

2. Download the minimal core dependencies (all dependencies will be placed in `lib`):

        ./pull-dependencies core

3. Compile the source code (this produces `libsempre/sempre-core.jar`):

        ant core

4. Run an interactive shell:

        ./run @mode=simple

    You should be able to type the following into the shell and get the answer `(number 7)`:
   
        (execute (call + (number 3) (number 4)))

To go further, check out the [tutorial](TUTORIAL.md) and then the [full
documentation](DOCUMENTATION.md).

## Virtuoso graph database

If you will be using natural language to query databases (e.g., Freebase), then
you will also need to setup your own Virtuoso database (unless someone already
has done this for you):

    # For Ubuntu, make sure these dependencies are installed
    sudo apt-get install -y automake gawk gperf libtool bison flex libssl-dev

    # Clone the repository
    git clone https://github.com/openlink/virtuoso-opensource
    cd virtuoso-opensource
    git checkout tags/v7.0.0

    # Configure
    ./autogen.sh
    mv INSTALL INSTALL.txt  # Avoid conflict on case-insensitive file systems
    ./configure --prefix=$PWD/install

    # Make (this takes a while)
    make
    make install
    cd ..

# ChangeLog
none
