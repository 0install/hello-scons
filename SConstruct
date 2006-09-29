from SCons import SConsign
import os

# By default, SCons resets all environment variables. This means that
# instead of compiling against the library versions you chose, it will
# build against whatever happens to be the default on the system today.
# It also breaks when plash is used.
# This makes the current environment available to the build:
env = Environment(ENV = os.environ)
Export('env')

build_dir = ARGUMENTS.get('build_dir', 'Hello-scons/build')
print "Bulding in", build_dir

# Store signature information in build directory
SConsign.File(build_dir + os.sep)

# Build in build directory
# Note: for more complex projects, you may want to turn duplicate on
# (see the scons manual for details)
SConscript('src/SConscript',
	build_dir = build_dir,
	duplicate = 0)
