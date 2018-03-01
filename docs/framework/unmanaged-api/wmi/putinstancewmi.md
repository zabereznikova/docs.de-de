---
title: PutInstanceWmi-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion PutInstanceWmi erstellt oder aktualisiert eine Instanz einer vorhandenen Klasse.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- PutInstanceWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutInstanceWmi
helpviewer_keywords:
- PutInstanceWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b1996103eea87562226537f9aa90dc337c56313c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="putinstancewmi-function"></a>PutInstanceWmi-Funktion
Erstellt oder aktualisiert eine Instanz einer vorhandenen Klasse. Die Instanz wird in das WMI-Repository geschrieben. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a>Parameter

`pInst`    
[in] Ein Zeiger auf die Instanz Writen sein.

`lFlags`   
[in] Eine Kombination von Flags, die das Verhalten dieser Funktion beeinflussen. Die folgenden Werte werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code: 

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0 x 20000 | Wenn festgelegt, WMI keine Qualifizierer mit speichert die **Amended** Flavor. </br> Wenn dies nicht festgelegt ist, wird davon ausgegangen, dass dieses Objekt nicht lokalisiert ist und alle Qualifizierer Storedwith dieser Instanz. |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | Erstellen Sie die Instanz aus, wenn sie nicht vorhanden, oder sie zu überschreiben, wenn sie bereits vorhanden ist. |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | Aktualisieren Sie die Instanz. Die Instanz muss vorhanden sein, der Aufruf erfolgreich ist. |
| `WBEM_FLAG_CREATE_ONLY` | 2 | Erstellen Sie die Instanz. Der Aufruf fehlschlägt, wenn die Instanz bereits vorhanden ist. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0 x 10 | Das Flag wird halbsynchrone aufgerufen. |

`pCtx`  
[in] In der Regel wird dieser Wert ist `null`. Andernfalls ist ein Zeiger auf ein ["IWbemContext"](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) -Instanz, die vom Anbieter verwendet werden kann, das die angeforderte Klassen bereitstellt. 

`ppCallResult`  
[out] Wenn `null`, dieser Parameter wird nicht verwendet. Wenn `lFlags` enthält `WBEM_FLAG_RETURN_IMMEDIATELY`, die Funktion gibt sofort mit `WBEM_S_NO_ERROR`. Die `ppCallResult` Parameter erhält einen Zeiger auf ein neues [IWbemCallResult](https://msdn.microsoft.com/library/aa391425(v=vs.85).aspx) Objekt.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0 x 80041003 | Der Benutzer nicht über die Berechtigung zum Aktualisieren einer Instanz der angegebenen Klasse. |
| `WBEM_E_FAILED` | 0 x 80041001 | Nicht angegebener Fehler ist aufgetreten. |
| `WBEM_E_INVALID_CLASS` | 0 x 80041010 | Die Klasse, die Unterstützung dieser Instanz ist ungültig. |
| `WBEM_E_ILLEGAL_NULL` | 0x80041028 | eine `null` Zielsätzen für eine Eigenschaft, die nicht möglich `null`, z. B. die von markiert ist ein **indiziert** oder **Not_Null** Qualifizierer. |
| `WBEM_E_INVALID_OBJECT` | 0x8004100f | Die angegebene Instanz ist ungültig. (Z. B. durch Aufruf von `PutInstanceWmi` mit einer Klasse gibt diesen Wert zurück.) |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | Die `WBEM_FLAG_CREATE_ONLY` -Flag angegeben wurde, aber die Instanz ist bereits vorhanden. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | `WBEM_FLAG_UPDATE_ONLY`wurde im angegebenen `lFlags`, aber die Instanz ist nicht vorhanden. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI wurde wahrscheinlich beendet und neu gestartet. Rufen Sie [ConnectServerWmi](connectserverwmi.md) erneut aus. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Der Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-ausgefallen ist. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich. |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemServices::PutInstance](https://msdn.microsoft.com/library/aa392115(v=vs.85).aspx) Methode.

Die `PutInstanceWmi` -Funktion unterstützt das Erstellen von Instanzen und Instanzen von vorhandenen Klassen nur aktualisieren.  Je nachdem, wie der `pCtx` Parameter festgelegt ist, einige oder alle Eigenschaften der Instanz aktualisiert werden. 

Wenn die Instanz verweist, zu `pInst` gehört zu einer Unterklasse, die Verwaltung von Windows ruft alle Anbieter, die verantwortlich für die Klassen, die von der Unterklasse abgeleitet wird. Alle diese Anbieter muss erfolgreich sein, für die ursprüngliche `PutInstanceWmi` Anforderung erfolgreich verarbeitet. Der Anbieter unterstützt die oberste Klasse in der Hierarchie wird zuerst aufgerufen. Die Reihenfolge des Aufrufs angezeigt mit die Unterklasse der obersten Klasse fortgesetzt und von oben nach unten verläuft wird, bis Windows Management den Anbieter für die Klasse, die Besitzer der Instanz verweist erreicht `pInst`.
Verwaltung von Windows wird die Anbieter für alle untergeordneten Klassen einer Instanz nicht aufgerufen werden. 

Wenn eine Anwendung eine Instanz aktualisieren muss, die zu einer Klassenhierarchie gehört die `pInst` Parameter muss mit der Instanz, die mit den zu ändernden Eigenschaften verweisen. Betrachten Sie also eine Zielinstanz, die zu gehört **ClassB**. Die **ClassB** Instanz leitet sich von **ClassA**, und **ClassA** definiert die Eigenschaft **PropA**. Wenn eine Anwendung eine Änderung an den Wert der vornehmen möchte **PropA** in der **ClassB** Instanz müssen sie festlegen `pInst` auf diese Instanz statt mit einer Instanz von **ClassA** .

Aufrufen von `PutInstanceWmi` auf einer Instanz einer abstrakten Klasse ist nicht zulässig.

Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch Aufrufen der [GetErrorInfo](geterrorinfo.md) Funktion.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
