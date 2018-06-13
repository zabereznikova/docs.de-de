---
title: PutClassWmi-Funktion (Referenz zur nicht verwalteten API)
description: Die PutClassWmi-Funktion wird eine neue Klasse erstellt oder aktualisiert eine vorhandene.
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
ms.openlocfilehash: 3ce887d59d02cfc2e4d8c183aa495dcc1535853c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461528"
---
# <a name="putclasswmi-function"></a>PutClassWmi-Funktion
Eine neue Klasse erstellt oder aktualisiert eine vorhandene.  

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
[in] Ein Zeiger auf eine gültige Klassendefinition. Es muss mit den erforderlichen Eigenschaftswerten ordnungsgemäß initialisiert werden.

`lFlags`   
[in] Eine Kombination von Flags, die das Verhalten dieser Funktion beeinflussen. Die folgenden Werte werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code: 

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0 x 20000 | Wenn Set WMI keine Qualifizierer mit der geänderten-Typ gespeichert werden. </br> Wenn dies nicht festgelegt ist, wird davon ausgegangen, dass dieses Objekt nicht lokalisiert ist und alle Qualifizierer Storedwith dieser Instanz. |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | Erstellen Sie die Klasse aus, wenn sie nicht vorhanden, oder sie zu überschreiben, wenn sie bereits vorhanden ist. |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | Aktualisieren Sie die Klasse. Die Klasse muss vorhanden sein, der Aufruf erfolgreich ist. |
| `WBEM_FLAG_CREATE_ONLY` | 2 | Erstellen einer Klasse. Der Aufruf fehlschlägt, wenn die Klasse bereits besteht. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Das Flag wird halbsynchrone aufgerufen. |
| `WBEM_FLAG_OWNER_UPDATE` | 0 x 10000 | Push-Anbieter müssen dieses Flag angeben, beim Aufrufen von `PutClassWmi` , um anzugeben, dass diese Klasse geändert hat. |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | 0 | Ermöglicht eine Klasse, die aktualisiert werden, wenn keine abgeleiteten Klassen und keine Instanzen dieser Klasse vorhanden sind. Darüber hinaus können Updates in allen Fällen ist die Änderung nur auf unwichtig Qualifizierer, z. B. das Description-Qualifizierers. Wenn die Klasse verfügt über Instanzen oder geändert, um wichtige Qualifizierer werden, schlägt die Aktualisierung fehl. |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | 0x20 | Lässt Updates zu Klassen an, auch wenn untergeordnete Klassen vorhanden sind, solange die Änderung keine Konflikte mit den untergeordneten Klassen verursacht. Dieses Flag kann z. B. eine neue Eigenschaft in der Basisklasse hinzugefügt werden, die in einem der untergeordneten Klassen nicht zuvor erwähnt wurde. Wenn die Klasse Instanzen verfügt, schlägt die Aktualisierung fehl. |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | 0 x 40 | Erzwingt die Aktualisierung von Klassen, wenn konfliktverursachende untergeordnete Klassen vorhanden sind. Dieses Flag erzwingt z. B. ein Update aus, wenn ein Qualifizierer für die Klasse in einer untergeordneten Klasse definiert ist, und die Basisklasse der Klasse versucht, den gleichen Qualifizierer hinzufügen, die Konflikt mit des maßgeblichen eine vorhandene. Im Modus "Force" ist Tis-Konflikt aufgelöst, indem Sie den in Konflikt stehenden Qualifizierer in der untergeordneten Klasse gelöscht. |

`pCtx`  
[in] In der Regel wird dieser Wert ist `null`. Andernfalls ist ein Zeiger auf ein ["IWbemContext"](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) -Instanz, die vom Anbieter verwendet werden kann, das die angeforderte Klassen bereitstellt. 

`ppCallResult`  
[out] Wenn `null`, dieser Parameter wird nicht verwendet. Wenn `lFlags` enthält `WBEM_FLAG_RETURN_IMMEDIATELY`, die Funktion gibt sofort mit `WBEM_S_NO_ERROR`. Die `ppCallResult` Parameter erhält einen Zeiger auf ein neues [IWbemCallResult](https://msdn.microsoft.com/library/aa391425(v=vs.85).aspx) Objekt.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0 x 80041003 | Der Benutzer keine Berechtigung zum Erstellen oder Ändern von Klassen. |
| `WBEM_E_FAILED` | 0 x 80041001 | Nicht angegebener Fehler ist aufgetreten. |
| `WBEM_E_INVALID_CLASS` | 0 x 80041010 | Die angegebene Klasse ist ungültig. In der Regel zeigt dies an, dass `pObject` ein Instanzobjekt angibt. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_INVALID OPERATION` | 0x80041016 | Der Name der angegebenen Klasse ist ungültig. |
| `WBEM_E_CLASS_HAS_CHILDREN` | 0x80041025 | Es wurde versucht, eine Änderung vorzunehmen, die eine Unterklasse ungültig machen würde. |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | Die `WBEM_FLAG_CREATE_ONLY` -Flag angegeben wurde, aber die Klasse bereits besteht. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | `WBEM_FLAG_UPDATE_ONLY` wurde im angegebenen `lFlags`, und die Klasse wurde nicht gefunden. |
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | Die erforderlichen Eigenschaften für Klassen haben nicht alle festgelegt wurde. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI wurde wahrscheinlich beendet und neu gestartet. Rufen Sie [ConnectServerWmi](connectserverwmi.md) erneut aus. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Der Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-ausgefallen ist. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemServices::PutClass](https://msdn.microsoft.com/library/aa392113(v=vs.85).aspx) Methode.

Der Benutzer darf keine Klassen mit Namen erstellen, die mit einem Unterstrich Chacater beginnen oder enden

Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch Aufrufen der [GetErrorInfo](geterrorinfo.md) Funktion.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
