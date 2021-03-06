add_swift_library(swiftSIL STATIC
  AbstractionPattern.cpp
  BasicBlockUtils.cpp
  Bridging.cpp
  Dominance.cpp
  DynamicCasts.cpp
  InstructionUtils.cpp
  Linker.cpp
  LoopInfo.cpp
  OptimizationRemark.cpp
  PrettyStackTrace.cpp
  Projection.cpp
  SIL.cpp
  SILArgument.cpp
  SILBasicBlock.cpp
  SILBuilder.cpp
  SILCoverageMap.cpp
  SILDebugScope.cpp
  SILDeclRef.cpp
  SILDefaultWitnessTable.cpp
  SILFunction.cpp
  SILFunctionType.cpp
  SILGlobalVariable.cpp
  SILInstruction.cpp
  SILInstructions.cpp
  SILLocation.cpp
  SILModule.cpp
  SILOpenedArchetypesTracker.cpp
  SILPrinter.cpp
  SILSuccessor.cpp
  SILType.cpp
  SILValue.cpp
  SILVerifier.cpp
  SILOwnershipVerifier.cpp
  SILVTable.cpp
  SILWitnessTable.cpp
  TypeLowering.cpp
  ValueOwnershipKindClassifier.cpp
  LINK_LIBRARIES
    swiftSerialization
    swiftSema
)

# intrinsics_gen is the LLVM tablegen target that generates the include files
# where intrinsics and attributes are declared. swiftSIL depends on these
# headers.
# For more information see the comment at the top of lib/CMakeLists.txt.
add_dependencies(swiftSIL intrinsics_gen clang-tablegen-targets)
