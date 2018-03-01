---
title: AssemblyBindInfo-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- AssemblyBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyBindInfo
helpviewer_keywords:
- AssemblyBindInfo structure [.NET Framework hosting]
ms.assetid: 6fc01e98-c2e7-49de-ab9f-95937cc89017
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bdf76b95e80d5d4d96d2b5ed8236018147167905
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="assemblybindinfo-structure"></a>AssemblyBindInfo-Struktur
Enthält ausführliche Informationen über die referenzierte Assembly.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`dwAppDomainId`|Ein eindeutiger Bezeichner für die `IStream` zurückgegeben, die durch einen Aufruf von [IHostAssemblyStore:: ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), von dem die referenzierte Assembly geladen werden.|  
|`lpReferencedIdentity`|Ein eindeutiger Bezeichner für die Assembly verwiesen wird.|  
|`lpPostPolicyIdentity`|Der Bezeichner für die referenzierte Assembly nach der Anwendung aller Bindung Richtlinie-Werte.|  
|`ePolicyLevel`|Eines der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, die angeben, welche Versionsrichtlinien ggf. auf die referenzierte Assembly angewendet werden soll.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host stellt den eindeutigen Bezeichner `dwAppDomainId` für die common Language Runtime (CLR). Nach einem Aufruf von `IHostAssemblyStore::ProvideAssembly` zurückgibt, die Laufzeit den Bezeichner verwendet, um zu bestimmen, ob der Inhalt von der `IStream` zugeordnet wurde. Wenn dies der Fall ist, lädt die Common Language Runtime den Stream neu zuzuordnen, statt die vorhandene Kopie. Die Common Language Runtime verwendet diesen Bezeichner auch als Suchschlüssel für Streams aus zurückgegebenen Aufrufe von [IHostAssemblyStore:: ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md). Aus diesem Grund muss der Bezeichner für Anforderungen zum modulimport und für Anforderungen Assembly eindeutig sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.idl  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten von Strukturen](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [ICLRAssemblyIdentityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [IHostAssemblyStore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [ModuleBindInfo-Struktur](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
