---
title: ICLRHostProtectionManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager
helpviewer_keywords:
- ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type:
- apiref
ms.openlocfilehash: e8ead998907d55b0bfbf82e5f6f4e7c504f657ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714158"
---
# <a name="iclrhostprotectionmanager-interface"></a>ICLRHostProtectionManager-Schnittstelle

Ermöglicht es dem Host, bestimmte verwaltete Klassen, Methoden, Eigenschaften und Felder von der Ausführung in teilweise vertrauenswürdigem Code zu blockieren.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[SetEagerSerializeGrantSets](iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|Bietet eine Garantie, dass bestimmte seltene Racebedingungen, die zu schwerwiegenden Common Language Runtime (CLR) führen können, nie auftreten.|  
|[SetProtectedCategories-Methode](iclrhostprotectionmanager-setprotectedcategories-method.md)|Gibt die Kategorien verwalteter Typen und Member an, deren Ausführung in teilweise vertrauenswürdigem Code blockiert werden soll.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [EApiCategories-Enumeration](eapicategories-enumeration.md)
- [ICLRControl-Schnittstelle](iclrcontrol-interface.md)
