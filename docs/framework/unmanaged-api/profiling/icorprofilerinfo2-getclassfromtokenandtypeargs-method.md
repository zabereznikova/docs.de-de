---
title: ICorProfilerInfo2::GetClassFromTokenAndTypeArgs-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d4d5ec9119cdcf89e507f133288f569e6fb37ea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072518"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetClassFromTokenAndTypeArgs-Methode
Ruft die `ClassID` eines Typs mit dem Token der angegebenen Metadaten und die `ClassID` Werte aller Typargumente.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleID`  
 [in] Die ID des Moduls, in dem der Typ befindet.  
  
 `typeDef`  
 [in] Ein `mdTypeDef` Metadatentoken, das den Typ verweist.  
  
 `cTypeArgs`  
 [in] Die Anzahl der Typparameter für den angegebenen Typ. Dieser Wert muss 0 (null) für nicht generische Typen sein.  
  
 `typeArgs`  
 [in] Ein Array von `ClassID` Werten, von denen jeder ein Argument des Typs. Der Wert des `typeArgs` kann NULL sein, wenn `cTypeArgs` auf 0 (null) festgelegt ist.  
  
 `pClassID`  
 [out] Ein Zeiger auf die `ClassID` des angegebenen Typs.  
  
## <a name="remarks"></a>Hinweise  
 Aufrufen der `GetClassFromTokenAndTypeArgs` -Methode mit einer `mdTypeRef` anstelle von eine `mdTypeDef` Metadatentoken unvorhersehbare Ergebnisse haben; der Aufrufer sollte sich Auflösen der `mdTypeRef` auf ein `mdTypeDef` bei der Übergabe.  
  
 Wenn der Typ nicht bereits geladen ist, wird beim Aufrufen `GetClassFromTokenAndTypeArgs` löst laden, die in vielen Kontexten einen gefährlichen Vorgang ist. Beispielsweise kann das Aufrufen dieser Methode während des Ladens von Modulen oder andere Typen zu einer Endlosschleife führen wie die Laufzeit versucht, die Ladevorgänge zirkulär durchzuführen.  
  
 Im Allgemeinen die Verwendung von `GetClassFromTokenAndTypeArgs` wird abgeraten. Wenn Profiler Ereignissen für einen bestimmten Typ interessiert sind, sollten sie Speichern der `ModuleID` und `mdTypeDef` dieses Typs, und verwenden [ICorProfilerInfo2:: Getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) überprüfen, ob eine angegebene `ClassID` ist, die von der gewünschte Typ.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
