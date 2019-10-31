---
title: Execquerywmi-Funktion (Referenz zur nicht verwalteten API)
description: Die execquerywmi-Funktion führt eine Abfrage zum Abrufen von-Objekten aus.
ms.date: 11/06/2017
api_name:
- ExecQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecQueryWmi
helpviewer_keywords:
- ExecQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 3c6ea58eca5ac635893a24b57ade261e04a69721
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130434"
---
# <a name="execquerywmi-function"></a>ExecQueryWmi-Funktion

Führt eine Abfrage zum Abrufen von Objekten aus.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT ExecQueryWmi (
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
in Der Text der Abfrage. Dieser Parameter kann nicht `null`werden.

`lFlags`\
in Eine Kombination von Flags, die sich auf das Verhalten dieser Funktion auswirken. Die folgenden Werte sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

| Konstante | Wert  | Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Wenn festgelegt, ruft die Funktion die im lokalisierten Namespace des Gebiets Schemas der aktuellen Verbindung gespeicherten geänderten Qualifizierer ab. <br/> Wenn nicht festgelegt, ruft die Funktion nur die Qualifizierer ab, die im unmittelbaren Namespace gespeichert sind. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Das-Flag verursacht einen semisynchronen-Rückruf. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | Die-Funktion gibt einen vorwärts-Enumerator zurück. In der Regel sind vorwärts-Enumeratoren schneller und verbrauchen weniger Arbeitsspeicher als herkömmliche Enumeratoren, aber Sie erlauben keine Aufrufe von [Klonen](clone.md). |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI behält Zeiger auf Objekte in der-Enumeration bei, bis Sie freigegeben werden. |
| `WBEM_FLAG_ENSURE_LOCATABLE` | 0x100 | Stellt sicher, dass alle zurückgegebenen Objekte über genügend Informationen verfügen, damit Systemeigenschaften, z. b. **__PATH**, **__RELPATH**und **__SERVER**, nicht `null`werden. |
| `WBEM_FLAG_PROTOTYPE` | 2 | Dieses Flag wird für die Prototyperstellung verwendet. Die Abfrage wird nicht ausgeführt, sondern es wird ein Objekt zurückgegeben, das wie ein typisches Ergebnis Objekt aussieht. |
| `WBEM_FLAG_DIRECT_READ` | 0x200 | Bewirkt, dass der direkte Zugriff auf den Anbieter für die angegebene Klasse ohne Berücksichtigung der zugehörigen übergeordneten Klasse oder Unterklassen verursacht wird. |

Die empfohlenen Flags sind `WBEM_FLAG_RETURN_IMMEDIATELY` und `WBEM_FLAG_FORWARD_ONLY`, um eine optimale Leistung zu erzielen.

`pCtx`\
in In der Regel ist dieser Wert `null`. Andernfalls handelt es sich um einen Zeiger auf eine [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, der die angeforderten Klassen bereitstellt.

`ppEnum`\
vorgenommen Wenn kein Fehler auftritt, empfängt den Zeiger auf den Enumerator, der dem Aufrufer das Abrufen der Instanzen im Resultset der Abfrage ermöglicht. Die Abfrage kann ein Resultset mit 0 (null) Instanzen aufweisen. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".

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
| `WBEM_E_INVALID_QUERY` | 0x80041017 | Die Abfrage enthielt einen Syntax Fehler. |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | Die angeforderte Abfragesprache wird nicht unterstützt. |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | Die Abfrage ist zu komplex. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI wurde wahrscheinlich angehalten und neu gestartet. Ruft [connectserverwmi](connectserverwmi.md) erneut auf. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Fehler beim Remote Prozedur Aufruf (RPC)-Link zwischen dem aktuellen Prozess und WMI. |
| `WBEM_E_NOT_FOUND` | 0x80041002 angezeigt | Die Abfrage gibt eine Klasse an, die nicht vorhanden ist. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufzurufenden Befehl der [IWbemServices:: ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) -Methode.

Diese Funktion verarbeitet die im `strQuery`-Parameter angegebene Abfrage und erstellt einen Enumerator, über den der Aufrufer auf die Abfrageergebnisse zugreifen kann. Der Enumerator ist ein Zeiger auf eine [ienumwbemclassobject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) -Schnittstelle. die Abfrageergebnisse sind Instanzen von Klassen Objekten, die über die [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Schnittstelle verfügbar gemacht werden.

Es gibt Grenzwerte für die Anzahl der `AND`-und `OR` Schlüsselwörter, die in WQL-Abfragen verwendet werden können. Eine große Anzahl von WQL-Schlüsselwörtern, die in einer komplexen Abfrage verwendet werden, kann dazu führen, dass WMI den `WBEM_E_QUOTA_VIOLATION` Fehlercode (oder 0x8004106c) als `HRESULT` Wert zurückgibt. Das Limit von WQL-Schlüsselwörtern hängt von der Komplexität der Abfrage ab.

Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, indem Sie die [GetErrorInfo](geterrorinfo.md) -Funktion aufrufen.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** WMINet_Utils. idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
