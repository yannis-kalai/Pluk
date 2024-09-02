# Pluk

What is Pluk?
Pluk Language is a general-purpose programming language. It is independent of any particular operating system and designed to be used on various software and hardware platforms (e.g. Windows, UNIX).

Pluk is an object-oriented interpreter (a ‘lazy’ compiler). Syntactically it is similar to C++. Like C++, it contains all means of procedure-oriented programming, which allows the ‘old school’ programmers to switch to object-oriented programming pretty easily. Frankly, the concept of object-oriented programming, in its ‘pure’ form, sometimes requires unnecessary and non-productive operations, such as development of classes, whose only purpose being to introduce procedures into the language.

Since the very beginning of its creation, Pluk has been intended to be a mixed (Pluk / C++) programming environment. Pluk could be used as an embedded interpreter: the main program is written in C++, but some ancillary functions (e.g. references to database) are executed by the Pluk machine called from the main program. To address this issue, there is a universal mechanism in Pluk for attaching functions and methods of 5 ++. This mechanism enables the user to create classes whose methods are written partly in C++ and partly in Pluk. It is also possible to create an associated C++ class. Each object of this class will be associated with an object of a Pluk class. This allows hiding part of code and data in the C++ class, leaving just the interface at the Pluk level. It is possible to create Pluk objects in and invoke Pluk methods from code written in C++. In this case, if Pluk objects support redefined operators, the latter will be invoked ‘transparently’ through the C++ program.

Since Pluk is a high-level language interpreter, it imposes certain limitations on the use of some C++ methods. It is not possible, for example, to manipulate computer memory from the Pluk level, just in contrast to the ‘high-level assembler’ (a nickname of C++, given for its ability to access computer resourses directly). This limitation (it can be easily bypassed by means of associated C++ class), however, spares the programmer such tasks as freeing allocated memory, maintaining the integrity of array and string boundaries, etc.

An important feature that distinguishes Pluk from C++ is non-type variables. Naturally, at a certain point in time, a variable takes the type of its value (for example, a number, string, vector, object). However, the name associated with the variable does not have type. If, for instance, the variable b initially contained a numerical value 5, its type was int. If later it were assigned a string "hello", its type would be String. So, at the stage of coding, the interpreter deals with an abstract variable of no particular type. The type check takes place later, at runtime. For example, an attempt to add the variable b equaling "hello" to the variable a equaling 5 will throw an error at runtime.

Another feature that differs Pluk from C++ is that a function is a variable that contains a string of a special type: an interpretable string. Class methods, although not regular variables, also contain interpretable strings. It allows handling both functions and methods as regular variables of string type. The programmer can treat an interpretable string as a conventional string: find sub-string, replace / delete sub-string, merge strings, etc. Pluk does not support overloaded global functions (coinciding by names and differing by types of parameters) since a function is a variable and should be accessed by name. A variable name does not contain any auxiliary names that define types of parameters since the variable that presently contains a function may contain something else in the future (a number, for example). Class methods do carry additional information that determines the types of parameters; hence, Pluk supports overloaded methods. The type of a parameter can be determined only at runtime since just at that time the relationship between a method and its invocation point could be revealed.


# Historical overview
Pluk language was developed in the collaboration of Laboratory of Medical Imaging of the Nuclear Physics Institute and Institute of Physical and Chemical Biology of Moscow State University in the 1994-1995. The original goal of project was creation of platform for analysis experimental data in the biophysical research. Experience of authors in analysis of experimental data and algorithm prototyping was formulated in the following desiderata.

# Desiderata
Language has to be fast interpreter which allows convenient manipulation of code and data from the integrated development environment (IDE). The IDE has to include integrated debugger
Language has to support object-oriented and procedural programing styles
The stop-on-error condition has to preserve the current data.
The structure of data (class specification) can be changed (e.g. new data fields could be added/removed to/from the class specification) runtime. The existed at the moment of changes variables must be modified in accordance with new specification. The content of variables, which is compatible with new specification, must be preserved.
The code can be changed any time and calculation must continue with new code
Object-oriented architecture has to support multiple inheritances. The structure of inheritances could be modified runtime.
Language has to support dynamic typing (typeless variables) as well as overloaded methods discriminated by parameter types.
Simple and transparent interface to the C/C++ libraries
Easy way to move prototype algorithms to production: Simple interface to create classes where methods are partially implemented on Pluk and partially implemented on C/C++. Support a simple way to move Pluk methods on C/C++ level
Basic mathematical library has to include state-of-art deconvolution of experimental curves on sum of exponents, sum of Gaussians etc.
Later this list was expanded by:
Seamless call of remote procedure and converting local objects into the proxy for remote one, in order to support distributed calculation. The conversion to the remote objects and back must be supported runtime to simplify debugging of the program.
Automatic generation of second order languages to generate as declarative specification as simplified scripts on base of Backus-Naur-specifications.
Automatically generate mapping of object-oriented data scheme into relational database with generation appropriate declarative specification
Automatically generate code to decompose object-oriented OSQL queries into multiple standard SQL queries as well as a code for assembly-disassembly Pluk object into relational database
Automatic synchronization of objects in the program memory with relational database presentation.

# On basis of Pluk platform were developed:
Medical image analysis stations (Ultrasound3D, Multivox2D/Multivod3D), PACS servers and medical automated information systems (AIS) (1994-2004). This packages were installed in more than 60 hospitals ( http://www.multivox.ru, http://techheim.com/kor/main/index.html )
Mathematical libraries and utilities for biophysical data analysis (1994-2015) (http://pluk.mpi-cbg.de/projects/fitmodel  http://pluk.mpi-cbg.de/projects/fitmodelpde2 )
Fluorescence microscopy image analysis software MotionTracking (2001-2024) ( http://motiontracking.mpi-cbg.de/get/ )

