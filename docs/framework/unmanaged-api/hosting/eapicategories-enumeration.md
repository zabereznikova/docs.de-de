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
ms.openlocfilehash: f25348410387a7b0e03ef897e8534336baeb126a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="eapicategories-enumeration"></a>EApiCategories-Enumeration
Beschreibt die Kategorien von Funktionen, die der Host ausführen in teilweise vertrauenswürdigem Code blockieren kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|`eAll`|Gibt an, dass alle verwalteten Klassen und Member, die von anderen abgedeckt werden `EApiCategories` Felder gehindert werden in teilweise vertrauenswürdigem Code ausgeführt wird.|  
|`eExternalProcessMgmt`|Gibt an, dass verwaltete Klassen und Member, die Erstellung, Bearbeitung und Zerstörung von externen Prozessen ermöglichen, Ausführen in teilweise vertrauenswürdigem Code gesperrt werden.|  
|`eExternalThreading`|Gibt an, dass verwaltete Klassen und Member, die die Erstellung, Bearbeitung und Zerstörung von externen Threads ermöglichen ausführen in teilweise vertrauenswürdigem Code gesperrt werden.|  
|`eMayLeakOnAbort`|Gibt an, dass verwaltete Typen und Member, die beim Abbruch zu Speicherverlusten potenziell konnte ausführen in teilweise vertrauenswürdigem Code gesperrt werden.|  
|`eNoCategory`|Gibt an, dass keine Kategorien für verwalteten Code für die Ausführung in teilweise vertrauenswürdigem Code gehindert werden.|  
|`eSecurityInfrastructure`|Gibt an, dass die common Language Runtime (CLR)-Security-Infrastruktur blockiert werden, von teilweise vertrauenswürdigem Code verwendet werden.|  
|`eSelfAffectingProcessMgmt`|Gibt an, dass verwaltete Klassen und Member, deren Funktionen gehosteten Prozess auswirken können, Ausführen in teilweise vertrauenswürdigem Code gesperrt werden.|  
|`eSelfAffectingThreading`|Gibt an, dass verwaltete Klassen und Member, deren Funktionen Threads im gehosteten Prozess auswirken können, Ausführen in teilweise vertrauenswürdigem Code gesperrt werden.|  
|`eSharedState`|Gibt an, dass verwaltete Klassen und Member, die gemeinsam verwendete Zustände verfügbar machen ausführen in teilweise vertrauenswürdigem Code gesperrt werden.|  
|`eSynchronization`|Gibt an, dass die common Language Runtime-Klassen und Member, mit die Benutzercode Sperren können ausführen in teilweise vertrauenswürdigem Code gesperrt werden.|  
|`eUI`|Gibt an, dass verwaltete Klassen und Member, die zugelassen oder erfordern menschliche Interaktion ausführen in teilweise vertrauenswürdigem Code gesperrt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Die [ICLRHostProtectionManager:: SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) Methode nimmt einen Parameter vom Typ `EApiCategories`.  
  
 Die `EApiCategories` Enumeration und die `SetProtectedCategories` Methode beziehen sich direkt auf die verwaltete <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> Klasse. Die verwaltete Klasse wird verwendet, mit der <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> Enumeration, deren Werte direkt entsprechen der `EApiCategories` Werte zu markieren von verwalteten Typen und Membern, die Funktionen, die Kategorien, die durch beschrieben entspricht verfügbar machen `EApiCategories`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRHostProtectionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
