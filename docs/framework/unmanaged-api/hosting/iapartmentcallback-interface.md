---
title: IApartmentCallback-Schnittstelle
ms.date: 03/30/2017
api_name:
- IApartmentCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IApartmentCallback
helpviewer_keywords:
- IApartmentCallback interface [.NET Framework hosting]
ms.assetid: 57c33c58-bf0b-4533-b569-e6a682d02cba
topic_type:
- apiref
ms.openlocfilehash: 0f38314df766b74164bf5e98d9b2153d2dddbcc1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721737"
---
# <a name="iapartmentcallback-interface"></a>IApartmentCallback-Schnittstelle

Stellt Methoden bereit, um Rückrufe in einem Apartment zu erstellen. Ein *Apartment* ist ein logischer Container innerhalb eines Prozesses für-Objekte, die die gleichen Thread Zugriffs Anforderungen haben.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[DoCallback-Methode](iapartmentcallback-docallback-method.md)|Führt die angegebene Funktion in einem Apartment aus.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Schnittstellen](hosting-interfaces.md)
