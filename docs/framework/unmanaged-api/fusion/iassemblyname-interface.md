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
ms.openlocfilehash: 22276e543e8eeb9c6cf9aeee7a9af92c503d3a7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549014"
---
# <a name="iassemblyname-interface"></a>IAssemblyName-Schnittstelle
Stellt Methoden zum Beschreiben von und Arbeiten mit der Identität einer Assembly eindeutig.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Clone-Methode](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-clone-method.md)|Erstellt eine flache Kopie dieses `IAssemblyName` Objekt.|  
|[Finalize-Methode](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-finalize-method.md)|Dadurch können `IAssemblyName` Objekt, das Freigeben von Ressourcen und andere Bereinigungen durchzuführen, bevor der Destruktor aufgerufen wird.|  
|[GetDisplayName-Methode](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md)|Ruft den lesbaren Namen der Assembly verwiesen wird, von diesem `IAssemblyName` Objekt.|  
|[GetName-Methode](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getname-method.md)|Ruft ab, die einfache nicht verschlüsselte Name der Assembly verwiesen wird, von diesem `IAssemblyName` Objekt.|  
|[GetProperty-Methode](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getproperty-method.md)|Ruft einen Zeiger auf die verwiesen wird, mit der angegebenen Eigenschaft `PropertyId`.|  
|[GetVersion-Methode](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getversion-method.md)|Ruft die Versionsinformationen für die Assembly verwiesen wird, von diesem `IAssemblyName` Objekt.|  
|[IsEqual-Methode](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md)|Bestimmt, ob ein angegebener `IAssemblyName` Objekt gleich diesem ist `IAssemblyName`basierend auf den angegebenen Vergleichsflags.|  
|[SetProperty-Methode](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-setproperty-method.md)|Legt den Wert der Eigenschaft verwiesen wird, mit dem angegebenen `PropertyId`.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Fusion-Schnittstellen](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [IAssemblyEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
