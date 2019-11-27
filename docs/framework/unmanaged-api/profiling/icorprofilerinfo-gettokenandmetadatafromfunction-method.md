---
title: ICorProfilerInfo::GetTokenAndMetadataFromFunction-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetTokenAndMetadataFromFunction
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction
helpviewer_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction method [.NET Framework profiling]
- GetTokenAndMetadataFromFunction method [.NET Framework profiling]
ms.assetid: e525aa16-c923-4b16-833b-36f1f0dd70fc
topic_type:
- apiref
ms.openlocfilehash: b3e14230888e9bf846879d5728c2b20883fb8d53
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438743"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a>ICorProfilerInfo::GetTokenAndMetadataFromFunction-Methode
Ruft das Metadatentoken und eine Instanz der Metadatenschnittstelle ab, die für das Token für die angegebene Funktion verwendet werden können.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionId`  
 in Die ID der Funktion, für die das Metadatentoken und die Metadatenschnittstelle zu erhalten sind.  
  
 `riid`  
 in Die Verweis-ID der Metadatenschnittstelle, von der die Instanz von abgeraten werden soll.  
  
 `ppImport`  
 vorgenommen Ein Zeiger auf die Adresse der Instanz der Metadatenschnittstelle, die für das Token für die angegebene Funktion verwendet werden kann.  
  
 `pToken`  
 vorgenommen Ein Zeiger auf das Metadatentoken für die angegebene Funktion.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
