---
title: ICLRAssemblyIdentityManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager
helpviewer_keywords: ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8d7fe632941c4cf0c20841ece390d2f41f28337d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyidentitymanager-interface"></a>ICLRAssemblyIdentityManager-Schnittstelle
Enthält Methoden, die Kommunikation zwischen dem Host und die common Language Runtime (CLR) über Assemblys zu unterstützen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetBindingIdentityFromFile-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|Ruft die Identität der Assembly Binden von Daten für die Assembly im angegebenen Dateipfad ab.|  
|[GetBindingIdentityFromStream-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|Ruft die Identitätsdaten kanonische Assembly für die Assembly im angegebenen Stream.|  
|[GetCLRAssemblyReferenceList-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|Ruft eine [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) Instanz aus der angegebenen Liste von partiellen Assemblyidentitäten.|  
|[GetProbingAssembliesFromReference-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|Ruft eine [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) Enumerator für die Assemblyidentitäten verweist auf die Assembly mit der angegebenen Identität.|  
|[GetReferencedAssembliesFromFile-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|Ruft eine [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) -Instanz, eine Liste der Assemblys enthält, auf die Assembly auf der angegebene Pfad verweist.|  
|[GetReferencedAssembliesFromStream-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|Ruft einen Zeiger auf ein `ICLRReferenceAssemblyEnum` Objekt, das für die Assemblys, die von der Assembly im angegebenen Stream Assemblyidentitätsdaten enthält.|  
|[IsStronglyNamed-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|Ruft einen Wert, der angibt, ob die angegebene Assembly stark benannt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Verwendung `ICLRAssemblyIdentityManager` zum Abrufen von Instanzen von `ICLRAssemblyReferenceList` und Assemblyidentitäten aufzulisten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [ICLRProbingAssemblyEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
