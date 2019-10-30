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
ms.openlocfilehash: 3693285e13d0650f7662e2187471027cc4c40704
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129417"
---
# <a name="einitializenewdomainflags-enumeration"></a>EInitializeNewDomainFlags-Enumeration
Ermöglicht dem Host, der Laufzeit Informationen zur Initialisierung einer Anwendungsdomäne bereitzustellen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|Keine Flags.|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|Informiert den Common Language Runtime (CLR), dass der Host keine Änderungen am Sicherheitszustand der Anwendungsdomäne in der <xref:System.AppDomainManager.InitializeNewDomain%2A>-Methode vornimmt.|  
  
## <a name="remarks"></a>Hinweise  
 Die [iclrdomainmanager:: abtappdomainmanagertype](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) -Methode nimmt einen Parameter vom Typ "`EInitializeNewDomainFlags`" an.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [SetAppDomainManagerType-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
