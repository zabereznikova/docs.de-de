---
title: CompareTo-Funktion (Referenz zur nicht verwalteten API)
description: Die CompareTo-Funktion vergleicht ein Objekt mit einem anderen WMI-Objekt.
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
ms.openlocfilehash: 2ec42dff333422e247a11b4a3a5b9aed9bd316fa
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798770"
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
in Dieser Parameter wird nicht verwendet.

`ptr`\
in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.

`flags`\
in Eine bitweise Kombination der Flags, die die für den Vergleich zu berücksichtigenden Objekteigenschaften angeben. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".

`pCompareTo`\
in Das Objekt für den Vergleich. `pCompareTo`muss eine gültige [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz sein. der Wert kann `null`nicht sein.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Ein nicht angegebener Fehler ist aufgetreten. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Es `BeginEnumeration` wurde ein zweiter-Rückruf ohne einen dazwischen liegenden- [`EndEnumeration`](endenumeration.md)Rückruf durchgeführt. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
| `WBEM_S_DIFFERENT` | 0x40003 | Die Objekte unterscheiden sich. |
| `WBEM_S_SAME` | 0 | Die Objekte sind auf der Grundlage der Vergleichsflags identisch. |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject:: CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) -Methode.

Die Flags, die als `lEnumFlags` Argument übermittelt werden können, werden in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren. Sie können die einzelnen Merkmale des Vergleichs angeben, indem Sie eine bitweise Kombination der folgenden Flags angeben:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | 2 | Ignorieren Sie die Quelle (Server und Namespace, von denen Sie stammen). |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | 1 | Alle Qualifizierer ignorieren (einschließlich **Key** und **Dynamic**) |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | 4 | Standardwerte von Eigenschaften ignorieren. Dieses Flag gilt nur für den Vergleich von-Klassen. |
| `WBEM_FLAG_IGNORE_FLAVOR` | 0x20 | Qualifizierervarianten ignorieren. Dieses Flag berücksichtigt weiterhin Qualifizierer, ignoriert jedoch Unterschiede wie Weiterleitungs Regeln und Überschreibungs Einschränkungen. |
| `WBEM_FLAG_IGNORE_CASE` | 0x10 | Groß-/Kleinschreibung beim Vergleichen von Zeichen folgen Werten ignorieren Dies gilt sowohl für Zeichen folgen als auch für Qualifiziererwerte. Beim Vergleich von Eigenschaften-und Qualifizierernamen wird immer die Groß-/Kleinschreibung beachtet, unabhängig davon, ob dieses Flag festgelegt |
| `WBEM_FLAG_IGNORE_CLASS` | 0x8 | Angenommen, die Objekte, die verglichen werden, sind Instanzen derselben Klasse. Folglich vergleicht dieses Flag nur instanzbezogene Informationen. Verwenden Sie diese Flags, um die Leistung zu optimieren. Wenn die Objekte nicht der gleichen Klasse entsprechen, sind die Ergebnisse nicht definiert. |

Oder Sie können ein einzelnes zusammengesetztes Flag wie folgt angeben:

|Konstante  |Wert  |Description  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | 0 | Beachten Sie alle Features im Vergleich. |

## <a name="requirements"></a>Anforderungen

**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** WMINet_Utils.idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
