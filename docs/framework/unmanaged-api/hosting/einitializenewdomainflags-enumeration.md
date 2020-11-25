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
ms.openlocfilehash: 8350b507609e63c060cda08514200d386c37a6b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724324"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|Keine Flags.|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|Informiert den Common Language Runtime (CLR), dass der Host keine Änderungen am Sicherheitszustand der Anwendungsdomäne in der-Methode vornimmt <xref:System.AppDomainManager.InitializeNewDomain%2A> .|  
  
## <a name="remarks"></a>Hinweise  

 Die [iclrdomainmanager:: abtappdomainmanagertype](iclrdomainmanager-setappdomainmanagertype-method.md) -Methode nimmt einen Parameter vom Typ an `EInitializeNewDomainFlags` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Enumerationen](hosting-enumerations.md)
- [SetAppDomainManagerType-Methode](iclrdomainmanager-setappdomainmanagertype-method.md)
