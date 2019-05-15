---
title: QualifierSet_Put-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion QualifierSet_Put schreibt benannten Qualifizierers und seinen Wert.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 42bef9ab728af251b043e29af4cee9e5cb3f405d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636548"
---
# <a name="qualifiersetput-function"></a>QualifierSet_Put-Funktion

Schreibt den benannten Qualifizierer und den Wert. Der neue Qualifizierer wird den vorherigen Wert mit dem gleichen Namen überschrieben. Wenn Sie der Qualifizierer nicht vorhanden ist, wird es erstellt.

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
[in] Dieser Parameter wird nicht verwendet.

`ptr`\
[in] Ein Zeiger auf ein [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) Instanz.

`wszName`\
[in] Der Name des Qualifizierers schreiben.

`pVal`\
[in] Ein Zeiger auf ein gültiges `VARIANT` , enthält den Qualifizierer, der zu schreiben. Dieser Parameter darf nicht sein `null`.

`lFlavor`\
[in] Einer der folgenden Konstanten, die die gewünschten Qualifizierern für diesen Qualifizierer definiert. Der Standardwert ist `WBEM_FLAVOR_OVERRIDABLE` (0).

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | 0 | Der Qualifizierer kann in einer abgeleiteten Klasse oder Instanz überschrieben werden. **Dies ist der Standardwert.** |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | 1 | Der Qualifizierer wird an Instanzen weitergegeben. |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_DERIVED_CLASS` | 2 | Der Qualifizierer wird auf die abgeleitete Klassen weitergegeben. |
| `WBEM_FLAVOR_NOT_OVERRIDABLE` | 0x10 | Der Qualifizierer kann in einer abgeleiteten Klasse oder Instanz nicht überschrieben werden. |
| `WBEM_FLAVOR_AMENDED` | 0x80 | Der Qualifizierer wurde lokalisiert. |

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | 0x8004101f | Es wurde ein unzulässiger Versuch unternommen, an die **Schlüssel** Qualifizierer für eine Eigenschaft, die kein Schlüssel sein kann. Die Schlüssel werden angegeben. der c-Om; Ass-Definition für ein Objekt und können nicht individuell pro Instanz geändert werden. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | 0x80041029 | Die `pVal` Parameter ist nicht vom zulässiger Qualifizierertyp. |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | 0x8004101a | Es ist nicht möglich, zum Aufrufen der `QualifierSet_Put` Methode für den Qualifizierer überschreibt, da das besitzende Objekt nicht zulässig ist. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) Methode.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** WMINet_Utils.idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
