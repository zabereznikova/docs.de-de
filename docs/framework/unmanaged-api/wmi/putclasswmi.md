---
title: PutClassWmi-Funktion (Referenz zur nicht verwalteten API)
description: Die PutClassWmi-Funktion wird eine neue Klasse erstellt oder aktualisiert eine bereits vorhandene.
ms.date: 11/06/2017
api_name:
- PutClassWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutClassWmi
helpviewer_keywords:
- PutClassWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de08662a825a84f19a40863cf73481d89364ebd0
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48046553"
---
# <a name="putclasswmi-function"></a>PutClassWmi-Funktion
Erstellt eine neue Klasse oder aktualisiert eine vorhandene Klasse.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a>Parameter

`pObject`    
[in] Ein Zeiger auf eine gültige Klassendefinition. Es muss ordnungsgemäß mit allen Werten für die erforderliche Eigenschaft initialisiert werden.

`lFlags`   
[in] Eine Kombination von Flags, die das Verhalten dieser Funktion zu beeinflussen. Die folgenden Werte werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code: 

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0 x 20000 | Wenn festgelegt ist, WMI keine keine Qualifizierer mit den geänderten Typ gespeichert werden. </br> Wenn dies nicht festgelegt ist, wird davon ausgegangen, dass dieses Objekt nicht lokalisiert ist und alle Qualifizierer Storedwith dieser Instanz. |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | Erstellen Sie die Klasse aus, wenn er nicht vorhanden ist, oder überschrieben, falls sie bereits vorhanden ist. |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | Aktualisieren Sie die Klasse. Der Aufruf erfolgreich ausgeführt werden muss die Klasse vorhanden sein. |
| `WBEM_FLAG_CREATE_ONLY` | 2 | Erstellen Sie die Klasse. Der Aufruf schlägt fehl, wenn die Klasse bereits vorhanden ist. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Das Flag wird halbsynchron aufgerufen. |
| `WBEM_FLAG_OWNER_UPDATE` | 0 x 10000 | Push-Anbieter müssen dieses Flag angeben, beim Aufrufen von `PutClassWmi` , um anzugeben, dass diese Klasse geändert wurde. |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | 0 | Ermöglicht eine Klasse, die aktualisiert werden, wenn keine abgeleiteten Klassen und keine Instanzen dieser Klasse vorhanden sind. Darüber hinaus können Updates in allen Fällen ist die Änderung nur auf unwichtig Qualifizierer, z. B. das Description-Qualifizierers. Wenn die Klasse verfügt über Instanzen oder Änderungen wichtig, Qualifizierer sind, schlägt die Aktualisierung fehl. |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | 0x20 | Können Updates von Klassen aus, auch wenn die untergeordnete Klassen vorhanden sind, solange die Änderung keine Konflikte mit den untergeordneten Klassen verursacht. Dieses Flag ermöglicht beispielsweise eine neue Eigenschaft mit der Basisklasse hinzugefügt werden, die in allen untergeordneten Klassen nicht zuvor erwähnt wurde. Wenn die Klasse Instanzen verfügt, schlägt die Aktualisierung fehl. |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | 0 x 40 | Erzwingt die Aktualisierung von Klassen, wenn konfliktverursachende untergeordnete Klassen vorhanden sind. Dieses Flag erzwingt z. B. ein Update aus, wenn ein Klasse-Qualifizierer in einer untergeordneten Klasse definiert ist und die Basisklasse der Klasse versucht, den gleichen Qualifizierer hinzufügen, die mit des maßgeblichen eine vorhandenen in Konflikt steht. Im Modus "Force" Tis-Konflikt lässt sich durch das Löschen des in Konflikt stehende Qualifizierers in der untergeordneten Klasse. |

`pCtx`  
[in] Dieser Wert in der Regel ist `null`. Andernfalls wird ein Zeiger auf ein [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, die die angeforderten Klassen bereitstellt. 

`ppCallResult`  
[out] Wenn `null`, dieser Parameter wird nicht verwendet. Wenn `lFlags` enthält `WBEM_FLAG_RETURN_IMMEDIATELY`, die Funktion gibt sofort zurück `WBEM_S_NO_ERROR`. Die `ppCallResult` Parameter erhält einen Zeiger auf ein neues [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) Objekt.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0 x 80041003 | Der Benutzer besitzt keine Berechtigung zum Erstellen oder Ändern von Klassen. |
| `WBEM_E_FAILED` | 0 x 80041001 | Ein Unbekannter Fehler aufgetreten. |
| `WBEM_E_INVALID_CLASS` | 0 x 80041010 | Die angegebene Klasse ist ungültig. In der Regel gibt dies an, dass `pObject` ein Instanzobjekt angibt. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_INVALID OPERATION` | 0x80041016 | Der Name für die angegebene Klasse ist ungültig. |
| `WBEM_E_CLASS_HAS_CHILDREN` | 0x80041025 | Es wurde versucht, eine Änderung vornehmen, die eine Unterklasse ungültig machen würde. |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | Die `WBEM_FLAG_CREATE_ONLY` -Flag angegeben wurde, aber die Klasse bereits vorhanden ist. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | `WBEM_FLAG_UPDATE_ONLY` in wurde angegeben `lFlags`, und die Klasse wurde nicht gefunden. |
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | Die erforderlichen Eigenschaften für Klassen wurden nicht alle festgelegt. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI wurde wahrscheinlich beendet und neu gestartet. Rufen Sie [ConnectServerWmi](connectserverwmi.md) erneut aus. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Der Remoteprozeduraufruf-Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-hat Fehler. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) Methode.

Der Benutzer darf keine Klassen mit Namen erstellen, die mit einem Unterstrich Chacater beginnen oder enden

Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch den Aufruf der [GetErrorInfo](geterrorinfo.md) Funktion.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
