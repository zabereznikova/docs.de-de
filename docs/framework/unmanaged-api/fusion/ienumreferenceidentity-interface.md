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
ms.openlocfilehash: 1305b9ebe3cd87ba002ee87610ff309d015a44e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131747"
---
# <a name="ienumreferenceidentity-interface"></a>IEnumReferenceIdentity-Schnittstelle
Dient als Enumerator für eine Auflistung von `IReferenceIdentity`-Objekten.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|Ruft einen Schnittstellen Zeiger auf einen neuen `IEnumReferenceIdentity` ab, der dieselben Member wie diese `IEnumReferenceIdentity`enthält.|  
|`IEnumReferenceIdentity::Next`|Ruft die angegebene Anzahl von `IReferenceIdentity` Objekten ab der aktuellen Position ab.|  
|`IEnumReferenceIdentity::Reset`|Verschiebt den Anweisungs Zeiger an den Anfang dieses `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Skip`|Verschiebt den Anweisungs Zeiger um die angegebene Anzahl von Elementen, beginnend an der aktuellen Position.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Isolation. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion-Schnittstellen](fusion-interfaces.md)
- [IReferenceIdentity-Schnittstelle](ireferenceidentity-interface.md)
