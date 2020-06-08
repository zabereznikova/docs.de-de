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
ms.openlocfilehash: b93b27957cc715a5b4718dd9ef61cd11f4a39914
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493401"
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
|`eCurrentContext`|Gibt den Kontext des aktuellen Threads zu dem Zeitpunkt an, zu dem die Common Language Runtime (CLR) die [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) -Methode aufruft, oder den Kontext, der von der CLR in einem Aufruf der [IHostSecurityManager:: SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) -Methode angefordert wurde.|  
|`eRestrictedContext`|Gibt einen Kontext an, über den der Host niedrigere Berechtigungen aufweist, z. b. die Garbage Collector oder die Klassen-oder Modulkonstruktoren.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die CLR liefert einen der `EContextType` -Werte als Parameterwert in Aufrufen der `IHostSecurityManager::GetSecurityContext` -Methode und der- `IHostSecurityManager::SetSecurityContext` Methode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [IHostSecurityContext-Schnittstelle](ihostsecuritycontext-interface.md)
- [IHostSecurityManager-Schnittstelle](ihostsecuritymanager-interface.md)
- [Hosten von Enumerationen](hosting-enumerations.md)
