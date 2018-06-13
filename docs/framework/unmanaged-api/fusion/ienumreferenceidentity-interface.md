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
ms.openlocfilehash: 4ebc9fe36955bac8b93ec95e9a55fc8ac1197d9a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429120"
---
# <a name="ienumreferenceidentity-interface"></a>IEnumReferenceIdentity-Schnittstelle
Dient als Enumerator für eine Auflistung von `IReferenceIdentity` Objekte.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|Ruft einen Schnittstellenzeiger auf eine neue `IEnumReferenceIdentity` , enthält das dieselben Member wie dies `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Next`|Ruft die angegebene Anzahl von `IReferenceIdentity` Objekte, die an der aktuellen Position ab.|  
|`IEnumReferenceIdentity::Reset`|Verschiebt den Anweisungszeiger an den Anfang `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Skip`|Verschiebt den Anweisungszeiger vorwärts durch die angegebene Anzahl von Elementen, die an der aktuellen Position ab.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Isolation.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Fusion-Schnittstellen](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [IReferenceIdentity-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
