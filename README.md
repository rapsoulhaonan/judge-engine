# Algohub Judge Engine

Algohub Judge Engine is a modern online judge engine, which supports most of programming languages.

Supported OS: Ubuntu 16.04, CentOS 6.7


## Install Dependencies

    ./install.sh


## Compile

    mvn clean package


## Run

    java -jar target/judge-engine-1.0-SNAPSHOT.jar src/test/resources/problems/2-sum/2-sum.json PYTHON src/test/resources/problems/2-sum/solution.py


## Install Dependencies Manually(for advanced users)


### Compilers and Interpreters

The judge engine uses compilers and interpreters under the hood, so you need to install compilers and interpreters in advance.

Currently Algohub Judge Engine uses JDK 8, GCC 5, Python3 and Ruby 2.

The following commands should be available in `$PATH`:

* `java`
* `javac`
* `g++`
* `python3`
* `ruby`


### Libraries and Pre-defined Modules


#### rapidjson

Algohub Judge Engine relies on the [rapidjson](ihttps://github.com/miloyip/rapidjson) library to support C++ language. So we need to make the rapidjson system wide.

    git clone git@github.com:miloyip/rapidjson.git
    sudo cp -r rapidjson/include/rapidjson/ /usr/local/include/


#### Pre-defined C++ Header Files

First, download the languages support files,

    git clone https://github.com/algohub/judge-engine-languages-support.git
    cd judge-engine-languages-support/

Algohub Judge Engine has some pre-defined C++ header files which are needed during compilation.

    sudo cp -r judge-engine-cpp-support/include/algohub/ /usr/local/include/


#### Pre-defined Python Module

The judge engine has a pre-defined python module named `algohub`, which is need during runtime.

Copy the Python `algohub` module  into one of Python's default module paths, i.e., `sys.path`

    python3 -c "import sys;print(sys.path);"
    cd judge-engine-languages-support/
    sudo cp -r judge-engine-python-support/algohub/ /usr/local/lib/python3.5/dist-packages/


#### Pre-defined Ruby module

The judge engine also has a pre-defined ruby module named `algohub`, which is need during runtime.

Copy the Ruby  `algohub` module into one of Ruby's default module search path(run `ruby -e 'puts $:'` to get all paths)

    cd judge-engine-languages-support/
    sudo cp ruby/algohub.rb /usr/local/lib/site_ruby/2.3.0/


## Acknowledgments

Special thanks to [@rednaxelafx](https://github.com/rednaxelafx), who is a compiler expert and gave me a lot of vital technical suggestions, this project would not have been possible without his help.

