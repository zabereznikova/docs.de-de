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
ms.openlocfilehash: de49d66667033dfc6918b139f90cd5523661597f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134314"
---
# <a name="iassemblyname-interface"></a>IAssemblyName-Schnittstelle
Stellt Methoden zum beschreiben und arbeiten mit der eindeutigen Identität einer Assembly bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Clone-Methode](iassemblyname-clone-method.md)|Erstellt eine flache Kopie dieses `IAssemblyName` Objekts.|  
|[Finalize-Methode](iassemblyname-finalize-method.md)|Ermöglicht es diesem `IAssemblyName` Objekt, Ressourcen freizugeben und andere Bereinigungs Vorgänge durchzuführen, bevor der Dekonstruktor aufgerufen wird.|  
|[GetDisplayName-Methode](iassemblyname-getdisplayname-method.md)|Ruft den lesbaren Namen der Assembly ab, auf die von diesem `IAssemblyName` Objekt verwiesen wird.|  
|[GetName-Methode](iassemblyname-getname-method.md)|Ruft den einfachen, unverschlüsselten Namen der Assembly ab, auf die von diesem `IAssemblyName` Objekt verwiesen wird.|  
|[GetProperty-Methode](iassemblyname-getproperty-method.md)|Ruft einen Zeiger auf die Eigenschaft ab, auf die vom angegebenen `PropertyId`verwiesen wird.|  
|[GetVersion-Methode](iassemblyname-getversion-method.md)|Ruft die Versionsinformationen für die Assembly ab, auf die von diesem `IAssemblyName` Objekt verwiesen wird.|  
|[IsEqual-Methode](iassemblyname-isequal-method.md)|Bestimmt basierend auf den angegebenen Vergleichsflags, ob ein angegebenes `IAssemblyName` Objekt gleich diesem `IAssemblyName`ist.|  
|[SetProperty-Methode](iassemblyname-setproperty-method.md)|Legt den Wert der Eigenschaft fest, auf die vom angegebenen `PropertyId`verwiesen wird.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion-Schnittstellen](fusion-interfaces.md)
- [IAssemblyEnum-Schnittstelle](iassemblyenum-interface.md)
