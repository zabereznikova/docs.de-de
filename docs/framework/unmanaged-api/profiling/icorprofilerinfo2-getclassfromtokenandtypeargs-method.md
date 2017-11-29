---
title: ICorProfilerInfo2::GetClassFromTokenAndTypeArgs-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 332be5616ac11fc89df8c8d54aa5c0cbc49491ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetClassFromTokenAndTypeArgs-Methode
Ruft die `ClassID` eines Typs mit dem angegebenen Metadaten-Token und die `ClassID` Werte eines beliebigen Typargumente.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
#### <a name="parameters"></a>Parameter  
 `moduleID`  
 [in] Die ID des Moduls, in dem der Typ befindet.  
  
 `typeDef`  
 [in] Ein `mdTypeDef` Metadatentoken, das auf den Typ verweist.  
  
 `cTypeArgs`  
 [in] Die Anzahl der Typparameter für den angegebenen Typ. Dieser Wert muss 0 (null) für nicht generische Typen.  
  
 `typeArgs`  
 [in] Ein Array von `ClassID` Werten, von denen jeder ein Argument des Typs. Der Wert der `typeArgs` kann NULL sein, wenn `cTypeArgs` auf 0 (null) festgelegt ist.  
  
 `pClassID`  
 [out] Ein Zeiger auf die `ClassID` des angegebenen Typs.  
  
## <a name="remarks"></a>Hinweise  
 Aufrufen der `GetClassFromTokenAndTypeArgs` Methode mit einer `mdTypeRef` anstelle von ein `mdTypeDef` Metadatentoken kann unvorhersehbare Folgen haben; Aufrufer sollte sich Auflösen der `mdTypeRef` auf eine `mdTypeDef` bei der Übergabe.  
  
 Wenn der Typ nicht bereits geladen wurde, Aufrufen von `GetClassFromTokenAndTypeArgs` wird geladen, die in vielen Kontexten einen gefährlichen Vorgang wird ausgelöst. Beispielsweise kann beim Aufrufen dieser Methode beim Laden von Modulen oder andere Typen zu einer Endlosschleife führen wie die Laufzeitumgebung versucht, Ladevorgänge zirkulär durchzuführen.  
  
 Verwenden Sie im Allgemeinen von `GetClassFromTokenAndTypeArgs` wird abgeraten. Wenn der Profiler-Ereignisse für einen bestimmten Typ interessiert sind, speichern sie die `ModuleID` und `mdTypeDef` dieses Typs, und verwenden [ICorProfilerInfo2:: Getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) zu überprüfen, ob eine angegebenen `ClassID` ist, mit der die gewünschte Typ.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
