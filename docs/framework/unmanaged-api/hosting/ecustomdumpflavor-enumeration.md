---
title: ECustomDumpFlavor-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ECustomDumpFlavor
api_location: mscoree.dll
api_type: COM
f1_keywords: ECustomDumpFlavor
helpviewer_keywords: ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a063dd6b50566d0bff393853015efc6a15f8cee1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ecustomdumpflavor-enumeration"></a>ECustomDumpFlavor-Enumeration
Enthält Werte, die angeben, die eine benutzerdefinierte Teilmenge eines Heaps einzuschließenden Elemente zu speichern, beim Melden von Fehlern.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|Gibt an, dass das benutzerdefinierte Heap Speicherabbild als Minidumps gestartet und zusätzliche Daten, die von einer angegebenen eingeschlossen werden sollen [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) Instanzen derselben Methode zu übergeben.|  
|`DUMP_FLAVOR_NonHeapCLRState`|Gibt an, dass das benutzerdefinierte Heap Speicherabbild alle Laufzeitzustand Daten sammelt, die nicht dynamisch zugeordnet wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Einen Parameter vom Typ `ECustomDumpFlavor` wird zum Übergeben der [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ECustomDumpItemKind-Enumeration](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [ICLRErrorReportingManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
