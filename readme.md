
mkdir build<br>
cd build<br>
cmake .. <br>
make <br>
this could build your code and generate a .so file<br>
<br>
In that same dir run <br>
python <br>
import xtensor_python_test <br>
xtensor_python_test.sum_of_sines(3) <br>
<br>

# from setuptools
just cd into root where setup.py is and run<br>
pip install . <br>
now you can use the code from anywhere<br>
