---
title: ICLRRuntimeHost::ExecuteInDefaultAppDomain-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type:
- apiref
ms.openlocfilehash: ed841d1b2ff346ebef668cbd96a58ddfe466b3b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120448"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a>ICLRRuntimeHost::ExecuteInDefaultAppDomain-Methode
Ruft die angegebene Methode des angegebenen Typs in der angegebenen verwalteten Assembly auf.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,   
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pwzAssemblyPath`  
 in Der Pfad zum <xref:System.Reflection.Assembly>, der die <xref:System.Type> definiert, deren-Methode aufgerufen werden soll.  
  
 `pwzTypeName`  
 in Der Name der <xref:System.Type>, die die aufzurufende Methode definiert.  
  
 `pwzMethodName`  
 in Der Name der aufzurufenden Methode.  
  
 `pwzArgument`  
 in Der Zeichen folgen Parameter, der an die Methode übergeben werden soll.  
  
 `pReturnValue`  
 vorgenommen Der von der aufgerufenen Methode zurückgegebene ganzzahlige Wert.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`ExecuteInDefaultAppDomain` erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CRL innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die aufgerufene Methode muss die folgende Signatur aufweisen:  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 , wobei `pwzMethodName` den Namen der aufgerufenen Methode darstellt, und `pwzArgument` den als Parameter an diese Methode übergebenen Zeichen folgen Wert darstellt. Wenn HRESULT auf S_OK festgelegt ist, wird `pReturnValue` auf den ganzzahligen Wert festgelegt, der von der aufgerufenen Methode zurückgegeben wird. Andernfalls ist `pReturnValue` nicht festgelegt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
