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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aee9b986c1e26c1b2e34dac7151a00172451bbad
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796552"
---
# <a name="iassemblyname-interface"></a>IAssemblyName-Schnittstelle
Stellt Methoden zum beschreiben und arbeiten mit der eindeutigen Identität einer Assembly bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Clone-Methode](iassemblyname-clone-method.md)|Erstellt eine flache Kopie des `IAssemblyName` -Objekts.|  
|[Finalize-Methode](iassemblyname-finalize-method.md)|Ermöglicht es `IAssemblyName` diesem Objekt, Ressourcen freizugeben und andere Bereinigungs Vorgänge durchzuführen, bevor der Dekonstruktor aufgerufen wird.|  
|[GetDisplayName-Methode](iassemblyname-getdisplayname-method.md)|Ruft den lesbaren Namen der Assembly ab, auf die von `IAssemblyName` diesem-Objekt verwiesen wird.|  
|[GetName-Methode](iassemblyname-getname-method.md)|Ruft den einfachen, unverschlüsselten Namen der Assembly ab, auf die `IAssemblyName` von diesem-Objekt verwiesen wird.|  
|[GetProperty-Methode](iassemblyname-getproperty-method.md)|Ruft einen Zeiger auf die Eigenschaft ab, auf die `PropertyId`vom angegebenen verwiesen wird.|  
|[GetVersion-Methode](iassemblyname-getversion-method.md)|Ruft die Versionsinformationen für die Assembly ab, auf `IAssemblyName` die von diesem-Objekt verwiesen wird.|  
|[IsEqual-Methode](iassemblyname-isequal-method.md)|Bestimmt basierend auf den `IAssemblyName` angegebenen Vergleichsflags, `IAssemblyName`ob ein angegebenes Objekt gleich diesem ist.|  
|[SetProperty-Methode](iassemblyname-setproperty-method.md)|Legt den Wert der Eigenschaft fest, auf die vom `PropertyId`angegebenen verwiesen wird.|  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion-Schnittstellen](fusion-interfaces.md)
- [IAssemblyEnum-Schnittstelle](iassemblyenum-interface.md)
