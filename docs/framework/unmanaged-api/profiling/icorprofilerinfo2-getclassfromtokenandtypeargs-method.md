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
ms.openlocfilehash: 702c5f9f2bc08c824bdc0607741a6afd65a3e89b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497256"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetClassFromTokenAndTypeArgs-Methode
Ruft die `ClassID` eines Typs unter Verwendung des angegebenen Metadatentokens und der `ClassID` Werte von Typargumenten ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleID`  
 in Die ID des Moduls, in dem sich der Typ befindet.  
  
 `typeDef`  
 in Ein `mdTypeDef` Metadatentoken, das auf den Typ verweist.  
  
 `cTypeArgs`  
 in Die Anzahl der Typparameter für den angegebenen Typ. Dieser Wert muss für nicht generische Typen NULL sein.  
  
 `typeArgs`  
 in Ein Array von- `ClassID` Werten, von denen jeder ein Argument vom Typ ist. Der Wert von `typeArgs` kann NULL sein `cTypeArgs` , wenn auf 0 (null) festgelegt ist.  
  
 `pClassID`  
 vorgenommen Ein Zeiger auf den `ClassID` des angegebenen Typs.  
  
## <a name="remarks"></a>Bemerkungen  
 Das Aufrufen der- `GetClassFromTokenAndTypeArgs` Methode mit einem anstelle eines metadatentyps `mdTypeRef` `mdTypeDef` kann zu unvorhersehbaren Ergebnissen führen. Aufrufer sollten `mdTypeRef` bei der Übergabe in eine auflösen `mdTypeDef` .  
  
 Wenn der Typ nicht bereits geladen ist, wird beim Aufrufen von das `GetClassFromTokenAndTypeArgs` Laden von auslöst, was in vielen Kontexten eine gefährliche Operation ist. Wenn Sie diese Methode z. b. beim Laden von Modulen oder anderen Typen aufrufen, kann dies zu einer Endlosschleife führen, da die Laufzeit versucht, Vorgänge zirkulär zu laden.  
  
 Im Allgemeinen wird von der Verwendung von abgeraten `GetClassFromTokenAndTypeArgs` . Wenn Profiler an Ereignissen für einen bestimmten Typ interessiert sind, sollten Sie das `ModuleID` und `mdTypeDef` dieses Typs speichern und [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) verwenden, um zu überprüfen, ob ein angegebenes der `ClassID` gewünschten Art ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](icorprofilerinfo2-interface.md)
