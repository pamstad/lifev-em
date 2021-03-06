SET( solver_mechanics_materials_functions_HEADERS
 solver/mechanics/materials/functions/EMMaterialFunctions.hpp
 solver/mechanics/materials/functions/EMActiveStrainMaterialFunctions.hpp
 solver/mechanics/materials/functions/FunctionsActiveStrainNeoHookean.hpp
 solver/mechanics/materials/functions/FunctionsAnisotropicExponential.hpp
solver/mechanics/materials/functions/FunctionsActiveStrainIsotropicExponential.hpp
solver/mechanics/materials/functions/FunctionsActiveStrainAnisotropicExponential.hpp
solver/mechanics/materials/functions/FunctionsActiveStrainShearExponential.hpp
 solver/mechanics/materials/functions/FunctionsIsotropicExponential.hpp
 solver/mechanics/materials/functions/FunctionsLinearizedNeoHookean.hpp
 solver/mechanics/materials/functions/FunctionsList.hpp
 solver/mechanics/materials/functions/FunctionsNeoHookean.hpp
 solver/mechanics/materials/functions/FunctionsOrthotropicFung.hpp
 solver/mechanics/materials/functions/FunctionsShearExponential.hpp
 solver/mechanics/materials/functions/FunctionsSimpleActiveStress.hpp
 solver/mechanics/materials/functions/FunctionsOrthotropicActiveStress.hpp
 solver/mechanics/materials/functions/FunctionsVolumetric.hpp
 solver/mechanics/materials/functions/FunctionsMooneyRivlin.hpp
 solver/mechanics/materials/functions/FunctionsMooneyRivlinCompact.hpp
 CACHE INTERNAL "")

SET( solver_mechanics_materials_functions_SOURCES
# solver/mechanics/materials/EMMaterial.cpp
 CACHE INTERNAL "")

SET(LOCAL_HEADERS)
FOREACH(INC ${solver_mechanics_materials_functions_HEADERS})
  STRING(REPLACE "solver/mechanics/materials/functions/" "" LOCAL_INC ${INC})
  SET(LOCAL_HEADERS ${LOCAL_HEADERS} ${LOCAL_INC})
ENDFOREACH()

INSTALL(
  FILES ${LOCAL_HEADERS}
  DESTINATION "${${PROJECT_NAME}_INSTALL_INCLUDE_DIR}/lifev/em/solver/mechanics/materials/functions/"
  COMPONENT ${PACKAGE_NAME}
)
