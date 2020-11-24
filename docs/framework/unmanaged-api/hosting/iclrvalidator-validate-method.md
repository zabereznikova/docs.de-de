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
ms.openlocfilehash: 4ce50f7706583f291d2e6a141d40ab6dd3e4b3e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674384"
---
# <a name="iclrvalidatorvalidate-method"></a>ICLRValidator::Validate-Methode

Überprüft die portable ausführbare Datei (PE) oder Microsoft Intermediate Language (MSIL) in der angegebenen Datei.  
  
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
 in Ein Zeiger auf eine- `IVEHandler` Instanz, die Validierungs Fehler behandelt.  
  
 `ulAppDomainId`  
 in Der Bezeichner für die aktuelle <xref:System.AppDomain> .  
  
 `ulFlags`  
 in Eine Kombination aus [ValidatorFlags](validatorflags-enumeration.md) -Werten, die die Art der Überprüfung angeben, die ausgeführt werden soll.  
  
 `ulMaxError`  
 in Die maximal zulässige Anzahl von Fehlern, bevor die Überprüfung beendet wird.  
  
 `token`  
 [in] Nicht verwendet.  
  
 `fileName`  
 in Der Name der zu validierenden Datei.  
  
 `pe`  
 in Ein Zeiger auf den Datei Puffer.  
  
 `ulSize`  
 in Die Größe (in Bytes) der zu validierenden Datei.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`Validate` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** IValidator. idl, IValidator. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRValidator-Schnittstelle](iclrvalidator-interface.md)
