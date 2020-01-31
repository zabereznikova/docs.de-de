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
ms.openlocfilehash: e0663ff122397ba639a0a219e513be2f3f0cbbef
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862762"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetClassFromTokenAndTypeArgs-Methode
Ruft den `ClassID` eines Typs unter Verwendung des angegebenen Metadatentokens und der `ClassID` Werte beliebiger Typargumente ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a>Parameters  
 `moduleID`  
 in Die ID des Moduls, in dem sich der Typ befindet.  
  
 `typeDef`  
 in Ein `mdTypeDef` Metadatentoken, das auf den Typ verweist.  
  
 `cTypeArgs`  
 in Die Anzahl der Typparameter für den angegebenen Typ. Dieser Wert muss für nicht generische Typen NULL sein.  
  
 `typeArgs`  
 in Ein Array von `ClassID` Werten, von denen jeder ein Argument vom Typ ist. Der Wert `typeArgs` kann NULL sein, wenn `cTypeArgs` auf NULL festgelegt ist.  
  
 `pClassID`  
 vorgenommen Ein Zeiger auf den `ClassID` des angegebenen Typs.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie die `GetClassFromTokenAndTypeArgs`-Methode mit einem `mdTypeRef` anstelle eines `mdTypeDef` Metadatentokens aufrufen, kann dies zu unvorhersehbaren Ergebnissen führen. Aufrufer sollten die `mdTypeRef` bei der Übergabe in eine `mdTypeDef` auflösen.  
  
 Wenn der Typ nicht bereits geladen ist, wird beim Aufrufen von `GetClassFromTokenAndTypeArgs` das Laden auslöst, was in vielen Kontexten eine gefährliche Operation ist. Wenn Sie diese Methode z. b. beim Laden von Modulen oder anderen Typen aufrufen, kann dies zu einer Endlosschleife führen, da die Laufzeit versucht, Vorgänge zirkulär zu laden.  
  
 Im Allgemeinen wird die Verwendung von `GetClassFromTokenAndTypeArgs` davon abgeraten. Wenn Profiler an Ereignissen für einen bestimmten Typ interessiert sind, sollten Sie die `ModuleID` und `mdTypeDef` dieses Typs speichern und [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) verwenden, um zu überprüfen, ob ein bestimmtes `ClassID` der gewünschte Typ ist.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](icorprofilerinfo2-interface.md)
