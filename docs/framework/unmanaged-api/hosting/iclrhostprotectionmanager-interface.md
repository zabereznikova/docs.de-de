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
ms.openlocfilehash: 7b1fc70380fff3c551c56043f49c2deda507e366
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703844"
---
# <a name="iclrhostprotectionmanager-interface"></a>ICLRHostProtectionManager-Schnittstelle
Ermöglicht es dem Host, bestimmte verwaltete Klassen, Methoden, Eigenschaften und Felder von der Ausführung in teilweise vertrauenswürdigem Code zu blockieren.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[SetEagerSerializeGrantSets](iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|Bietet eine Garantie, dass bestimmte seltene Racebedingungen, die zu schwerwiegenden Common Language Runtime (CLR) führen können, nie auftreten.|  
|[SetProtectedCategories-Methode](iclrhostprotectionmanager-setprotectedcategories-method.md)|Gibt die Kategorien verwalteter Typen und Member an, deren Ausführung in teilweise vertrauenswürdigem Code blockiert werden soll.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EApiCategories-Enumeration](eapicategories-enumeration.md)
- [ICLRControl-Schnittstelle](iclrcontrol-interface.md)
