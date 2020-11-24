---
title: IHostControl-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
ms.openlocfilehash: 1bffef31702aa051d9ca865b18a67ac90c00cd00
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680656"
---
# <a name="ihostcontrol-interface"></a>IHostControl-Schnittstelle

Bietet Methoden zum Konfigurieren des Ladens von Assemblys und zum bestimmen, welche Hostingschnittstellen der Host unterstützt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetHostManager-Methode](ihostcontrol-gethostmanager-method.md)|Ruft einen Schnittstellen Zeiger auf die Implementierung der-Schnittstelle des Hosts mit dem angegebenen ab `IID` .|  
|[SetAppDomainManager-Methode](ihostcontrol-setappdomainmanager-method.md)|Benachrichtigt den Host, dass eine Anwendungsdomäne erstellt wurde.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.AppDomainManager>
- [ICLRRuntimeHost-Schnittstelle](iclrruntimehost-interface.md)
- [ICLRControl-Schnittstelle](iclrcontrol-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
