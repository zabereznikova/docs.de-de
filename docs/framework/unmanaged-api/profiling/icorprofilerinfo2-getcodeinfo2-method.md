---
title: ICorProfilerInfo2::GetCodeInfo2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetCodeInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetCodeInfo2
helpviewer_keywords:
- ICorProfilerInfo2::GetCodeInfo2 method [.NET Framework profiling]
- GetCodeInfo2 method [.NET Framework profiling]
ms.assetid: 532da6ee-7f0a-401b-a61e-fc47ec235d2e
topic_type:
- apiref
ms.openlocfilehash: 5149e3fab023de42d03673ec5d3e5ae888a9ed5a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433285"
---
# <a name="icorprofilerinfo2getcodeinfo2-method"></a>ICorProfilerInfo2::GetCodeInfo2-Methode
Ruft die Wertebereiche von nativem Code ab, der der angegebenen `FunctionID` zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCodeInfo2(  
    [in]  FunctionID functionID,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionID`  
 [in] Die ID der Funktion, der der systemeigene Code zugeordnet ist.  
  
 `cCodeInfos`  
 [in] Die Größe des `codeInfos`-Arrays.  
  
 `pcCodeInfos`  
 [out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.  
  
 `codeInfos`  
 [out] Ein vom Aufrufer bereitgestellter Puffer. Nach dem Ausführen enthält die Methode ein Array aus `COR_PRF_CODE_INFO`-Strukturen, von denen jede einen Block des systemeigenen Codes beschreibt.  
  
## <a name="remarks"></a>Hinweise  
 Die Wertebereiche sind in aufsteigender Reihenfolge des MSIL-Offsets (Microsoft Intermediate Language (MSIL) sortiert.  
  
 Nachdem `GetCodeInfo2` ausgeführt ist, müssen Sie sich vergewissern, dass der `codeInfos`-Puffer groß genug war, um alle `COR_PRF_CODE_INFO`-Strukturen zu enthalten. Vergleichen Sie hierzu den Wert von `cCodeInfos` mit dem Wert des `cchName`-Parameters. Wenn `cCodeInfos` dividiert durch die Größe einer `COR_PRF_CODE_INFO`-Struktur kleiner ist als `pcCodeInfos`, weisen Sie einen größeren `codeInfos`-Puffer zu, aktualisieren Sie `cCodeInfos` mit der neuen Größe, und rufen `GetCodeInfo2` erneut auf.  
  
 Alternativ können Sie zuerst `GetCodeInfo2` mit einem `codeInfos`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln. Sie können dann die Größe des `codeInfos`-Puffers auf den von `pcCodeInfos` zurückgegebenen Wert multipliziert mit der Größe einer `COR_PRF_CODE_INFO`-Struktur festlegen und `GetCodeInfo2` erneut aufrufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetCodeInfo3-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)
- [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
