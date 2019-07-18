---
title: CompareTo-Funktionen (Referenz zur nicht verwalteten API)
description: Die CompareTo-Funktion vergleicht ein Objekt in einen anderen WMI-Objekt.
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3566b9b8a3b4183f936c82c39c38dc5daa3aeae1
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636691"
---
# <a name="compareto-function"></a>CompareTo-Funktion

Vergleicht ein Objekt mit einem anderen Windows-Verwaltungsobjekt.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT CompareTo (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo
);
```

## <a name="parameters"></a>Parameter

`vFunc`\
[in] Dieser Parameter wird nicht verwendet.

`ptr`\
[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.

`flags`\
[in] Eine bitweise Kombination der Flags, die angeben, die Merkmale für den Vergleich zu berücksichtigen. Finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.

`pCompareTo`\
[in] Das Objekt für den Vergleich. `pCompareTo` muss ein gültiger [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz ist nicht möglich `null`.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Ein Unbekannter Fehler aufgetreten. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Einen zweiten Aufruf von `BeginEnumeration` wurde ohne einen zwischenzeitlichen Aufruf versucht [ `EndEnumeration` ](endenumeration.md). |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
| `WBEM_S_DIFFERENT` | 0x40003 | Die Objekte unterscheiden. |
| `WBEM_S_SAME` | 0 | Die Objekte sind gleich basierend auf die Vergleichsflags. |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) Methode.

Die Flags, die als übergeben werden können die `lEnumFlags` Argument definiert werden, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code. Sie können die einzelnen Eigenschaften, die im Vergleich zum angeben, indem eine bitweise Kombination der folgenden Flags angeben:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | 2 | Ignorieren Sie die Quelle (die Server und der Namespace, die von dem sie stammen). |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | 1 | Ignorieren Sie alle Qualifizierer (einschließlich **Schlüssel** und **dynamische**) |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | 4 | Ignorieren Sie die Standardwerte von Eigenschaften. Dieses Flag gilt nur für Vergleich von Klassen verwendet werden. |
| `WBEM_FLAG_IGNORE_FLAVOR` | 0x20 | Varianten von Qualifizierern ignoriert werden. Dieses Flag immer noch berücksichtigt Qualifizierer, aber ignoriert Flavor Unterschiede, z. B. weitergaberegeln und Einschränkungen beim Überschreiben. |
| `WBEM_FLAG_IGNORE_CASE` | 0x10 | Ignorieren von Groß-/Kleinschreibung im Vergleichen von Zeichenfolgenwerten. Dies gilt sowohl für Zeichenfolgen und Qualifiziererwerte. Beim Vergleich von Eigenschaften-und Qualifizierernamen wird immer Groß-/Kleinschreibung beachtet, unabhängig davon, ob dieses Flag festgelegt ist. |
| `WBEM_FLAG_IGNORE_CLASS` | 0x8 | Wird davon ausgegangen Sie, dass die verglichenen Objekte Instanzen derselben Klasse. Daher wird dieses Flag nur instanzbezogenen Informationen verglichen. Verwenden Sie diese Flags zum Optimieren der Leistung. Wenn die Objekte nicht von derselben Klasse vorhanden sind, sind die Ergebnisse nicht definiert. |

Oder Sie können einem einzigen zusammengesetzten Flag wie folgt angeben:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | 0 | Berücksichtigen Sie alle Features im Vergleich. |

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** WMINet_Utils.idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
