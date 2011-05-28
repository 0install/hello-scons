from SCons import SConsign
import os

# By default, SCons resets all environment variables. This means that
# instead of compiling against the library versions you chose, it will
# build against whatever happens to be the default on the system today.
# It also breaks when plash is used.
# This makes the current environment available to the build:
env = Environment(ENV = os.environ)
Export('env')

# Build in build directory
# Note: for more complex projects, you may want to turn duplicate on
# (see the scons manual for details)
SConscript(os.path.join(os.environ['SRCDIR'], 'src', 'SConscript'))
