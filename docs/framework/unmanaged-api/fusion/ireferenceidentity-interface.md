---
title: IReferenceIdentity-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IReferenceIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IReferenceIdentity
helpviewer_keywords: IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 35c6152836adf02d541bacd149ed9ac053765ba6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ireferenceidentity-interface"></a>IReferenceIdentity-Schnittstelle
Stellt einen Verweis auf die eindeutige Signatur des ein Codeobjekt dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|Ruft einen Schnittstellenzeiger auf eine neue `IReferenceIdentity` -Instanz, die mit dieser identisch ist `IReferenceIdentity`, abgesehen von den Änderungen des angegebenen Attributs.|  
|`IReferenceIdentity::EnumAttributes`|Ruft einen Schnittstellenzeiger auf eine `IEnumIDENTITY_ATTRIBUTE` -Instanz, die mit diesem verknüpften Attribute enthält `IReferenceIdentity`.|  
|`IReferenceIdentity::GetAttribute`|Ruft den Wert des Attributs im angegebenen Namespace, mit dem angegebenen Namen ab.|  
|`IReferenceIdentity::SetAttribute`|Legt das Attribut mit dem angegebenen Namespace und dem angegebenen Namen auf den angegebenen Wert fest.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Isolation.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Fusion-Schnittstellen](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [IEnumIDENTITY_ATTRIBUTE-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
