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
ms.openlocfilehash: dbb3ac150ebfe9fe3698427d8bb2bfb3e3347c07
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796465"
---
# <a name="ienumidentity_attribute-interface"></a>IEnumIDENTITY_ATTRIBUTE-Schnittstelle
Dient als Enumerator für die Attribute des Code-Objekts im aktuellen Gültigkeitsbereich.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|Ruft einen Schnittstellen Zeiger auf einen neuen `IEnumIDENTITY_ATTRIBUTE` ab, der dieselben Member wie dieses `IEnumIDENTITY_ATTRIBUTE`enthält.|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|Schreibt die Daten, die in den Elementen dieses `IEnumIDENTITY_ATTRIBUTE` enthalten sind, in den angegebenen Datenpuffer.|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|Ruft die angegebene Anzahl von Attributen ab der aktuellen Position ab.|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|Verschiebt den Anweisungs Zeiger an den Anfang dieses `IEnumIDENTITY_ATTRIBUTE`.|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|Verschiebt den Anweisungs Zeiger um die angegebene Anzahl von Elementen, beginnend an der aktuellen Position.|  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Isolation. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion-Schnittstellen](fusion-interfaces.md)
