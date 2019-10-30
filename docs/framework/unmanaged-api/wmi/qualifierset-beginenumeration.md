---
title: QualifierSet_BeginEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_BeginEnumeration-Funktion setzt einen Enumerator der Qualifizierer eines Objekts zurück.
ms.date: 11/06/2017
api_name:
- QualifierSet_BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_BeginEnumeration
helpviewer_keywords:
- QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 79edbd876fc9992f088b9adb159e005c735a72cb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127324"
---
# <a name="qualifierset_beginenumeration-function"></a>QualifierSet_BeginEnumeration-Funktion

Setzt einen Enumerator der Qualifizierer eines Objekts auf den Anfang der Enumeration zurück.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags
);
```

## <a name="parameters"></a>Parameter

`vFunc`\
in Dieser Parameter wird nicht verwendet.

`ptr`\
in Ein Zeiger auf eine [iwbemqualifierset](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) -Instanz.

`lFlags`\
in Eine bitweise Kombination der im Abschnitt " [Hinweise](#remarks) " beschriebenen Flags oder Werte, die die Qualifizierer angibt, die in der-Enumeration enthalten sein sollen.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Der `lFlags`-Parameter ist ungültig. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Es wurde ein zweiter `QualifierSet_BeginEnumeration` aufgerufen, ohne dass ein dazwischen befindender [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md)aufgerufen wurde. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu beginnen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufzurufenden Befehl der [iwbemqualifierset:: beginenumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) -Methode.

Um alle Qualifizierer eines Objekts aufzulisten, muss diese Methode vor dem ersten Aufruf von [QualifierSet_Next](qualifierset-next.md)aufgerufen werden. Die Reihenfolge, in der Qualifizierer aufgelistet werden, ist für eine bestimmte Enumeration garantiert invariante.

Die Flags, die als `lEnumFlags` Argument übermittelt werden können, werden in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren.

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|  | 0 | Gibt die Namen aller Qualifizierer zurück. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Gibt nur die Namen der Qualifizierer zurück, die speziell für die aktuelle Eigenschaft oder das aktuelle Objekt <br/> Für eine Eigenschaft: gibt nur die Qualifizierer zurück, die für die Eigenschaft spezifisch sind (einschließlich über schreibungen), nicht die Qualifizierer, die von der Klassendefinition weitergegeben werden <br/> Für eine-Instanz: gibt nur instanzspezifische Qualifizierernamen zurück. <br/> Für eine Klasse: gibt nur Qualifizierer zurück, die für die abgeleitete Klasse spezifisch sind.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | Gibt nur die Namen der Qualifizierer zurück, die von einem anderen-Objekt <br/> Für eine Eigenschaft: gibt nur die Qualifizierer zurück, die von der Klassendefinition an diese Eigenschaft weitergegeben werden, und nicht die der Eigenschaft selbst. <br/> Für eine Instanz: gibt nur die Qualifizierer zurück, die aus der Klassendefinition weitergegeben wurden <br/> Für eine Klasse: gibt nur die Qualifizierernamen zurück, die von den übergeordneten Klassen geerbt wurden. |

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** WMINet_Utils. idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
