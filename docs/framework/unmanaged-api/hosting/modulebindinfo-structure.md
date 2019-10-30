---
title: ModuleBindInfo-Struktur
ms.date: 03/30/2017
api_name:
- ModuleBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ModuleBindInfo
helpviewer_keywords:
- ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type:
- apiref
ms.openlocfilehash: ae40d8adaae70ccff6e8058858a506267d58873f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133747"
---
# <a name="modulebindinfo-structure"></a>ModuleBindInfo-Struktur
Bietet ausführliche Informationen über das Modul, auf das verwiesen wird, und die Assembly, die es enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`dwAppDomainId`|Ein eindeutiger Bezeichner für die `IStream`, die durch einen [IHostAssemblyStore::P rovidemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) -Methode zurückgegeben wird, aus der das Modul, auf das verwiesen wird, geladen werden soll.|  
|`lpAssemblyIdentity`|Ein eindeutiger Bezeichner der Assembly, die das Modul enthält, auf das verwiesen wird.|  
|`lpModuleName`|Der Name des Moduls, auf das verwiesen wird.|  
  
## <a name="remarks"></a>Hinweise  
 `ModuleBindInfo` wird als Parameter an `IHostAssemblyStore::ProvideModule`übergeben. Der Host stellt den eindeutigen Bezeichner `dwAppDomainId` für die Common Language Runtime (CLR) bereit. Nachdem ein Aufrufen der [IHostAssemblyStore::P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) -Methode zurückgegeben wurde, verwendet die Common Language Runtime den Bezeichner, um zu bestimmen, ob die Inhalte der `IStream` zugeordnet wurden. Wenn dies der Fall ist, lädt die Laufzeit die vorhandene Kopie, anstatt den Stream neu zuzuordnen. Die Laufzeit verwendet diesen Bezeichner auch als Suchschlüssel für Streams, die von Aufrufen der `IHostAssemblyStore::ProvideAssembly`-Methode zurückgegeben werden. Daher muss der Bezeichner für Modul Anforderungen und für Assemblyanforderungen eindeutig sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. idl  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Strukturen](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [AssemblyBindInfo-Struktur](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [ICLRAssemblyIdentityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
