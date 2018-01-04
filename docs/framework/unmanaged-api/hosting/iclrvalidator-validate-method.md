---
title: ICLRValidator::Validate-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRValidator.Validate
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRValidator::Validate
helpviewer_keywords:
- Validate method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::Validate method [.NET Framework hosting]
ms.assetid: 0b1b432a-d234-4002-839b-81366c3a8bdc
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7328fe62276de6c33464ab8cfc6d6a5f39ee710e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
  
#### <a name="parameters"></a>Parameter  
 `veh`  
 [in] Ein Zeiger auf eine `IVEHandler` -Instanz, die Validierungsfehler behandelt.  
  
 `ulAppDomainId`  
 [in] Der Bezeichner für die aktuelle <xref:System.AppDomain>.  
  
 `ulFlags`  
 [in] Eine Kombination von [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) Werte, der angibt, welche Art von Validierung, die ausgeführt werden soll.  
  
 `ulMaxError`  
 [in] Die maximale Anzahl von Fehlern, um zuzulassen, bevor Sie die Überprüfung beendet werden soll.  
  
 `token`  
 [in] Wird nicht verwendet.  
  
 `fileName`  
 [in] Der Name der Datei, die überprüft werden.  
  
 `pe`  
 [in] Ein Zeiger auf die Dateipuffer.  
  
 `ulSize`  
 [in] Die Größe in Bytes der Datei überprüft werden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`Validate`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** IValidator.idl, IValidator.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRValidator-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
