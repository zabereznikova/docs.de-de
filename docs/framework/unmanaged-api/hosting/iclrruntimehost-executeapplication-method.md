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
ms.openlocfilehash: 38938de335e5f0d7cb8051554c400f16df012362
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965359"
---
# <a name="iclrruntimehostexecuteapplication-method"></a>ICLRRuntimeHost::ExecuteApplication-Methode
Wird in Manifest-basierten ClickOnce-Bereitstellungs Szenarien verwendet, um die Anwendung anzugeben, die in einer neuen Domäne aktiviert werden soll. Weitere Informationen zu diesen Szenarien finden Sie unter [ClickOnce-Sicherheit und-Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 in Der vollständige Name der Anwendung, wie für <xref:System.ApplicationIdentity>definiert.  
  
 `dwManifestPaths`  
 in Die Anzahl der Zeichen folgen, die `ppwzManifestPaths` im Array enthalten sind.  
  
 `ppwzManifestPaths`  
 [in] Optional. Ein Zeichen folgen Array, das Manifeste Pfade für die Anwendung enthält.  
  
 `dwActivationData`  
 in Die Anzahl der Zeichen folgen, die `ppwzActivationData` im Array enthalten sind.  
  
 `ppwzActivationData`  
 [in] Optional. Ein Zeichen folgen Array, das die Aktivierungsdaten der Anwendung enthält, z. b. den Teil der Abfrage Zeichenfolge der URL für Anwendungen, die über das Web bereitgestellt werden  
  
 `pReturnValue`  
 vorgenommen Der Wert, der vom Einstiegspunkt der Anwendung zurückgegeben wird.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`ExecuteApplication`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 `ExecuteApplication`wird verwendet, um ClickOnce-Anwendungen in einer neu erstellten Anwendungsdomäne zu aktivieren.  
  
 Der `pReturnValue` Output-Parameter wird auf den Wert festgelegt, der von der Anwendung zurückgegeben wird. Wenn Sie für `pReturnValue` `ExecuteApplication` den Wert NULL angeben, schlägt nicht fehl, aber es wird kein Wert zurückgegeben.  
  
> [!IMPORTANT]
> Rufen Sie nicht die Methode [Start Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) auf, bevor `ExecuteApplication` Sie die-Methode aufrufen, um eine Manifest-basierte Anwendung zu aktivieren. Wenn die `Start` -Methode zuerst aufgerufen wird, `ExecuteApplication` kann der Methodenaufruf nicht ausgeführt werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Fern** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [ICLRRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [SetAppDomainManager-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)
- [Exemplarische Vorgehensweise: Herunterladen von Assemblys bei Bedarf mit der API für die ClickOnce-Bereitstellung unter Verwendung des Designers](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
