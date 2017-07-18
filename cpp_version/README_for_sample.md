cd build
To train a random forest and save it:
./ranger --verbose --file ../src/test.dat  --depvarname label --treetype 1 --probability --ntree 1 --nthreads 4 --output PREFIX_TEST --write

To predict with a file
./ranger --file ../src/test.dat --probability --predict ranger_out.forest 
