---
title: IAssemblyName-Schnittstelle
ms.date: 03/30/2017
api_name:
- IAssemblyName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName
helpviewer_keywords:
- IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type:
- apiref
ms.openlocfilehash: f6feed9f59715f9a2801cd3a2a99a087957d4377
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715068"
---
# <a name="iassemblyname-interface"></a>IAssemblyName-Schnittstelle

Stellt Methoden zum beschreiben und arbeiten mit der eindeutigen Identität einer Assembly bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Clone-Methode](iassemblyname-clone-method.md)|Erstellt eine flache Kopie des- `IAssemblyName` Objekts.|  
|[Finalize-Methode](iassemblyname-finalize-method.md)|Ermöglicht es diesem `IAssemblyName` Objekt, Ressourcen freizugeben und andere Bereinigungs Vorgänge durchzuführen, bevor der Dekonstruktor aufgerufen wird.|  
|[GetDisplayName-Methode](iassemblyname-getdisplayname-method.md)|Ruft den lesbaren Namen der Assembly ab, auf die von diesem-Objekt verwiesen wird `IAssemblyName` .|  
|[GetName-Methode](iassemblyname-getname-method.md)|Ruft den einfachen, unverschlüsselten Namen der Assembly ab, auf die von diesem-Objekt verwiesen wird `IAssemblyName` .|  
|[GetProperty-Methode](iassemblyname-getproperty-method.md)|Ruft einen Zeiger auf die Eigenschaft ab, auf die vom angegebenen verwiesen wird `PropertyId` .|  
|[GetVersion-Methode](iassemblyname-getversion-method.md)|Ruft die Versionsinformationen für die Assembly ab, auf die von diesem-Objekt verwiesen wird `IAssemblyName` .|  
|[IsEqual-Methode](iassemblyname-isequal-method.md)|Bestimmt `IAssemblyName` `IAssemblyName` basierend auf den angegebenen Vergleichsflags, ob ein angegebenes Objekt gleich diesem ist.|  
|[SetProperty-Methode](iassemblyname-setproperty-method.md)|Legt den Wert der Eigenschaft fest, auf die vom angegebenen verwiesen wird `PropertyId` .|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Fusion-Schnittstellen](fusion-interfaces.md)
- [IAssemblyEnum-Schnittstelle](iassemblyenum-interface.md)
