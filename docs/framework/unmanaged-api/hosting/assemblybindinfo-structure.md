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
ms.openlocfilehash: 615637813b08629aaea74b23fa2737f52d61bafb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616917"
---
# <a name="assemblybindinfo-structure"></a>AssemblyBindInfo-Struktur
Bietet ausführliche Informationen über die Assembly, auf die verwiesen wird.  
  
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
|`dwAppDomainId`|Ein eindeutiger Bezeichner für das `IStream` , das durch einen [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md)zurückgegeben wird, aus dem die referenzierte Assembly geladen werden soll.|  
|`lpReferencedIdentity`|Eine eindeutige ID für die Assembly, auf die verwiesen wird.|  
|`lpPostPolicyIdentity`|Der Bezeichner für die Assembly, auf die verwiesen wird, nach der Anwendung von Bindungs Richtlinien Werten.|  
|`ePolicyLevel`|Einer der [EPolicyAction](epolicyaction-enumeration.md) -Werte, die angeben, welche Versions Verwaltungsrichtlinien ggf. auf die Assembly angewendet werden sollen, auf die verwiesen wird.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host stellt den eindeutigen Bezeichner `dwAppDomainId` für die Common Language Runtime (CLR) bereit. Nachdem ein Rückruf `IHostAssemblyStore::ProvideAssembly` von zurückgegeben wurde, verwendet die Common Language Runtime den Bezeichner, um zu bestimmen, ob der Inhalt des `IStream` zugeordnet wurde. Wenn dies der Fall ist, lädt die Laufzeit die vorhandene Kopie, anstatt den Stream neu zuzuordnen. Die Laufzeit verwendet diesen Bezeichner auch als Suchschlüssel für Streams, die von Aufrufen an [IHostAssemblyStore::P rovidemodule](ihostassemblystore-providemodule-method.md)zurückgegeben werden. Daher muss der Bezeichner für Modul Anforderungen und für Assemblyanforderungen eindeutig sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. idl  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hostingstrukturen](hosting-structures.md)
- [ICLRAssemblyIdentityManager-Schnittstelle](iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList-Schnittstelle](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager-Schnittstelle](ihostassemblymanager-interface.md)
- [IHostAssemblyStore-Schnittstelle](ihostassemblystore-interface.md)
- [ModuleBindInfo-Struktur](modulebindinfo-structure.md)
