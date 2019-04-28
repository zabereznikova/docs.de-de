---
title: ICLRTaskManager::GetCurrentTaskType-Methode
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTaskType
helpviewer_keywords:
- GetCurrentTaskType method [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTaskType method [.NET Framework hosting]
ms.assetid: 6b0d9259-dbe2-45bb-b34d-990f60c73424
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2963e2a31fd62470e3ed6933edb38119d286071b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763359"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a>ICLRTaskManager::GetCurrentTaskType-Methode
Ruft den Typ der Aufgabe, die gerade ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pTaskType`  
 [out] Ein Zeiger auf den Wert der [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) -Enumeration, der den Typ der Aufgabe gibt an, die gerade ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
