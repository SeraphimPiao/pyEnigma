# pyEnigma

[![builds.sr.ht status](https://builds.sr.ht/~cedric/pyenigma.svg)](https://builds.sr.ht/~cedric/pyenigma)


[pyEnigma](https://git.sr.ht/~cedric/pyenigma), a  Python Enigma cypher machine
simulator.

For reporting issues, visit the tracker here:
https://todo.sr.ht/~cedric/pyenigma


## Usage


### As a Python library

You can install pyEnigma with Poetry.

```bash
$ poetry install pyenigma
```

Then you can use it in your program:

```python
Python 3.6.4 (default, Feb 23 2018, 13:45:58)
[GCC 7.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from pyenigma import enigma
>>> from pyenigma import rotor
>>> print(rotor.ROTOR_GR_III)

    Name: III
    Model: German Railway (Rocket)
    Date: 7 February 1941
    Wiring: JVIUBHTCDYAKEQZPOSGXNRMWFL
>>>
>>> engine = enigma.Enigma(rotor.ROTOR_Reflector_A, rotor.ROTOR_I,
                                rotor.ROTOR_II, rotor.ROTOR_III, key="ABC",
                                plugs="AV BS CG DL FU HZ IN KM OW RX")
>>> print(engine)

    Reflector:
    Name: Reflector A
    Model: None
    Date: None
    Wiring: EJMZALYXVBWFCRQUONTSPIKHGD

    Rotor 1:
    Name: I
    Model: Enigma 1
    Date: 1930
    Wiring: EKMFLGDQVZNTOWYHXUSPAIBRCJ
    State: A

    Rotor 2:
    Name: II
    Model: Enigma 1
    Date: 1930
    Wiring: AJDKSIRUXBLHWTMCQGZNPYFVOE
    State: B

    Rotor 3:
    Name: III
    Model: Enigma 1
    Date: 1930
    Wiring: BDFHJLCPRTXVZNYEIWGAKMUSQO
    State: C
>>> secret = engine.encipher("Hello World")
>>> print(secret)
Qgqop Vwoxn
```

### As a program

Install pyEnigma system wide with pipx:

```bash
$ pipx install pyenigma
```

Then you can use the command line interface:

```bash
$ echo "Hello World" | enigma ABC A  I II III "AV BS CG DL FU HZ IN KM OW RX"
Qgqop Vwoxn

$ echo "Qgqop Vwoxn" | enigma ABC A  I II III "AV BS CG DL FU HZ IN KM OW RX"
Hello World
```


## License

pyEnigma is licensed under
[GNU General Public License version 3](https://www.gnu.org/licenses/gpl-3.0.html)


## Author

* [Christophe Goessen](https://github.com/cgoessen) (initial author)
* [Cédric Bonhomme](https://www.cedricbonhomme.org)
