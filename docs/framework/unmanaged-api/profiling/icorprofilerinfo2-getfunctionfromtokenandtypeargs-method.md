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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7e1498ec3ce1e5258546cec8d8f8172739af6d9d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179763"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs-Methode
Ruft die `FunctionID` einer Funktion mit dem angegebenen Metadaten-Token, mit der Klasse, und `ClassID` Werte aller Typargumente.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 [in] Die ID des Moduls, in dem die Funktion befindet.  
  
 `funcDef`  
 [in] Ein `mdMethodDef` Metadatentoken, das die Funktion verweist.  
  
 `classId`  
 [in] Die ID der enthaltenden Klasse der Funktion.  
  
 `cTypeArgs`  
 [in] Die Anzahl der Typparameter für die angegebene Funktion. Dieser Wert muss 0 (null) für nicht generische Funktionen sein.  
  
 `typeArgs`  
 [in] Ein Array von `ClassID` Werten, von denen jeder ein Argument der Funktion. Der Wert des `typeArgs` kann NULL sein, wenn `cTypeArgs` auf 0 (null) festgelegt ist.  
  
 `pFunctionID`  
 [out] Ein Zeiger auf die `FunctionID` der angegebenen Funktion.  
  
## <a name="remarks"></a>Hinweise  
 Aufrufen der `GetFunctionFromTokenAndTypeArgs` -Methode mit einer `mdMethodRef` Metadaten anstelle von einer `mdMethodDef` Metadatentoken unvorhersehbare Ergebnisse haben. Aufrufer sollten Auflösen der `mdMethodRef` auf eine `mdMethodDef` bei der Übergabe.  
  
 Wenn die Funktion nicht bereits geladen ist, wird beim Aufrufen `GetFunctionFromTokenAndTypeArgs` bewirkt, dass beim Laden auftreten, handelt es sich in vielen Kontexten einen gefährlichen Vorgang. Beispielsweise kann das Aufrufen dieser Methode während des Ladens von Modulen oder Typen zu einer Endlosschleife führen wie die Laufzeit versucht, die Ladevorgänge zirkulär durchzuführen.  
  
 Im Allgemeinen die Verwendung von `GetFunctionFromTokenAndTypeArgs` wird abgeraten. Wenn der Profiler-Ereignisse für eine bestimmte Funktion interessiert sind, sollten sie speichern die `ModuleID` und `mdMethodDef` von dieser Funktion und Verwendung [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) um zu überprüfen, ob eine angegebene `FunctionID` ist mit der gewünschten Funktion.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
