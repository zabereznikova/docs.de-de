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
ms.openlocfilehash: 070c52258b66dcc352f2beef81b9a0694b8301ce
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703286"
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
 in Der Pfad zum <xref:System.Reflection.Assembly> , der das definiert, <xref:System.Type> dessen-Methode aufgerufen werden soll.  
  
 `pwzTypeName`  
 in Der Name der, die die aufzurufende <xref:System.Type> Methode definiert.  
  
 `pwzMethodName`  
 in Der Name der aufzurufenden Methode.  
  
 `pwzArgument`  
 in Der Zeichen folgen Parameter, der an die Methode übergeben werden soll.  
  
 `pReturnValue`  
 vorgenommen Der von der aufgerufenen Methode zurückgegebene ganzzahlige Wert.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`ExecuteInDefaultAppDomain`wurde erfolgreich zurückgegeben.|  
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
  
 dabei `pwzMethodName` steht für den Namen der aufgerufenen Methode und `pwzArgument` für den Zeichen folgen Wert, der als Parameter an diese Methode übergeben wird. Wenn der HRESULT-Wert auf S_OK festgelegt ist, `pReturnValue` wird auf den ganzzahligen Wert festgelegt, der von der aufgerufenen Methode zurückgegeben Andernfalls `pReturnValue` ist nicht festgelegt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRRuntimeHost-Schnittstelle](iclrruntimehost-interface.md)
