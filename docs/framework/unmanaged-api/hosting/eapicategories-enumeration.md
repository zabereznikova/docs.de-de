---
title: EApiCategories-Enumeration
ms.date: 03/30/2017
api_name:
- EApiCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EApiCategories
helpviewer_keywords:
- EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type:
- apiref
ms.openlocfilehash: f90e08373c0497201816bc7eead89b83b84be255
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726872"
---
# <a name="eapicategories-enumeration"></a>EApiCategories-Enumeration

Beschreibt die Kategorien von Funktionen, die der Host für die Ausführung in teilweise vertrauenswürdigem Code blockieren kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    eNoCategory               = 0,  
    eSynchronization          = 0x1,  
    eSharedState              = 0x2,  
    eExternalProcessMgmt      = 0x4,  
    eSelfAffectingProcessMgmt = 0x8,  
    eExternalThreading        = 0x10,  
    eSelfAffectingThreading   = 0x20,  
    eSecurityInfrastructure   = 0x40,  
    eUI                       = 0x80,  
    eMayLeakOnAbort           = 0x100,  
    eAll                      = 0x1ff  
} EHostProtectionCategories;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`eAll`|Gibt an, dass alle verwalteten Klassen und Member, die von anderen Feldern abgedeckt werden, `EApiCategories` in teilweise vertrauenswürdigem Code nicht ausgeführt werden können.|  
|`eExternalProcessMgmt`|Gibt an, dass verwaltete Klassen und Member, die das Erstellen, manipulieren und zerstören externer Prozesse zulassen, für die Ausführung in teilweise vertrauenswürdigem Code blockiert werden.|  
|`eExternalThreading`|Gibt an, dass verwaltete Klassen und Member, die das Erstellen, manipulieren und löschen externer Threads zulassen, für die Ausführung in teilweise vertrauenswürdigem Code blockiert werden.|  
|`eMayLeakOnAbort`|Gibt an, dass verwaltete Typen und Member, die ggf. beim Abbruch Speicher abbrechen können, in teilweise vertrauenswürdigem Code blockiert werden.|  
|`eNoCategory`|Gibt an, dass die Ausführung von verwalteten Code Kategorien in teilweise vertrauenswürdigem Code nicht blockiert wird.|  
|`eSecurityInfrastructure`|Gibt an, dass die Common Language Runtime (CLR)-Sicherheitsinfrastruktur nicht von teilweise vertrauenswürdigem Code verwendet werden soll.|  
|`eSelfAffectingProcessMgmt`|Gibt an, dass verwaltete Klassen und Member, deren Funktionen den gehosteten Prozess beeinflussen können, in teilweise vertrauenswürdigem Code nicht ausgeführt werden können.|  
|`eSelfAffectingThreading`|Gibt an, dass verwaltete Klassen und Member, deren Funktionen sich auf Threads im gehosteten Prozess auswirken können, in teilweise vertrauenswürdigem Code blockiert werden.|  
|`eSharedState`|Gibt an, dass verwaltete Klassen und Member, die freigegebenen Zustand verfügbar machen, in teilweise vertrauenswürdigem Code blockiert werden.|  
|`eSynchronization`|Gibt an, dass Common Language Runtime Klassen und Member, die zulassen, dass Benutzercode Sperren enthalten, in teilweise vertrauenswürdigem Code blockiert werden.|  
|`eUI`|Gibt an, dass verwaltete Klassen und Member, die eine Benutzerinteraktion zulassen oder erfordern, in teilweise vertrauenswürdigem Code blockiert werden sollen.|  
  
## <a name="remarks"></a>Hinweise  

 Die [iclrhostschutzmanager:: SetProtectedCategories](iclrhostprotectionmanager-setprotectedcategories-method.md) -Methode nimmt einen Parameter vom Typ an `EApiCategories` .  
  
 Die `EApiCategories` -Enumeration und die- `SetProtectedCategories` Methode sind direkt mit der verwalteten- <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> Klasse verknüpft. Die verwaltete Klasse wird mit der- <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> Enumeration verwendet, deren Werte direkt den `EApiCategories` Werten entsprechen, um verwaltete Typen und Member zu markieren, die Funktionen verfügbar machen, die den in beschriebenen Kategorien entsprechen `EApiCategories` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRHostProtectionManager-Schnittstelle](iclrhostprotectionmanager-interface.md)
- [Hosten von Enumerationen](hosting-enumerations.md)
