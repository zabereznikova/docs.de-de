---
title: ComCallUnmarshal-Co-Klasse
ms.date: 03/30/2017
api_name:
- ComCallUnmarshal Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ComCallUnmarshal
helpviewer_keywords:
- ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f17a88a90905006432ae8c5dc040277124c947b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697289"
---
# <a name="comcallunmarshal-coclass"></a>ComCallUnmarshal-Co-Klasse
Stellt Schnittstellen zum Verwalten von das Marshalling der Schnittstellenzeiger bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a>Schnittstellen  
  
|Interface|Beschreibung|  
|---------------|-----------------|  
|`IMarshal`|Stellt Methoden zum Erstellen, initialisieren und verwalten einen Proxy in einen Clientprozess.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.idl  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Co-Klassen](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
