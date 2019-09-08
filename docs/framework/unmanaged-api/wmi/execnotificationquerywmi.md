---
title: Execnotificationquerywmi-Funktion (Referenz zur nicht verwalteten API)
description: Die execnotificationquerywmi-Funktion führt eine Abfrage aus, um Ereignisse zu empfangen.
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
ms.openlocfilehash: 5cfe54c7c9b7ae707b2d3591afbd830bac171f0b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798647"
---
# <a name="execnotificationquerywmi-function"></a>ExecNotificationQueryWmi-Funktion

Führt eine Abfrage zum Empfangen von Ereignissen aus. Der Aufruf wird sofort zurückgegeben, und der Aufrufer kann den zurückgegebenen Enumerator nach Ereignissen abrufen, sobald sie eintreffen. Wenn Sie den zurückgegebenen Enumerator freigeben, wird die Abfrage abgebrochen.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
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

`strQueryLanguage`\
in Eine Zeichenfolge mit der gültigen von der Windows-Verwaltung unterstützten Abfragesprache. Der Wert muss "WQL" und das Akronym für WMI-Abfragesprache sein.

`strQuery`\
in Der Text der Abfrage. Dieser Parameter darf nicht `null`sein.

`lFlags`\
in Eine Kombination der beiden folgenden Flags, die sich auf das Verhalten dieser Funktion auswirken. Diese Werte sind in der Header Datei " *wbemcli. h* " definiert, oder Sie können Sie als Konstanten im Code definieren.

| Konstante | Wert  | Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Das-Flag verursacht einen semisynchronen-Rückruf. Wenn dieses Flag nicht festgelegt ist, schlägt der-Befehl fehl. Dies liegt daran, dass Ereignisse kontinuierlich empfangen werden, was bedeutet, dass der Benutzer den zurückgegebenen Enumerator Abfragen muss. Durch eine unbegrenzte Sperre dieses Aufrufes ist dies unmöglich. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | Die-Funktion gibt einen vorwärts-Enumerator zurück. In der Regel sind vorwärts-Enumeratoren schneller und verbrauchen weniger Arbeitsspeicher als herkömmliche Enumeratoren, aber Sie erlauben keine Aufrufe von [Klonen](clone.md). |

`pCtx`\
in Normalerweise ist `null`dieser Wert. Andernfalls handelt es sich um einen Zeiger auf eine [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, der die angeforderten Ereignisse bereitstellt.

`ppEnum`\
vorgenommen Wenn kein Fehler auftritt, empfängt den Zeiger auf den Enumerator, der dem Aufrufer das Abrufen der Instanzen im Resultset der Abfrage ermöglicht. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".

`authLevel`\
in Die Autorisierungs Ebene.

`impLevel`\
in Die Ebene des Identitäts Wechsels.

`pCurrentNamespace`\
in Ein Zeiger auf ein [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) -Objekt, das den aktuellen Namespace darstellt.

`strUser`\
in Der Benutzername. Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.

`strPassword`\
in Das Kennwort. Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.

`strAuthority`\
in Der Domänen Name des Benutzers. Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | Der Benutzer verfügt nicht über die Berechtigung zum Anzeigen einer oder mehrerer Klassen, die von der Funktion zurückgegeben werden können. |
| `WBEM_E_FAILED` | 0x80041001 | Ein nicht angegebener Fehler ist aufgetreten. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | Die Abfrage gibt eine Klasse an, die nicht vorhanden ist. |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | 0x80042002 | Es wurde eine zu viel Genauigkeit bei der Übermittlung von Ereignissen angefordert. Es muss eine größere Abruf Toleranz angegeben werden. |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | 0x80042001 | Die Abfrage fordert mehr Informationen an als die Windows-Verwaltung bereitstellen kann. Dieser `HRESULT` Wert wird zurückgegeben, wenn eine Ereignis Abfrage eine Anforderung zum Abfragen aller Objekte in einem Namespace ergibt. |
| `WBEM_E_INVALID_QUERY` | 0x80041017 | Die Abfrage enthielt einen Syntax Fehler. |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | Die angeforderte Abfragesprache wird nicht unterstützt. |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | Die Abfrage ist zu komplex. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI wurde wahrscheinlich angehalten und neu gestartet. Ruft [connectserverwmi](connectserverwmi.md) erneut auf. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Fehler beim Remote Prozedur Aufruf (RPC)-Link zwischen dem aktuellen Prozess und WMI. |
| `WBEM_E_UNPARSABLE_QUERY` | 0x80041058 | Die Abfrage kann nicht analysiert werden. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemServices:: ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) -Methode.

Nachdem die Funktion zurückgegeben wurde, übergibt der Aufrufer regelmäßig das zurückgegebene `ppEnum` Objekt an die [Next](next.md) -Funktion, um festzustellen, ob Ereignisse verfügbar sind.

Die Anzahl der `AND` Schlüsselwörter und, die `OR` in WQL-Abfragen verwendet werden können, ist begrenzt. Eine große Anzahl von WQL-Schlüsselwörtern, die in einer komplexen Abfrage verwendet werden, `WBEM_E_QUOTA_VIOLATION` kann dazu führen, dass WMI den Fehlercode ( `HRESULT` oder 0x8004106c) als-Wert zurückgibt. Das Limit von WQL-Schlüsselwörtern hängt von der Komplexität der Abfrage ab.

Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, indem Sie die [GetErrorInfo](geterrorinfo.md) -Funktion aufrufen.

## <a name="requirements"></a>Anforderungen

**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** WMINet_Utils.idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
