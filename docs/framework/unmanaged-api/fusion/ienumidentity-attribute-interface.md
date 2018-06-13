---
title: IEnumIDENTITY_ATTRIBUTE-Schnittstelle
ms.date: 03/30/2017
api_name:
- IEnumIDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords:
- IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da6462a320b1f090940473f566ade91d36e74780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431700"
---
# <a name="ienumidentityattribute-interface"></a>IEnumIDENTITY_ATTRIBUTE-Schnittstelle
Dient als Enumerator für die Attribute des Codeobjekts im aktuellen Bereich.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|Ruft einen Schnittstellenzeiger auf eine neue `IEnumIDENTITY_ATTRIBUTE` , enthält das dieselben Member wie dies `IEnumIDENTITY_ATTRIBUTE`.|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|Schreibt die Daten in die Elemente dieser `IEnumIDENTITY_ATTRIBUTE` auf den angegebenen Datenpuffer.|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|Ruft die angegebene Anzahl von Attributen, beginnend mit der aktuellen Position ab.|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|Verschiebt den Anweisungszeiger an den Anfang `IEnumIDENTITY_ATTRIBUTE`.|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|Verschiebt den Anweisungszeiger vorwärts durch die angegebene Anzahl von Elementen, die an der aktuellen Position ab.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Isolation.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Fusion-Schnittstellen](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
