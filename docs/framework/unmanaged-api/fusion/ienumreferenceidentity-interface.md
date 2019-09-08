---
title: IEnumReferenceIdentity-Schnittstelle
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c5d4bc1fa82f7623168050f4ee36f0ea3cd171e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796434"
---
# <a name="ienumreferenceidentity-interface"></a>IEnumReferenceIdentity-Schnittstelle
Dient als Enumerator für eine Auflistung von `IReferenceIdentity` -Objekten.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|Ruft einen Schnittstellen Zeiger auf einen neuen `IEnumReferenceIdentity` ab, der dieselben Member wie dieses `IEnumReferenceIdentity`enthält.|  
|`IEnumReferenceIdentity::Next`|Ruft die angegebene Anzahl von `IReferenceIdentity` -Objekten ab der aktuellen Position ab.|  
|`IEnumReferenceIdentity::Reset`|Verschiebt den Anweisungs Zeiger an den Anfang dieses `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Skip`|Verschiebt den Anweisungs Zeiger um die angegebene Anzahl von Elementen, beginnend an der aktuellen Position.|  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Isolation. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion-Schnittstellen](fusion-interfaces.md)
- [IReferenceIdentity-Schnittstelle](ireferenceidentity-interface.md)
