---
title: ExecNotificationQueryWmi-Funktion (Referenz zur nicht verwalteten API)
description: Die ExecNotificationQueryWmi-Funktion führt eine Abfrage aus, um Ereignisse zu empfangen.
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
ms.openlocfilehash: 4b5c26ab9c273b134915eea39078a83f569bcd32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462415"
---
# <a name="execnotificationquerywmi-function"></a>ExecNotificationQueryWmi-Funktion
Führt eine Abfrage aus, um Ereignisse zu empfangen. Der Aufruf sofort zurückgegeben, und der Aufrufer den zurückgegebenen Enumerator für Ereignisse beim Eintreffen Abfragen kann. Den zurückgegebenen Enumerator freigeben, wird die Abfrage abgebrochen.  

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
[in] Eine Kombination der folgenden zwei Flags, die das Verhalten dieser Funktion zu beeinflussen. Diese Werte werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code. 

| Konstante | Wert  | Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Das Flag wird halbsynchrone aufgerufen. Wenn dieses Flag nicht festgelegt ist, schlägt der Aufruf fehl. Grund hierfür ist Ereignisse kontinuierlich, stammen, was bedeutet, dass der Benutzer den zurückgegebenen Enumerator abrufen muss. Dieser Aufruf auf unbestimmte Zeit blockiert ist, die nicht möglich. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | Die Funktion gibt einen Enumerator Vorwärtscursor. In der Regel nur vorwärts Enumeratoren werden schneller ausgeführt und belegen weniger Speicher als konventionelle Enumeratoren, aber es nicht möglich, dass Aufrufe [Klon](clone.md). |

`pCtx`  
[in] In der Regel wird dieser Wert ist `null`. Andernfalls ist ein Zeiger auf ein ["IWbemContext"](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) -Instanz, die vom Anbieter verwendet werden kann, das die angeforderte Ereignisse bereitstellt. 

`ppEnum`  
[out] Wenn kein Fehler auftritt, empfängt den Zeiger auf den Enumerator, der den Aufrufer beim Abrufen von den Instanzen im Resultset der Abfrage ermöglicht. Finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.

`authLevel`  
[in] Die Autorisierungsebene.

`impLevel` [in] Die Ebene des Identitätswechsels.

`pCurrentNamespace`   
[in] Ein Zeiger auf ein [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) -Objekt, das den aktuellen Namespace darstellt.

`strUser`   
[in] Der Benutzername. Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.

`strPassword`   
[in] Das Kennwort. Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.

`strAuthority`   
[in] Der Domänenname des Benutzers. Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0 x 80041003 | Der Benutzer keine Berechtigung zum Anzeigen, eine oder mehrere Klassen, die die Funktion zurückgeben kann. |
| `WBEM_E_FAILED` | 0 x 80041001 | Nicht angegebener Fehler ist aufgetreten. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_INVALID_CLASS` | 0 x 80041010 | Die Abfrage gibt eine Klasse, die nicht vorhanden ist. |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | 0x80042002 | Zu viele mit einfacher Genauigkeit in die Übermittlung von Ereignissen wurde angefordert. Eine größere Abruf Toleranz muss angegeben werden. |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | 0x80042001 | Die Abfrage Requess kann mehr Informationen als Windows-Verwaltung bereitstellen. Dies `HRESULT` wird zurückgegeben, wenn ein Ereignis in einer Anforderung zum Abrufen aller Objekte in einem Namespace Abfrageergebnisse. |
| `WBEM_E_INVALID_QUERY` | 0x80041017 | Die Abfrage hat einen Syntaxfehler. |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | Die angeforderte Abfragesprache wird nicht unterstützt. |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | Die Abfrage ist zu komplex. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI wurde wahrscheinlich beendet und neu gestartet. Rufen Sie [ConnectServerWmi](connectserverwmi.md) erneut aus. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Der Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-ausgefallen ist. |
| `WBEM_E_UNPARSABLE_QUERY` | 0x80041058 | Die Abfrage kann nicht analysiert werden. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemServices::ExecNotificationQuery](https://msdn.microsoft.com/library/aa392105(v=vs.85).aspx) Methode.

Nachdem die Funktion zurückgibt, der Aufrufer in regelmäßigen Abständen übergibt das zurückgegebene `ppEnum` -Objekt an die [Weiter](next.md) Funktion, um festzustellen, ob alle Ereignisse verfügbar sind.

Begrenzt die Anzahl der `AND` und `OR` Schlüsselwörter, die in der WQL-Abfragen verwendet werden können. Große Anzahl von WQL Schlüsselwörter in eine komplexe Abfrage kann dazu führen, dass WMI zurückzugebenden der `WBEM_E_QUOTA_VIOLATION` (oder 0x8004106c) Fehlercode als ein `HRESULT` Wert. Das Limit von WQL-Schlüsselwörter, hängt davon ab, wie komplex die Abfrage ist.

Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch Aufrufen der [GetErrorInfo](geterrorinfo.md) Funktion.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
