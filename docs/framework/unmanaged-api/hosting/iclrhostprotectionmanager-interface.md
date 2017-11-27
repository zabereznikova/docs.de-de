---
title: ICLRHostProtectionManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostProtectionManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostProtectionManager
helpviewer_keywords: ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c88279eb26b819adaaaf86dcf59105c6ac728017
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrhostprotectionmanager-interface"></a>ICLRHostProtectionManager-Schnittstelle
Ermöglicht es dem Host zum Blockieren von bestimmten verwaltete Klassen, Methoden, Eigenschaften und Felder in teilweise vertrauenswürdigem Code ausgeführt wird.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[SetEagerSerializeGrantSets](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|Gewährleistet, dass bestimmte seltenen Racebedingungen, die schwerwiegende common Language Runtime (CLR)-Fehler führen können, niemals auftreten.|  
|[SetProtectedCategories-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|Gibt die Kategorien von verwalteten Typen und Membern, die ausführen in teilweise vertrauenswürdigem Code gesperrt werden sollen.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [EApiCategories-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
