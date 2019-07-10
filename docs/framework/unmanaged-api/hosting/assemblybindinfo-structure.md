---
title: AssemblyBindInfo-Struktur
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f4cb71e5ac0afe19e865ffca6fe578ad08f3162
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773871"
---
# <a name="assemblybindinfo-structure"></a>AssemblyBindInfo-Struktur
Enthält ausführliche Informationen über die referenzierte Assembly.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
|`lpPostPolicyIdentity`|Der Bezeichner für die referenzierte Assembly nach der Anwendung der Bindung Richtlinienwerte.|  
|`ePolicyLevel`|Eines der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, die angeben, welche versionsverwaltung-Richtlinien, sofern vorhanden, für die referenzierte Assembly angewendet werden sollen.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host stellt den eindeutigen Bezeichner `dwAppDomainId` für die common Language Runtime (CLR). Nach einem Aufruf von `IHostAssemblyStore::ProvideAssembly` zurückgegeben wird, die Runtime den Bezeichner verwendet, um zu bestimmen, ob der Inhalt des der `IStream` zugeordnet wurde. Wenn dies der Fall ist, lädt die Runtime den Stream neu zuzuordnen, anstatt die vorhandene Kopie. Die Common Language Runtime verwendet diesen Bezeichner auch als Suchschlüssel für Streams aus zurückgegebenen Aufrufe von [IHostAssemblyStore:: ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md). Aus diesem Grund muss der Bezeichner für Anforderungen zum modulimport und Anforderungen der Assembly eindeutig sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.idl  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Strukturen](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [ICLRAssemblyIdentityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [ModuleBindInfo-Struktur](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
