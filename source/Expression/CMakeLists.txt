if(NOT LLDB_BUILT_STANDALONE)
  set(tablegen_deps intrinsics_gen)
endif()

add_lldb_library(lldbExpression
  DiagnosticManager.cpp
  DWARFExpression.cpp
  Expression.cpp
  ExpressionSourceCode.cpp
  ExpressionVariable.cpp
  FunctionCaller.cpp
  IRDynamicChecks.cpp
  IRExecutionUnit.cpp
  IRInterpreter.cpp
  IRMemoryMap.cpp
  LLVMUserExpression.cpp
  Materializer.cpp
  REPL.cpp
  UserExpression.cpp
  UtilityFunction.cpp

  DEPENDS
  ${tablegen_deps}

  LINK_LIBS
    lldbCore
    lldbHost
    lldbInterpreter
    lldbSymbol
    lldbTarget
    lldbUtility
    lldbPluginExpressionParserClang
    lldbPluginExpressionParserSwift
  LINK_COMPONENTS
    Core
    ExecutionEngine
    Support
  )
