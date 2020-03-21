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
ms.openlocfilehash: 427895ffea94e6c657d775ebdeb8571070a61c6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178066"
---
# <a name="iclrvalidatorvalidate-method"></a>ICLRValidator::Validate-Methode
Überprüft die portable ausführbare Datei (PE) oder Microsoft-Zwischensprache (MSIL) in der angegebenen Datei.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 [in] Ein Zeiger auf `IVEHandler` eine Instanz, die Validierungsfehler verarbeitet.  
  
 `ulAppDomainId`  
 [in] Der Bezeichner <xref:System.AppDomain>für die aktuelle .  
  
 `ulFlags`  
 [in] Eine Kombination von [ValidatorFlags-Werten,](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) die die Art der Validierung angibt, die ausgeführt werden soll.  
  
 `ulMaxError`  
 [in] Die maximale Anzahl von Fehlern, die vor dem Beenden der Validierung zugelassen werden sollen.  
  
 `token`  
 [in] Nicht verwendet.  
  
 `fileName`  
 [in] Der Name der zu überprüfenden Datei.  
  
 `pe`  
 [in] Ein Zeiger auf den Dateipuffer.  
  
 `ulSize`  
 [in] Die Größe der zu überprüfenden Datei in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`Validate`erfolgreich zurückgegeben werden.|  
|HOST_E_CLRNOTAVAILABLE|Die Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout für den Anruf.|  
|HOST_E_NOT_OWNER|Der Aufrufer besitzt die Sperre nicht.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.|  
|E_FAIL|Ein unbekannter katastrophaler Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** IValidator.idl, IValidator.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRValidator-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
