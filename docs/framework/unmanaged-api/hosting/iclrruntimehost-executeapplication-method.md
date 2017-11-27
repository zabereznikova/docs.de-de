---
title: ICLRRuntimeHost::ExecuteApplication-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.ExecuteApplication
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3b43365ad208dae5b28b31cf494de37ca670d791
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimehostexecuteapplication-method"></a>ICLRRuntimeHost::ExecuteApplication-Methode
In Szenarien für die ClickOnce-Manifest-basiertes verwendet, an die Anwendung in einer neuen Domäne aktiviert werden. Weitere Informationen zu diesen Szenarien finden Sie unter [ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pwzAppFullName`  
 [in] Der vollständige Name der Anwendung, entsprechend der Definition für <xref:System.ApplicationIdentity>.  
  
 `dwManifestPaths`  
 [in] Die Anzahl der Zeichenfolgen die `ppwzManifestPaths` Array.  
  
 `ppwzManifestPaths`  
 [in] Optional. Ein Zeichenfolgenarray, das manifest Pfade für die Anwendung enthält.  
  
 `dwActivationData`  
 [in] Die Anzahl der Zeichenfolgen die `ppwzActivationData` Array.  
  
 `ppwzActivationData`  
 [in] Optional. Ein Zeichenfolgenarray, das die Anwendung Aktivierungsdaten, z. B. die Zeichenfolge Abfrageteil der URL für Anwendungen, die über das Internet bereitgestellt enthält.  
  
 `pReturnValue`  
 [out] Der Wert, der vom Einstiegspunkt der Anwendung zurückgegeben wird.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`ExecuteApplication`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 `ExecuteApplication`Dient zum Aktivieren von ClickOnce-Anwendungen in eine neu erstellte Anwendungsdomäne.  
  
 Die `pReturnValue` Output-Parameter von der Anwendung zurückgegebenen Wert festgelegt ist. Wenn Sie angeben, dass einen Wert von Null für `pReturnValue`, `ExecuteApplication` schlägt nicht fehl, aber es gibt keinen Wert zurück.  
  
> [!IMPORTANT]
>  Rufen Sie nicht die [Start-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) Methode vor dem Aufruf der `ExecuteApplication` Methode, um ein Manifest-basierten Anwendung aktivieren. Wenn die `Start` -Methode zuerst aufgerufen wird, die `ExecuteApplication` Methodenaufruf schlägt fehl.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ActivationContext>  
 <xref:System.AppDomainManager>  
 <xref:System.ApplicationIdentity>  
 [ICLRRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [SetAppDomainManager-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)  
 [Exemplarische Vorgehensweise: Bedarfsgerechtes Herunterladen von Assemblys mit der API für die ClickOnce-Bereitstellung unter Verwendung des Designers](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
