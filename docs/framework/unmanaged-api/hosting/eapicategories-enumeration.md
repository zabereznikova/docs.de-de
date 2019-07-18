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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41513d9b6f98743bfad95e4d9606cfb4927369e6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769794"
---
# <a name="eapicategories-enumeration"></a>EApiCategories-Enumeration
Beschreibt die Kategorien von Funktionen, die der Host blockieren kann, Ausführen in teilweise vertrauenswürdigen Code.  
  
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
  
|Member|Beschreibung|  
|------------|-----------------|  
|`eAll`|Gibt an, dass alle verwalteten Klassen und Member, die von anderen abgedeckt werden `EApiCategories` Felder ausführen in teilweise vertrauenswürdigen Code blockiert werden.|  
|`eExternalProcessMgmt`|Gibt an, dass verwaltete Klassen und Member, die die Erstellung, Bearbeitung und Löschung von externen Prozessen zu ermöglichen, an der Ausführung in teilweise vertrauenswürdigem Code gehindert werden.|  
|`eExternalThreading`|Gibt an, dass verwaltete Klassen und Member, mit denen die Erstellung, Bearbeitung und Zerstörung von externen Threads blockiert werden, Ausführen in teilweise vertrauenswürdigen Code.|  
|`eMayLeakOnAbort`|Gibt an, dass verwaltete Typen und Member, die möglicherweise bei Abbruch Speicherverlust könnte blockiert werden, Ausführen in teilweise vertrauenswürdigen Code.|  
|`eNoCategory`|Gibt an, dass keine Kategorien für verwalteten Code für die Ausführung in teilweise vertrauenswürdigem Code gehindert werden.|  
|`eSecurityInfrastructure`|Gibt an, dass die common Language Runtime (CLR)-Security-Infrastruktur blockiert werden, von teilweise vertrauenswürdigem Code verwendet werden.|  
|`eSelfAffectingProcessMgmt`|Gibt an, dass verwaltete Klassen und Member, deren Funktionen gehosteten Prozess auswirken können, an der Ausführung in teilweise vertrauenswürdigem Code gehindert werden.|  
|`eSelfAffectingThreading`|Gibt an, dass verwaltete Klassen und Member, deren Funktionen Threads im Prozess gehosteten auswirken können, an der Ausführung in teilweise vertrauenswürdigem Code gehindert werden.|  
|`eSharedState`|Gibt an, dass verwaltete Klassen und Member, die gemeinsam genutzten Zustand verfügbar zu machen, an der Ausführung in teilweise vertrauenswürdigem Code gehindert werden.|  
|`eSynchronization`|Gibt an, dass die common Language Runtime-Klassen und Member, mit denen Benutzercode, der Sperren beibehält, an der Ausführung in teilweise vertrauenswürdigem Code gehindert werden.|  
|`eUI`|Gibt an, dass verwaltete Klassen und Member, die zulassen, oder erfordern menschliche Interaktion ausführen in teilweise vertrauenswürdigen Code blockiert werden.|  
  
## <a name="remarks"></a>Hinweise  
 Die [ICLRHostProtectionManager:: SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) Methode nimmt einen Parameter vom Typ `EApiCategories`.  
  
 Die `EApiCategories` Enumeration und die `SetProtectedCategories` Methode beziehen sich direkt an die verwaltete <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> Klasse. Die verwaltete Klasse wird verwendet, mit der <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> -Enumeration, deren Werte direkt entsprechen der `EApiCategories` -Werten, um verwaltete Typen und Member, die Funktionen von beschriebenen Kategorien verfügbar machen `EApiCategories`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRHostProtectionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
