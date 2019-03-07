---
title: ICLRValidator::Validate-Methode
ms.date: 03/30/2017
api_name:
- ICLRValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::Validate
helpviewer_keywords:
- Validate method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::Validate method [.NET Framework hosting]
ms.assetid: 0b1b432a-d234-4002-839b-81366c3a8bdc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ace11aa2cc3c24a6582b227f9a7ff8816ea0668
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492113"
---
# <a name="iclrvalidatorvalidate-method"></a>ICLRValidator::Validate-Methode
Überprüft die Datei (portable Executable) oder Microsoft intermediate Language (MSIL) in der angegebenen Datei.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Validate (  
    [in] IVEHandler        *veh,  
    [in] unsigned long      ulAppDomainId,  
    [in] unsigned long      ulFlags,  
    [in] unsigned long      ulMaxError,  
    [in] unsigned long      token,  
    [in] LPWSTR             fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long      ulSize  
);      
```  
  
## <a name="parameters"></a>Parameter  
 `veh`  
 [in] Ein Zeiger auf ein `IVEHandler` -Instanz, die Validierungsfehler behandelt.  
  
 `ulAppDomainId`  
 [in] Der Bezeichner für die aktuelle <xref:System.AppDomain>.  
  
 `ulFlags`  
 [in] Eine Kombination von [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) Werte, der die Art der Validierung ausgeführt werden soll.  
  
 `ulMaxError`  
 [in] Die maximale Anzahl von Fehlern, die vor dem Beenden der Überprüfungsprozess zulassen.  
  
 `token`  
 [in] Nicht verwendet.  
  
 `fileName`  
 [in] Der Name der Datei, die überprüft werden.  
  
 `pe`  
 [in] Ein Zeiger auf den Dateipuffer.  
  
 `ulSize`  
 [in] Die Größe in Bytes der Datei, die überprüft werden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`Validate` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** IValidator.idl, IValidator.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICLRValidator-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
