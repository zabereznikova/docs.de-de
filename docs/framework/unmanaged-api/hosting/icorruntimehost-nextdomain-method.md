---
title: ICorRuntimeHost::NextDomain-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.NextDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type:
- apiref
ms.openlocfilehash: 36eacedfb83c1248fc252091872bcfeecdbcd874
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139518"
---
# <a name="icorruntimehostnextdomain-method"></a>ICorRuntimeHost::NextDomain-Methode
Ruft einen Schnittstellen Zeiger auf die nächste Domäne in der-Enumeration ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `hEnum`  
 in Der Enumerator, der durch einen aufzurufenden [Enumerator](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)abgerufen wurde.  
  
 `pAppDomain`  
 vorgenommen Ein Schnittstellen Zeiger auf den <xref:System._AppDomain?displayProperty=nameWithType> Typ, der die nächste Domäne in der Enumeration darstellt, oder NULL, wenn keine weiteren Domänen vorhanden sind.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Der Vorgang war erfolgreich.|  
|S_FALSE|Der Vorgang konnte nicht ausgeführt werden, oder es sind keine weiteren Domänen in der Enumeration vorhanden.|  
|E_FAIL|Ein unbekannter, schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die Common Language Runtime (CLR) im Prozess nicht mehr verwendet werden. Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:** 1,0, 1,1  
  
## <a name="see-also"></a>Siehe auch

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [ICorRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
