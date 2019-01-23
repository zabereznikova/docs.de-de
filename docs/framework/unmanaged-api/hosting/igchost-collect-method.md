---
title: IGCHost::Collect-Methode
ms.date: 03/30/2017
api_name:
- IGCHost.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f911d99470b9870f5c42d4170a4024123c10e7f3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511120"
---
# <a name="igchostcollect-method"></a>IGCHost::Collect-Methode
Erzwingt, dass eine Collection für die angegebene Generation, unabhängig vom Status des aktuellen Garbagecollection durchgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `Generation`  
 [in] Die Objektgeneration, für den die Garbagecollection ausgeführt werden soll. Der Wert-1 gibt an, dass alle Generationen eine Garbagecollection unterzogen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** GCHost.idl, GCHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IGCHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
