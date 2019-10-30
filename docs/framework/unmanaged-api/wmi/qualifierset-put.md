---
title: QualifierSet_Put-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_Put-Funktion schreibt den benannten Qualifizierer und seinen Wert.
ms.date: 11/06/2017
api_name:
- QualifierSet_Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Put
helpviewer_keywords:
- QualifierSet_Put function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: a35025c6d16455a51b7b22d822ba77337ddd894a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120232"
---
# <a name="qualifierset_put-function"></a>QualifierSet_Put-Funktion

Schreibt den benannten Qualifizierer und den Wert. Der neue Qualifizierer überschreibt den vorherigen Wert desselben Namens. Wenn der Qualifizierer nicht vorhanden ist, wird er erstellt.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT QualifierSet_Put (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
);
```

## <a name="parameters"></a>Parameter

`vFunc`\
in Dieser Parameter wird nicht verwendet.

`ptr`\
in Ein Zeiger auf eine [iwbemqualifierset](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) -Instanz.

`wszName`\
in Der Name des Qualifizierers, der geschrieben werden soll.

`pVal`\
in Ein Zeiger auf einen gültigen `VARIANT`, der den Qualifizierer enthält, der geschrieben werden soll. Dieser Parameter kann nicht `null`werden.

`lFlavor`\
in Eine der folgenden Konstanten, die die gewünschten qualifizierervarianten für diesen Qualifizierer definiert. Der Standardwert ist `WBEM_FLAVOR_OVERRIDABLE` (0).

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | 0 | Der Qualifizierer kann in einer abgeleiteten Klasse oder Instanz überschrieben werden. **Dies ist der Standardwert.** |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | 1 | Der Qualifizierer wird an Instanzen weitergegeben. |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_DERIVED_CLASS` | 2 | Der Qualifizierer wird an abgeleitete Klassen weitergegeben. |
| `WBEM_FLAVOR_NOT_OVERRIDABLE` | 0x10 | Der Qualifizierer kann in einer abgeleiteten Klasse oder Instanz nicht überschrieben werden. |
| `WBEM_FLAVOR_AMENDED` | 0x80 | Der Qualifizierer ist lokalisiert. |

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | 0x8004101f | Es wurde ein unzulässiger Versuch unternommen, den **Schlüssel** Qualifizierer für eine Eigenschaft anzugeben, die kein Schlüssel sein kann. Die Schlüssel werden in der Klassendefinition für ein Objekt angegeben und können nicht pro Instanz geändert werden. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | 0x80041029 | Der `pVal`-Parameter ist kein gültiger qualifizierungstyp. |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | 0x8004101a | Es ist nicht möglich, die `QualifierSet_Put`-Methode für den Qualifizierer aufzurufen, da das besitzende Objekt keine über schreibungen zulässt. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufzurufenden Befehl der [iwbemqualifierset::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) -Methode.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** WMINet_Utils. idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
