%tensorflow_version 2.x
!pip uninstall -y tensorflow
!pip install tensorflow-gpu==1.14.0
!git clone https://github.com/vlomme/Multi-Tacotron-Voice-Cloning.git
cd Multi-Tacotron-Voice-Cloning/
!pip install -r requirements.txt
!apt-get install libportaudio2
!gdown https://drive.google.com/uc?id=1aQBmpflbX_ePUdXTSNE4CfEL9hdG2-O8
!unzip pretrained.zip
!python demo_cli.py -p "ex.wav" -t "Hello my friends. Я многоязычный синтез построенный на tacotron. Шла саша по шоссе и сосала сушку" --no_sound
import IPython.display as ipd
print("original(оригинал)")
ipd.display(ipd.Audio('ex.wav'))#filepath to original voices (Путь до оригинального файла)
print("cloned(клонированный)")
ipd.display(ipd.Audio('demo_output_00.wav'))#filepath to synthesized voices (Путь до синтезированного файла)
