---
title: EContextType-Enumeration
ms.date: 03/30/2017
api_name:
- EContextType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EContextType
helpviewer_keywords:
- EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type:
- apiref
ms.openlocfilehash: 5e82f542bdc364a52fc558e582134a7d8d554ec3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131147"
---
# <a name="econtexttype-enumeration"></a>EContextType-Enumeration
Beschreibt den Sicherheitskontext des aktuell ausgeführten Threads.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`eCurrentContext`|Gibt den Kontext des aktuellen Threads zu dem Zeitpunkt an, zu dem die Common Language Runtime (CLR) die [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) -Methode aufruft, oder den Kontext, der von der CLR in einem Aufruf von [IHostSecurityManager:: SetSecurityContext angefordert wird. ](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)-Methode.|  
|`eRestrictedContext`|Gibt einen Kontext an, über den der Host niedrigere Berechtigungen aufweist, z. b. die Garbage Collector oder die Klassen-oder Modulkonstruktoren.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR stellt einen der `EContextType` Werte als Parameterwert in Aufrufen der Methoden `IHostSecurityManager::GetSecurityContext` und `IHostSecurityManager::SetSecurityContext` bereit.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IHostSecurityContext-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [IHostSecurityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
