# Lorem Ipsum Samples
Generate 100 words from https://lipsum.com/
put them into file lipsum

sudo apt install espeak

for word in $(cat lipsum); do echo $word|sed 's/[^a-zA-Z0-9]//g'; done|sort -u >words
for word in $(cat words); do echo $word | espeak --stdin -w $word.wav; done
A number of samples.

Or
for word in $(cat lipsum); do echo $word|tr '[:upper:]' '[:lower:]' |sed 's/[^a-zA-Z0-9]//g'; done |nl -nrz | sort -u -k2 >words 
cat words|while read number word; do echo $word | espeak --stdin -w $number-$word.wav; done
A number of sorted samples
