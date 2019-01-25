---
title: EInitializeNewDomainFlags-Enumeration
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 826e02789f6940923538f3e01744345dacf4b2ba
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705283"
---
# <a name="einitializenewdomainflags-enumeration"></a>EInitializeNewDomainFlags-Enumeration
Kann der Host die Laufzeitumgebung mit Informationen zur Initialisierung einer Anwendungsdomäne bereitstellen.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|Keine Flags.|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|Informiert der common Language Runtime (CLR), dass der Host keine Änderungen an die Anwendungsdomäne, in den Sicherheitszustand vornehmen, wird die <xref:System.AppDomainManager.InitializeNewDomain%2A> Methode.|  
  
## <a name="remarks"></a>Hinweise  
 Die [ICLRDomainManager:: SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) Methode nimmt einen Parameter vom Typ `EInitializeNewDomainFlags`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [SetAppDomainManagerType-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
