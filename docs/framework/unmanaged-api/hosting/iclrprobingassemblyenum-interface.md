---
title: ICLRProbingAssemblyEnum-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRProbingAssemblyEnum
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRProbingAssemblyEnum
helpviewer_keywords: ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 31f3bfcb2b70bda952f0e4bb43dd8b0067e6ef1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrprobingassemblyenum-interface"></a>ICLRProbingAssemblyEnum-Schnittstelle
Enthält Methoden, mit denen der Host zum Abrufen der gesuchten Identitäten einer Assembly mit der Assembly aneinander gehängt Identitätsinformationen, die intern für die common Language Runtime (CLR), ohne zu erstellen oder zu verstehen, die Identität an.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Get-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|Ruft die Identität der Assembly am angegebenen Index ab.|  
  
## <a name="remarks"></a>Hinweise  
 Methoden, z. B. [ICLRAssemblyIdentityManager:: GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) Zurückgeben einer `ICLRProbingAssemblyEnum` Instanz.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRAssemblyIdentityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
