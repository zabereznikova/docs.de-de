---
title: IGCHost2-Schnittstelle
ms.date: 03/30/2017
api_name:
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
ms.openlocfilehash: 7529ecd215d74eb0eedbec8b90eba367ed20d56f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687742"
---
# <a name="igchost2-interface"></a>IGCHost2-Schnittstelle

Bietet Methoden zum Abrufen von Informationen über das Garbage Collection System und zum Steuern einiger Aspekte von Garbage Collection.  
  
> [!NOTE]
> Für eine neue Entwicklung empfiehlt es sich, stattdessen die [ICLRGCManager2](iclrgcmanager2-interface.md) -Schnittstelle zu verwenden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[SetGCStartupLimitsEx-Methode](igchost2-setgcstartuplimitsex-method.md)|Legt die Segmentgröße und die maximale Größe für die Generation 0 fest. Aktiviert die Generation 0 und die Segment Größen größer als `DWORD` .|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Gchost. idl, gchost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Schnittstellen](hosting-interfaces.md)
- [CLR-Hostingschnittstellen](clr-hosting-interfaces.md)
- [CorRuntimeHost-Co-Klasse](corruntimehost-coclass.md)
