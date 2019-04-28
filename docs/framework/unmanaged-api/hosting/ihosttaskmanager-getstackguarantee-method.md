---
title: IHostTaskManager::GetStackGuarantee-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetStackGuarantee
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetStackGuarantee
helpviewer_keywords:
- GetStackGuarantee method [.NET Framework hosting]
- IHostTaskManager::GetStackGuarantee method [.NET Framework hosting]
ms.assetid: 8176d732-c25c-4520-811d-e3310f339947
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea1c1f998febccbc80fb10cef5a8dfd229e1987e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789401"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a>IHostTaskManager::GetStackGuarantee-Methode
Ruft die Menge an Stapelspeicher, der garantiert verfügbar, sobald ein Stack-Vorgang abgeschlossen wird, aber vor dem Endtag eines Prozesses ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pGuarantee`  
 [out] Ein Zeiger auf die Anzahl der Bytes, die verfügbar sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
