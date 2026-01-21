import os

env = Environment()

# Detect Homebrew prefix (Apple Silicon: /opt/homebrew, Intel: /usr/local)
homebrew_prefix = os.environ.get('HOMEBREW_PREFIX', '/opt/homebrew')

includes = '''
              .
              ./cost-model/include
              ./cost-model/include/base
              ./cost-model/include/tools
              ./cost-model/include/user-api
              ./cost-model/include/dataflow-analysis
              ./cost-model/include/dataflow-specification-language
              ./cost-model/include/design-space-exploration
              ./cost-model/include/cost-analysis
              ./cost-model/include/abstract-hardware-model
              ./cost-model/src
'''

# Add Homebrew include path for Boost headers
env.Append(CPPPATH=[homebrew_prefix + '/include'])
# Add Homebrew library path for Boost libraries
env.Append(LIBPATH=[homebrew_prefix + '/lib'])

env.Append(CXXFLAGS=['-std=c++17'])
env.Append(LIBS=['boost_program_options', 'boost_filesystem'])

env.Append(CPPPATH = Split(includes))
#env.Program("maestro-top.cpp")
#env.Program('maestro', ['maestro-top.cpp', 'lib/src/maestro_v3.cpp', 'lib/src/BASE_base-objects.cpp' ])
env.Program('maestro', ['maestro-top.cpp', 'cost-model/src/BASE_base-objects.cpp' ])
#env.Library('maestro', ['maestro-top.cpp', 'lib/src/maestro_v3.cpp', 'lib/src/BASE_base-objects.cpp' ])

