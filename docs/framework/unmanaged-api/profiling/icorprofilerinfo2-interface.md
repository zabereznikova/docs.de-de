---
title: ICorProfilerInfo2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2
helpviewer_keywords:
- ICorProfilerInfo2 interface [.NET Framework profiling]
ms.assetid: 91bd49b6-4d12-494f-a8f1-2f251e8c65e3
topic_type:
- apiref
ms.openlocfilehash: fdac9eedb0ae442d6dd2646859cab13398020a87
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449774"
---
# <a name="icorprofilerinfo2-interface"></a>ICorProfilerInfo2-Schnittstelle
Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information. The `ICorProfilerInfo2` interface is an extension of the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface. That is, it provides new methods supported in the .NET Framework version 2.0 and later versions.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[DoStackSnapshot-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)|Walks the stack of the specified thread to report managed call frames to the profiler.|  
|[EnumModuleFrozenObjects-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)|Gets an enumerator that allows iteration over the frozen objects in the specified module.|  
|[GetAppDomainStaticAddress-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getappdomainstaticaddress-method.md)|Gets the address of the specified application domain-static field that is in the scope of the specified application domain.|  
|[GetArrayObjectInfo-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getarrayobjectinfo-method.md)|Gets detailed information about an array object.|  
|[GetBoxClassLayout-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getboxclasslayout-method.md)|Gets information about the class layout for a specified value type that is boxed.|  
|[GetClassFromTokenAndTypeArgs-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)|Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.|  
|[GetClassIDInfo2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)|Gets the parent module of the specified generic class, the metadata token for the class, the `ClassID` of its parent class, and the `ClassID` for each type argument, if present, of the class.|  
|[GetClassLayout-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclasslayout-method.md)|Ruft aus dem Arbeitsspeicher Informationen über das Layout der Felder ab, die durch die angegebene Klasse definiert sind . Das heißt, diese Methode ruft die Offsets der Felder der Klasse ab.|  
|[GetCodeInfo2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)|Ruft die Wertebereiche von nativem Code ab, der der angegebenen `FunctionID` zugeordnet ist.|  
|[GetContextStaticAddress-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcontextstaticaddress-method.md)|Gets the address of the specified context-static field that is in the scope of the specified context.|  
|[GetFunctionFromTokenAndTypeArgs-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)|Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.|  
|[GetFunctionInfo2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)|Ruft die übergeordnete Klasse, das Metadatentoken und die `ClassID` jedes Typarguments einer Funktion ab, falls vorhanden.|  
|[GetGenerationBounds-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md)|Gets the memory regions (the segments of the heap) that make up the generations of the garbage-collected heap.|  
|[GetNotifiedExceptionClauseInfo-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)|Gets the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run or has just been run.|  
|[GetObjectGeneration-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md)|Gets the segment of the heap that contains the specified object.|  
|[GetRVAStaticAddress-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getrvastaticaddress-method.md)|Gets the address of the specified relative virtual address (RVA)-static field.|  
|[GetStaticFieldInfo-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstaticfieldinfo-method.md)|Gets the scope in which the specified field is static.|  
|[GetStringLayout-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md)|Ruft Informationen zum Layout eines Zeichenfolgenobjekts ab.|  
|[GetThreadAppDomain-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)|Gets the ID of the application domain in which the specified thread is currently executing code.|  
|[GetThreadStaticAddress-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md)|Gets the address of the specified thread-static field that is in the scope of the specified thread.|  
|[SetEnterLeaveFunctionHooks2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)|Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.|  
  
## <a name="remarks"></a>Hinweise  
 A profiler calls a method in the `ICorProfilerInfo2` interface to communicate with the CLR to control event monitoring and request information.  
  
 The methods of the `ICorProfilerInfo2` interface are implemented by the CLR using the free-threaded model. Jede Methode gibt ein HRESULT zurück, um einen Erfolg oder einen Fehler anzugeben. Eine Liste möglicher Rückgabecodes finden Sie in der Datei "CorError.h".  
  
 The CLR passes an `ICorProfilerInfo2` interface to each code profiler during initialization, using the profiler's implementation of [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). A code profiler can then call methods of the `ICorProfilerInfo2` interface to get information about managed code being executed under the control of the CLR.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
