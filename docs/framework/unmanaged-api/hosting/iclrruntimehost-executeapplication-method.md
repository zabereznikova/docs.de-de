---
title: ICLRRuntimeHost::ExecuteApplication-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteApplication
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c2a56d153fcd7238f58c9650b8db08b3f39edaa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496273"
---
# <a name="iclrruntimehostexecuteapplication-method"></a>ICLRRuntimeHost::ExecuteApplication-Methode
In Szenarien für die ClickOnce-Manifest-basierten verwendet, an die Anwendung in einer neuen Domäne aktiviert werden. Weitere Informationen zu diesen Szenarien finden Sie unter [ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment).  
  
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
  
## <a name="parameters"></a>Parameter  
 `pwzAppFullName`  
 [in] Der vollständige Name der Anwendung entsprechend der Definition für <xref:System.ApplicationIdentity>.  
  
 `dwManifestPaths`  
 [in] Die Anzahl der Zeichenfolgen, die innerhalb der `ppwzManifestPaths` Array.  
  
 `ppwzManifestPaths`  
 [in] Optional. Ein Zeichenfolgenarray, das Manifestspfade für die Anwendung enthält.  
  
 `dwActivationData`  
 [in] Die Anzahl der Zeichenfolgen, die innerhalb der `ppwzActivationData` Array.  
  
 `ppwzActivationData`  
 [in] Optional. Ein Zeichenfolgenarray mit den von der Anwendung Aktivierungsdaten wie z. B. den Abfragezeichenfolgenabschnitt der URL für Anwendungen, die über das Internet bereitgestellt.  
  
 `pReturnValue`  
 [out] Der Wert, der von den Einstiegspunkt der Anwendung zurückgegeben wird.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`ExecuteApplication` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 `ExecuteApplication` Dient zum Aktivieren von ClickOnce-Anwendungen in eine neu erstellte Anwendungsdomäne.  
  
 Die `pReturnValue` Output-Parameter von der Anwendung zurückgegebenen Wert festgelegt ist. Wenn Sie angeben, dass der Wert Null für `pReturnValue`, `ExecuteApplication` schlägt nicht fehl, aber keinen Wert zurück.  
  
> [!IMPORTANT]
>  Rufen Sie nicht die [Methode starten](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) Methode vor dem Aufruf der `ExecuteApplication` Methode, um eine manifestbasierte Anwendung zu aktivieren. Wenn die `Start` Methode zuerst aufgerufen wird, die `ExecuteApplication` Methodenaufruf schlägt fehl.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [ICLRRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [SetAppDomainManager-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)
- [Exemplarische Vorgehensweise: Herunterladen von Assemblys bei Bedarf mit der API für die ClickOnce-Bereitstellung unter Verwendung des Designers](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
