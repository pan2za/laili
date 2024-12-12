# laili
AI operation system

### packages
anaconda (Canceled, since anaconda has its own release)

ollama, from https://github.com/lingfish/ollama-deb, licensed by Apache-2.0

pytorch, (have done in UBUNTU 24.10, but have not in UBUNTU 24.04 LTS),       (ref: https://salsa.debian.org/deeplearning-team)

tensorflow  already availabe  (ref: https://salsa.debian.org/deeplearning-team/tensorflow)

Scikit-learn available at https://packages.debian.org/stable/python3-sklearn

numpy, available at https://packages.debian.org/sid/amd64/python3-numpy/download

Keras, available at https://packages.debian.org/bullseye/python3-keras

Pandas , available at https://packages.debian.org/bullseye/python3-pandas

Matplotlib, available in https://packages.debian.org/buster/python3-matplotlib 

Seaborn , available in https://packages.debian.org/en/stable/python/python3-seaborn

opencv , from https://github.com/swenkel/opencv_deb_single_package , licensed by FIXME

rag和langchain的

whisper-asr-service , from https://github.com/pan2za/whisper-asr-webservice, licensed by MIT.

## mailme

contact me at delta chat：

r4q4avjwx at nine.testrun.org

## reference

https://github.com/mijofa/mijofa.github.io

https://www.udacity.com/school/artificial-intelligence

## STEP 0.1 : clone the following code and installed it.

https://github.com/pan2za/github-apt-repos which is forked from https://github.com/X4BNet/github-apt-repos

command:

git clone https://github.com/pan2za/github-apt-repos

cd github-apt-repos

python3 setup.py install

## STEP 0.2: Collect all *.deb files

mkdir ~/cache

cp *.deb ~/cache/


## STEP 1: HTTP(S) PRO?XY

As to me, I use pro?xy, here it is fastgithub from somewhere.

The enviroment variables of the following should be set or github pull will fail.

<<run fastgithub ...>>

then,

export HTTP_PROXY=http://127.0.0.1:38457

export HTTPS_PROXY=https://127.0.0.1:38457

## STEP 2: ENVIROMENT VARIABLES SETTING

export GITHUB_USER=pan2za

export GITHUB_TOKEN=your_token_in_github


export GPGPASSWD=your_private_key_passphrase

export DEBEMAIL=484A5196D698B203 or your public key keyid

## STEP 3: repo creation/pull command

github-apt-repos --gpg-passwd "$GPGPASSWD" --gpg-user-id "$DEBEMAIL" --github-token=$GITHUB_TOKEN --deb-dir ~/cache/ --github-apt-repo  pan2za/laili

where 

GPGPASSWD is passphrase of private key

DEBEMAIL is last 8 hex text of the finger print, that is, 84A5196D698B203

GITHUB_TOKEN is from github.com/settings/token

~/cache is location for all *.deb local files.

If the command works, in the release page of github, the released apt repo should be found.


## STEP 4: you can add the release repo to your apt/source.list.d/laili.source.list.

to verify the public key, you should download my public key in this repo.

Have fun!
