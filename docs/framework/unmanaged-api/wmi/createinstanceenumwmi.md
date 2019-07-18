---
title: CreateInstanceEnumWmi-Funktion (Referenz zur nicht verwalteten API)
description: Die CreateInstanceEnumWmi-Funktion gibt einen Enumerator, mit der Instanzen einer bestimmten Klasse, die Volltextauswahlkriterien erfüllen zurück.
ms.date: 11/06/2017
api_name:
- CreateInstanceEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstanceEnumWmi
helpviewer_keywords:
- CreateInstanceEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db325296d85dc6d4780583731a6cab10fb884fd1
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636477"
---
# <a name="createinstanceenumwmi-function"></a>CreateInstanceEnumWmi-Funktion

Gibt einen Enumerator zurück, der die Instanzen einer bestimmten Klasse zurückgibt, die angegebene Auswahlkriterien erfüllen.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT CreateInstanceEnumWmi (
   [in] BSTR                    strFilter,
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

`strFilter`\
[in] Der Name der Klasse, für die Instanzen gewünscht werden. Dieser Parameter darf nicht sein `null`.

`lFlags`\
[in] Eine Kombination von Flags, die das Verhalten dieser Funktion zu beeinflussen. Die folgenden Werte werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Wenn festgelegt ist, die Funktion ruft ab, die ergänzende Qualifizierer, die in der lokalisierten Namespace des Gebietsschemas für die aktuelle Verbindung gespeichert. <br/> Wenn dies nicht festgelegt ist, die Funktion ruft nur die Qualifizierer, die in der unmittelbaren Namespace gespeichert. |
| `WBEM_FLAG_DEEP` | 0 | Die Enumeration enthält auch alle Unterklassen in der Hierarchie an. |
| `WBEM_FLAG_SHALLOW` | 1 | Die Enumeration enthält nur reine Instanzen dieser Klasse und schließt alle Instanzen von Unterklassen, die angeben von Eigenschaften, die in dieser Klasse nicht gefunden. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Das Flag wird halbsynchron aufgerufen. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | Die Funktion gibt einen Enumerator vorwärts gerichtete. In der Regel vorwärts-Enumeratoren sind schneller, und verwenden Sie weniger Arbeitsspeicher als konventionelle Enumeratoren, aber sie ermöglichen keine Aufrufe von [Klon](clone.md). |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI behält Zeiger auf Objekte in der Enumeration, bis sie freigegeben werden. |

Die empfohlene Flags sind `WBEM_FLAG_RETURN_IMMEDIATELY` und `WBEM_FLAG_FORWARD_ONLY` für eine optimale Leistung.

`pCtx`\
[in] Dieser Wert in der Regel ist `null`. Andernfalls wird ein Zeiger auf ein [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, die die angeforderten Instanzen bereitstellt.

`ppEnum`\
[out] Erhält der Zeiger auf den Enumerator.

`authLevel`\
[in] Die Autorisierungsebene.

`impLevel`\
[in] Die Ebene des Identitätswechsels.

`pCurrentNamespace`\
[in] Ein Zeiger auf ein [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) -Objekt, das den aktuellen Namespace darstellt.

`strUser`\
[in] Der Benutzername. Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.

`strPassword`\
[in] Das Kennwort. Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.

`strAuthority`\
[in] Der Domänenname des Benutzers. Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | Der Benutzer keine Berechtigung zum Anzeigen von Instanzen der angegebenen Klasse. |
| `WBEM_E_FAILED` | 0x80041001 | Ein Unbekannter Fehler aufgetreten. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | `strFilter` existiert nicht. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI wurde wahrscheinlich beendet und neu gestartet. Rufen Sie [ConnectServerWmi](connectserverwmi.md) erneut aus. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Der Remoteprozeduraufruf-Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-hat Fehler. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum) Methode.

Beachten Sie, dass der zurückgegebene Enumerator 0 (null) Elemente verfügen kann.

Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch den Aufruf der [GetErrorInfo](geterrorinfo.md) Funktion.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** WMINet_Utils.idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
