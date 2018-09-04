---
title: PutInstanceWmi-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion PutInstanceWmi erstellt oder aktualisiert eine Instanz einer vorhandenen Klasse.
ms.date: 11/06/2017
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
ms.openlocfilehash: 67abf017040b9e6bbe9b10e560c8d57c124ae84e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43658963"
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
[in] Ein Zeiger auf die Instanz, die geschrieben werden.

`lFlags`   
[in] Eine Kombination von Flags, die das Verhalten dieser Funktion zu beeinflussen. Die folgenden Werte werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code: 

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0 x 20000 | Wenn festgelegt, WMI keine keine Qualifizierer mit speichert die **Amended** Flavor. </br> Wenn dies nicht festgelegt ist, wird davon ausgegangen, dass dieses Objekt nicht lokalisiert ist und alle Qualifizierer Storedwith dieser Instanz. |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | Erstellen Sie die Instanz aus, wenn er nicht vorhanden ist, oder überschrieben, falls sie bereits vorhanden ist. |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | Aktualisieren Sie die Instanz. Die Instanz muss vorhanden sein, der Aufruf erfolgreich ist. |
| `WBEM_FLAG_CREATE_ONLY` | 2 | Erstellen Sie die Instanz. Der Aufruf schlägt fehl, wenn die Instanz bereits vorhanden ist. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Das Flag wird halbsynchron aufgerufen. |

`pCtx`  
[in] Dieser Wert in der Regel ist `null`. Andernfalls wird ein Zeiger auf ein [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, die die angeforderten Klassen bereitstellt. 

`ppCallResult`  
[out] Wenn `null`, dieser Parameter wird nicht verwendet. Wenn `lFlags` enthält `WBEM_FLAG_RETURN_IMMEDIATELY`, die Funktion gibt sofort zurück `WBEM_S_NO_ERROR`. Die `ppCallResult` Parameter erhält einen Zeiger auf ein neues [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) Objekt.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0 x 80041003 | Der Benutzer nicht über die Berechtigung zum Aktualisieren einer Instanz der angegebenen Klasse. |
| `WBEM_E_FAILED` | 0 x 80041001 | Ein Unbekannter Fehler aufgetreten. |
| `WBEM_E_INVALID_CLASS` | 0 x 80041010 | Die Klasse, die Unterstützung von dieser Instanz ist ungültig. |
| `WBEM_E_ILLEGAL_NULL` | 0x80041028 | eine `null` wurde für eine Eigenschaft, die kann nicht angegeben `null`, z. B. ein, die gekennzeichnet ist, indem ein **indiziert** oder **Not_Null** Qualifizierer. |
| `WBEM_E_INVALID_OBJECT` | 0x8004100f | Die angegebene Instanz ist ungültig. (Zum Beispiel der Aufruf `PutInstanceWmi` mit einer Klasse gibt diesen Wert zurück.) |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | Die `WBEM_FLAG_CREATE_ONLY` -Flag angegeben wurde, aber die Instanz bereits vorhanden ist. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | `WBEM_FLAG_UPDATE_ONLY` in wurde angegeben `lFlags`, aber die Instanz ist nicht vorhanden. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI wurde wahrscheinlich beendet und neu gestartet. Rufen Sie [ConnectServerWmi](connectserverwmi.md) erneut aus. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Der Remoteprozeduraufruf-Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-hat Fehler. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich. |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) Methode.

Die `PutInstanceWmi` unterstützt das Erstellen von Instanzen und Aktualisierung von vorhandenen Klassen nur Instanzen funktionieren.  Je nachdem, wie der `pCtx` Parameter festgelegt ist, einige oder alle Eigenschaften der Instanz aktualisiert werden. 

Wenn die Instanz verweist `pInst` gehört zu einer Unterklasse, die Windows-Verwaltung Ruft alle Anbieter, die verantwortlich für die Klassen, die von der die Unterklasse abgeleitet wird. Alle diese Anbieter muss erfolgreich sein, für die ursprüngliche `PutInstanceWmi` -Anforderung erfolgreich ist. Der Anbieter oberste Klasse in der Hierarchie unterstützt, wird zuerst aufgerufen. Die Aufrufreihenfolge weiterhin mit der Unterklasse der obersten-Klasse und von oben nach unten verläuft wird, bis Windows-Verwaltung den Anbieter für die Klasse, die Besitzer der Instanz verweist erreicht `pInst`.
Windows-Verwaltung wird die Anbieter für alle untergeordneten Klassen einer Instanz nicht aufgerufen werden. 

Wenn eine Anwendung eine Instanz aktualisieren muss, die zu einer Klassenhierarchie, gehört die `pInst` Parameter muss mit der Instanz, die mit den zu ändernden Eigenschaften verweisen. Beachten Sie, also eine Zielinstanz, die angehört **ClassB**. Die **ClassB** Instanz leitet sich von **ClassA**, und **ClassA** definiert die Eigenschaft **PropA**. Wenn eine Anwendung eine Änderung an den Wert der vornehmen möchte **PropA** in die **ClassB** -Instanz müssen sie festlegen `pInst` auf diese Instanz und nicht auf einer Instanz von **ClassA** .

Aufrufen von `PutInstanceWmi` auf einer Instanz einer abstrakten Klasse ist nicht zulässig.

Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch den Aufruf der [GetErrorInfo](geterrorinfo.md) Funktion.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
