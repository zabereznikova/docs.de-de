---
title: ICLRAssemblyIdentityManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager
helpviewer_keywords:
- ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4707f457f9d6e60717a3620c44aee7ad0c3d755c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610902"
---
# <a name="iclrassemblyidentitymanager-interface"></a>ICLRAssemblyIdentityManager-Schnittstelle
Enthält Methoden, die Kommunikation zwischen dem Host und die common Language Runtime (CLR) zu Assemblys zu unterstützen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetBindingIdentityFromFile-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|Ruft die Identität der Assembly Binden von Daten für die Assembly im angegebenen Dateipfad ab.|  
|[GetBindingIdentityFromStream-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|Ruft die kanonische Assemblyidentitätsdaten für die Assembly im angegebenen Stream.|  
|[GetCLRAssemblyReferenceList-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|Ruft eine [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) Instanz aus der angegebenen Liste von partiellen Assemblyidentitäten.|  
|[GetProbingAssembliesFromReference-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|Ruft eine [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) Enumerator für die Assemblyidentitäten aus, auf die verwiesen wird durch die Assembly mit der angegebenen Identität.|  
|[GetReferencedAssembliesFromFile-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|Ruft eine [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) Instanz, die eine Liste der Assemblys, die auf die verwiesen wird von der Assembly in den angegebenen Dateipfad enthält.|  
|[GetReferencedAssembliesFromStream-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|Ruft einen Zeiger auf ein `ICLRReferenceAssemblyEnum` -Objekt, das Assembly für die Assemblys, auf die verwiesen wird durch die Assembly im angegebenen Stream enthält.|  
|[IsStronglyNamed-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-isstronglynamed-method.md)|Ruft einen Wert, der angibt, ob die angegebene Assembly stark benannt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Verwendung `ICLRAssemblyIdentityManager` zum Abrufen von Instanzen der `ICLRAssemblyReferenceList` und Assemblyidentitäten aufzulisten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [ICLRProbingAssemblyEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
