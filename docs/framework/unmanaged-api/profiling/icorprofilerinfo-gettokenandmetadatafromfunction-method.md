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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fb81972a7f52889d10a59cd5cd9ea0e8e1e3e571
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492880"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a>ICorProfilerInfo::GetTokenAndMetadataFromFunction-Methode
Ruft das Metadatentoken und eine Instanz der Metadaten-Schnittstelle, die für die angegebene Funktion anhand des Tokens verwendet werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion für die das Metadatentoken und die Metadaten-Schnittstelle abgerufen werden soll.  
  
 `riid`  
 [in] Die Referenz-ID der Metadatenschnittstelle, von der Instanz abgerufen.  
  
 `ppImport`  
 [out] Ein Zeiger auf die Adresse der Instanz der Schnittstelle, die für die angegebene Funktion anhand des Tokens verwendet werden kann.  
  
 `pToken`  
 [out] Ein Zeiger auf das Metadatentoken für die angegebene Funktion.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
