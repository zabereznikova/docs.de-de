---
title: ICorProfilerInfo4::GetCodeInfo3-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetCodeInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetCodeInfo3
helpviewer_keywords:
- GetCodeInfo3 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetCodeInfo3 method [.NET Framework profiling]
ms.assetid: bb8c105e-4d9a-4684-8c05-ed6909cc1b8c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cb067d16ef7f8177f979a083707f8c6ef36750c0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145807"
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a>ICorProfilerInfo4::GetCodeInfo3-Methode
Ruft die Erweiterungen des systemeigenen Codes ab, die der JIT-kompilierten Version der angegebenen Funktion zugeordnet sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionID`  
 [in] Die ID der Funktion, der der systemeigene Code zugeordnet ist.  
  
 `reJitId`  
 [in] Die Identität der erneut JIT-kompilierten Funktion.  
  
 `cCodeInfos`  
 [in] Die Größe des `codeInfos`-Arrays.  
  
 `pcCodeInfos`  
 [out] Ein Zeiger auf die Gesamtanzahl der [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) verfügbar sind.  
  
 `codeInfos`  
 [out] Ein vom Aufrufer bereitgestellter Puffer. Nach dem Ausführen enthält die Methode ein Array aus `COR_PRF_CODE_INFO`-Strukturen, von denen jede einen Block des systemeigenen Codes beschreibt.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetCodeInfo3` -Methode ist vergleichbar mit [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md), außer dass der erneut JIT-kompilierte ID der Funktion abgerufen werden sollen, die die angegebene IP-Adresse enthält.  
  
> [!NOTE]
>  `GetCodeInfo3` kann eine Garbagecollection auslösen, während [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) nicht der Fall ist. Weitere Informationen finden Sie unter den [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT.  
  
 Die Wertebereiche sind in aufsteigender Reihenfolge des CIL-Offsets (Common Intermediate Language) sortiert.  
  
 Nach dem `GetCodeInfo3` zurückgegeben wird, müssen Sie sicherstellen, dass die `codeInfos` -Puffer groß genug, um alle enthalten war die [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) Strukturen. Vergleichen Sie hierzu den Wert von `cCodeInfos` mit dem Wert des `cchName`-Parameters. Wenn `cCodeInfos` dividiert durch die Größe einer [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) -Struktur kleiner ist als `pcCodeInfos`, weisen Sie einen größeren `codeInfos` -Puffer zu, aktualisieren `cCodeInfos` mit der neuen Größe, und rufen `GetCodeInfo3` erneut aus.  
  
 Alternativ können Sie zuerst `GetCodeInfo3` mit einem `codeInfos`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln. Sie können dann Festlegen der `codeInfos` -Puffers auf den Rückgabewert `pcCodeInfos`multipliziert mit der Größe der eine [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) -Struktur, und rufen `GetCodeInfo3` erneut.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetCodeInfo2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)
- [ICorProfilerInfo4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
