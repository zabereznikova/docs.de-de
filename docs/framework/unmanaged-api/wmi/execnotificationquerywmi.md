---
title: ExecNotificationQueryWmi-Funktion (Referenz zur nicht verwalteten API)
description: ExecNotificationQueryWmi-Funktion führt eine Abfrage, um Ereignisse zu empfangen.
ms.date: 11/06/2017
api_name:
- ExecNotificationQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecNotificationQueryWmi
helpviewer_keywords:
- ExecNotificationQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d314d85e7c1297636e8dd5cecaf050a527151518
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43453050"
---
# <a name="execnotificationquerywmi-function"></a>ExecNotificationQueryWmi-Funktion
Führt eine Abfrage zum Empfangen von Ereignissen. Der Aufruf sofort zurückgegeben, und der Aufrufer Abfragen kann des zurückgegebenen Enumerators für Ereignisse, deren eintreffen. Den zurückgegebenen Enumerator freigegeben wird, bricht die Abfrage ab.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ExecNotificationQueryWmi (
   [in] BSTR                    strQueryLanguage,
   [in] BSTR                    strQuery,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
); 
```  

## <a name="parameters"></a>Parameter

`strQueryLanguage`    
[in] Eine Zeichenfolge mit der gültigen Abfragesprache, die von der Windows-Verwaltung unterstützt. Es muss "WQL", das Akronym für WMI-Abfragesprache.

`strQuery`  
[in] Der Text der Abfrage. Dieser Parameter darf nicht sein `null`.

`lFlags`   
[in] Eine Kombination der folgenden zwei Flags, die das Verhalten dieser Funktion zu beeinflussen. Diese Werte werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code. 

| Konstante | Wert  | Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Das Flag wird halbsynchron aufgerufen. Wenn dieses Flag nicht festgelegt ist, schlägt der Aufruf fehl. Grund hierfür ist Ereignisse kontinuierlich stammen, was bedeutet, dass der Benutzer den zurückgegebenen Enumerator abrufen muss. Dieser Aufruf auf unbestimmte Zeit blockiert wird, die unmöglich. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | Die Funktion gibt einen Enumerator vorwärts gerichtete. In der Regel vorwärts-Enumeratoren sind schneller, und verwenden Sie weniger Arbeitsspeicher als konventionelle Enumeratoren, aber sie ermöglichen keine Aufrufe von [Klon](clone.md). |

`pCtx`  
[in] Dieser Wert in der Regel ist `null`. Andernfalls wird ein Zeiger auf ein [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, die die angeforderte Ereignisse bereitstellt. 

`ppEnum`  
[out] Wenn kein Fehler auftritt, empfängt den Zeiger auf der Enumerator, der dem Aufrufer zum Abrufen von Instanzen im Resultset der Abfrage ermöglicht. Finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.

`authLevel`  
[in] Die Autorisierungsebene.

`impLevel` [in] Die Ebene des Identitätswechsels.

`pCurrentNamespace`   
[in] Ein Zeiger auf ein [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) -Objekt, das den aktuellen Namespace darstellt.

`strUser`   
[in] Der Benutzername. Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.

`strPassword`   
[in] Das Kennwort. Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.

`strAuthority`   
[in] Der Domänenname des Benutzers. Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0 x 80041003 | Der Benutzer keine Berechtigung zum Anzeigen, eine oder mehrere Klassen, die die Funktion zurückgeben kann. |
| `WBEM_E_FAILED` | 0 x 80041001 | Ein Unbekannter Fehler aufgetreten. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_INVALID_CLASS` | 0 x 80041010 | Die Abfrage gibt eine Klasse, die nicht vorhanden ist. |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | 0x80042002 | Zu viel Genauigkeit bei der Übermittlung von Ereignissen wurde angefordert. Eine größere Abruf Toleranz muss angegeben werden. |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | 0 x 80042001 | Die Abfrage Requess kann mehr Informationen als Windows-Verwaltung bereitstellen. Dies `HRESULT` wird zurückgegeben, wenn ein Event-in einer Anforderung zum Abrufen aller Objekte in einem Namespace Abfrageergebnisse. |
| `WBEM_E_INVALID_QUERY` | 0x80041017 | Die Abfrage musste ein Syntaxfehler aufgetreten. |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | Die angeforderte Abfragesprache wird nicht unterstützt. |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | Die Abfrage ist zu komplex. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI wurde wahrscheinlich beendet und neu gestartet. Rufen Sie [ConnectServerWmi](connectserverwmi.md) erneut aus. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Der Remoteprozeduraufruf-Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-hat Fehler. |
| `WBEM_E_UNPARSABLE_QUERY` | 0x80041058 | Die Abfrage kann nicht analysiert werden. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) Methode.

Nachdem die Funktion zurückgibt, der Aufrufer in regelmäßigen Abständen übergibt das zurückgegebene `ppEnum` -Objekt an die [Weiter](next.md) Funktion, um festzustellen, ob alle Ereignisse zur Verfügung stehen.

Bestehen Einschränkungen in Bezug auf die Anzahl der `AND` und `OR` Schlüsselwörter, die in WQL-Abfragen verwendet werden können. Große Anzahl von WQL-Schlüsselwörter, die verwendet werden, in eine komplexe Abfrage kann dazu führen, dass WMI Zurückgeben der `WBEM_E_QUOTA_VIOLATION` (oder 0x8004106c) Fehlercode als ein `HRESULT` Wert. Das Limit von WQL-Schlüsselwörter, hängt davon ab, wie komplex die Abfrage ist.

Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch den Aufruf der [GetErrorInfo](geterrorinfo.md) Funktion.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
