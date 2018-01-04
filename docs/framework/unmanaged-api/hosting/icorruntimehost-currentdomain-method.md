---
title: ICorRuntimeHost::CurrentDomain-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.CurrentDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::CurrentDomain
helpviewer_keywords:
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
- CurrentDomain method [.NET Framework hosting]
ms.assetid: dd2afb38-675b-4c3c-a9f3-8ab3b133eb02
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ac437d924b6f5b290db117260701b554e29b6e7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostcurrentdomain-method"></a>ICorRuntimeHost::CurrentDomain-Methode
Ruft einen Schnittstellenzeiger vom Typ <xref:System.AppDomain?displayProperty=nameWithType> , die die Domäne geladen wird, für den aktuellen Thread darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CurrentDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pAppDomain`  
 [out] Ein Zeiger des Typs <xref:System.AppDomain?displayProperty=nameWithType> , die aktuelle Anwendungsdomäne des Threads darstellt. This-Zeiger typisiert ist `IUnknown`, sodass Aufrufer in der Regel aufrufen sollte `QueryInterface` um einen Zeiger vom Typ <xref:System._AppDomain>.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Der Vorgang war erfolgreich.|  
|S_FALSE|Der Vorgang konnte nicht abgeschlossen werden.|  
|E_FAIL|Ein Unbekannter, schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden kann. Nachfolgende Aufrufe hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** 1.0, 1.1  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [ICorRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
