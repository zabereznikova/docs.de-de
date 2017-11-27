---
title: IDefinitionIdentity-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDefinitionIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IDefinitionIdentity
helpviewer_keywords: IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a63436f107a2604fd5620854339447a4af254e52
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="idefinitionidentity-interface"></a>IDefinitionIdentity-Schnittstelle
Stellt die eindeutige Signatur des Codes, der die Anwendung im aktuellen Bereich definiert.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|Ruft einen Schnittstellenzeiger auf eine neue `IDefinitionIdentity` -Objekt, das mit dieser identisch ist `IDefinitionIdentity`, abgesehen von den Änderungen des angegebenen Attributs.|  
|`IDefinitionIdentity::EnumAttributes`|Ruft einen Schnittstellenzeiger auf eine [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) Objekt, das die mit diesem verknüpften Attribute enthält `IDefinitionIdentity`.|  
|`IDefinitionIdentity::GetAttribute`|Ruft den Wert des Attributs mit dem angegebenen Namen im angegebenen Namespace an.|  
|`IDefinitionIdentity::SetAttribute`|Legt das Attribut mit dem angegebenen Namen im angegebenen Namespace mit dem angegebenen Wert fest.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Isolation.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Fusion-Schnittstellen](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
