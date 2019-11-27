---
title: ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type:
- apiref
ms.openlocfilehash: 41021a524142afe34727584265aee578e31a64b3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433209"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs-Methode
Ruft den `FunctionID` einer Funktion mit dem angegebenen Metadatentoken, der enthaltenden Klasse und `ClassID` Werten beliebiger Typargumente ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleID`  
 in Die ID des Moduls, in dem sich die Funktion befindet.  
  
 `funcDef`  
 in Ein `mdMethodDef` Metadatentoken, das auf die Funktion verweist.  
  
 `classId`  
 in Die ID der enthaltenden Klasse der Funktion.  
  
 `cTypeArgs`  
 in Die Anzahl der Typparameter für die angegebene Funktion. Dieser Wert muss für nicht generische Funktionen 0 (null) sein.  
  
 `typeArgs`  
 in Ein Array von `ClassID` Werten, von denen jeder ein Argument der Funktion ist. Der Wert `typeArgs` kann NULL sein, wenn `cTypeArgs` auf NULL festgelegt ist.  
  
 `pFunctionID`  
 vorgenommen Ein Zeiger auf den `FunctionID` der angegebenen Funktion.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie die `GetFunctionFromTokenAndTypeArgs`-Methode mit einem `mdMethodRef`-Metadaten anstelle eines `mdMethodDef` Metadatentokens aufrufen, kann dies zu unvorhersehbaren Ergebnissen führen. Aufrufer sollten die `mdMethodRef` bei der Übergabe in eine `mdMethodDef` auflösen.  
  
 Wenn die Funktion nicht bereits geladen ist, wird beim Aufrufen von `GetFunctionFromTokenAndTypeArgs` das Laden ausgelöst. Dies ist ein gefährlicher Vorgang in vielen Kontexten. Wenn Sie diese Methode beispielsweise beim Laden von Modulen oder Typen aufrufen, kann dies zu einer Endlosschleife führen, da die Laufzeit versucht, Vorgänge zirkulär zu laden.  
  
 Im Allgemeinen wird die Verwendung von `GetFunctionFromTokenAndTypeArgs` davon abgeraten. Wenn Profiler an Ereignissen für eine bestimmte Funktion interessiert sind, sollten Sie die `ModuleID` und `mdMethodDef` dieser Funktion Speichern und [ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) verwenden, um zu überprüfen, ob ein bestimmter `FunctionID` der der gewünschten Funktion entspricht.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
