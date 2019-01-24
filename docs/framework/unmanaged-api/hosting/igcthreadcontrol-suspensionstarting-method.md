---
title: IGCThreadControl::SuspensionStarting-Methode
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff0c95ea79978c0b58057ec06fea231f5632c941
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702651"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a>IGCThreadControl::SuspensionStarting-Methode
Benachrichtigt den Host, dass die Laufzeit eine Threadunterbrechung für eine Garbagecollection oder einer anderen Unterbrechung beginnt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a>Hinweise  
 Darf nicht verlegt werden alle Threads, während die `SuspensionStarting` Rückruf.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IGCThreadControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
