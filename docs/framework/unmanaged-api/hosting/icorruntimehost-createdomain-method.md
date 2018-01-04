---
title: ICorRuntimeHost::CreateDomain-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.CreateDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fe0adad8397f42716368691abbb1d1c303fced97
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostcreatedomain-method"></a>ICorRuntimeHost::CreateDomain-Methode
Erstellt eine Anwendungsdomäne. Der Aufrufer empfängt einen Schnittstellenzeiger vom Typ <xref:System._AppDomain> mit einer Instanz des Typs <xref:System.AppDomain?displayProperty=nameWithType>.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pwzFriendlyName`  
 [in] Ein optionaler Parameter verwendet, um der Domäne einen Anzeigenamen zuweisen. Dieser aussagekräftige Name kann in Benutzeroberflächen wie Debuggern zur Kennzeichnung der Domäne angezeigt werden.  
  
 `pIdentityArray`  
 [in] Ein optionales Array von Zeigern auf `IIdentity` Instanzen, die Beweise Sicherheitsrichtlinie darstellen herstellen einen Berechtigungssatz zugeordnet. Ein `IIdentity` -Objekt abgerufen werden kann, durch Aufrufen der [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) Methode.  
  
 `pAppDomain`  
 [out] Einen Schnittstellenzeiger vom Typ <xref:System._AppDomain> mit einer Instanz von <xref:System.AppDomain?displayProperty=nameWithType> , die verwendet werden kann, um der Domäne weiter zu steuern.  
  
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
