---
title: ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b225b87eab6e65055618c8b6659459637e8a01be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs-Methode
Ruft die `FunctionID` einer Funktion mit dem angegebenen Metadaten-Token, mit der Klasse, und `ClassID` Werte eines beliebigen Typargumente.  
  
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
  
#### <a name="parameters"></a>Parameter  
 `moduleID`  
 [in] Die ID des Moduls, in dem die Funktion befindet.  
  
 `funcDef`  
 [in] Ein `mdMethodDef` Metadatentoken, das die Funktion verweist.  
  
 `classId`  
 [in] Die ID der enthaltenden Klasse der Funktion.  
  
 `cTypeArgs`  
 [in] Die Anzahl der Typparameter für die angegebene Funktion. Dieser Wert muss 0 (null) für nicht generische Funktionen sein.  
  
 `typeArgs`  
 [in] Ein Array von `ClassID` Werten, von denen jeder ein Argument der Funktion. Der Wert der `typeArgs` kann NULL sein, wenn `cTypeArgs` auf 0 (null) festgelegt ist.  
  
 `pFunctionID`  
 [out] Ein Zeiger auf die `FunctionID` der angegebenen Funktion.  
  
## <a name="remarks"></a>Hinweise  
 Aufrufen der `GetFunctionFromTokenAndTypeArgs` Methode mit einer `mdMethodRef` Metadaten anstelle von einer `mdMethodDef` Metadatentoken kann unvorhersehbare Folgen haben. Aufrufer sollten Auflösen der `mdMethodRef` auf eine `mdMethodDef` bei der Übergabe.  
  
 Wenn die Funktion nicht bereits geladen wurde, Aufrufen `GetFunctionFromTokenAndTypeArgs` führt dazu, dass Laden auftreten, die in vielen Kontexten einen gefährlichen Vorgang ist. Beispielsweise kann beim Aufrufen dieser Methode beim Laden von Modulen oder Typen zu einer Endlosschleife führen wie die Laufzeitumgebung versucht, Ladevorgänge zirkulär durchzuführen.  
  
 Verwenden Sie im Allgemeinen von `GetFunctionFromTokenAndTypeArgs` wird abgeraten. Wenn der Profiler-Ereignisse für eine bestimmte Funktion interessiert sind, speichern sie die `ModuleID` und `mdMethodDef` dieser Funktion und Verwendung [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) zu überprüfen, ob eine angegebenen `FunctionID` ist der die gewünschte Funktion.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
