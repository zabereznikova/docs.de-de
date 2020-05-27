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
ms.openlocfilehash: 31be0525c637e50c1161129277d651b56dadfaa3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006752"
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
|`dwAppDomainId`|Ein eindeutiger Bezeichner für das-Element `IStream` , das durch einen Rückruf der [IHostAssemblyStore::P rovidemodule](ihostassemblystore-providemodule-method.md) -Methode zurückgegeben wird, aus der das Modul, auf das verwiesen wird, geladen werden soll.|  
|`lpAssemblyIdentity`|Ein eindeutiger Bezeichner der Assembly, die das Modul enthält, auf das verwiesen wird.|  
|`lpModuleName`|Der Name des Moduls, auf das verwiesen wird.|  
  
## <a name="remarks"></a>Hinweise  
 `ModuleBindInfo`wird als Parameter an übergeben `IHostAssemblyStore::ProvideModule` . Der Host stellt den eindeutigen Bezeichner `dwAppDomainId` für die Common Language Runtime (CLR) bereit. Nachdem ein Aufrufen der [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md) -Methode zurückgegeben wurde, verwendet die Common Language Runtime den Bezeichner, um zu bestimmen, ob der Inhalt der `IStream` zugeordnet wurde. Wenn dies der Fall ist, lädt die Laufzeit die vorhandene Kopie, anstatt den Stream neu zuzuordnen. Die Laufzeit verwendet diesen Bezeichner auch als Suchschlüssel für Streams, die von Aufrufen der-Methode zurückgegeben werden `IHostAssemblyStore::ProvideAssembly` . Daher muss der Bezeichner für Modul Anforderungen und für Assemblyanforderungen eindeutig sein.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. idl  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Strukturen](hosting-structures.md)
- [AssemblyBindInfo-Struktur](assemblybindinfo-structure.md)
- [ICLRAssemblyIdentityManager-Schnittstelle](iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList-Schnittstelle](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager-Schnittstelle](ihostassemblymanager-interface.md)
