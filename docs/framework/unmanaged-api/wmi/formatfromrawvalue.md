---
title: FormatFromRawValue-Funktion (Nicht verwaltete API-Referenz)
description: Die FormatFromRawValue-Funktion konvertiert Rohleistungsdaten in ein angegebenes Format.
ms.date: 11/21/2017
api_name:
- FormatFromRawValue
api_location:
- PerfCounter.dll
api_type:
- DLLExport
f1_keywords:
- FormatFromRawValue
helpviewer_keywords:
- FormatFromRawValue function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 0a7c0b8387f0c8e2b6e2ade94f7efeede75bd758
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176837"
---
# <a name="formatfromrawvalue-function"></a>FormatFromRawValue-Funktion
Konvertiert einen Rohdatenleistungswert in das angegebene Format oder zwei Rohdatenleistungswerte, wenn die Formatkonvertierung zeitabhängig ist.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
int FormatFromRawValue (
   [in] uint                    dwCounterType,
   [in] uint                    dwFormat,
   [in] long*                   pTimeBase,
   [in] PDH_RAW_COUNTER*        pRawValue1,
   [in] PDH_RAW_COUNTER*        pRawValue2,
   [out] PDH_FMT_COUNTERVALUE*  pFmtValue
);
```

## <a name="parameters"></a>Parameter

`dwCounterType`\
[in] Der Zählertyp. Eine Liste der Leistungsindikatortypen finden Sie unter [WMI-Leistungszählertypen](/windows/desktop/WmiSdk/wmi-performance-counter-types). `dwCounterType`kann ein beliebiger `PERF_LARGE_RAW_FRACTION` Zählertyp mit Ausnahme von und `PERF_LARGE_RAW_BASE`sein.

`dwFormat`\
[in] Das Format, in das die Rohleistungsdaten konvertiert werden sollen. Es kann sich um einen der folgenden Werte handeln:

|Dauerhaft  |value  |Beschreibung |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | Geben Sie den berechneten Wert als Gleitkommawert mit doppelter Genauigkeit zurück. |
| `PDH_FMT_LARGE` | 0x00000400 | Geben Sie den berechneten Wert als 64-Bit-Ganzzahl zurück. |
| `PDH_FMT_LONG` | 0x00000100 | Geben Sie den berechneten Wert als 32-Bit-Ganzzahl zurück. |

Einer der vorherigen Werte kann ORed mit einem der folgenden Skalierungsflags sein:

|Dauerhaft  |value  |Beschreibung |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | Wenden Sie die Skalierungsfaktoren des Leistungsindikators nicht an. |
| `PDH_FMT_1000` | 0x00002000 | Multiplizieren Sie den Endwert mit 1.000. |

`pTimeBase`\
[in] Ein Zeiger auf die Zeitbasis, falls erforderlich für die Formatkonvertierung. Wenn zeitbasisviele Informationen für die Formatkonvertierung nicht erforderlich sind, wird der Wert dieses Parameters ignoriert.

`pRawValue1`\
[in] Ein Zeiger auf [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) eine Struktur, die einen rohen Leistungswert darstellt.

`pRawValue2`\
[in] Ein Zeiger auf [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) eine Struktur, die einen zweiten rohen Leistungswert darstellt. Wenn kein zweiter unformatierter Leistungswert `null`erforderlich ist, sollte dieser Parameter .

`pFmtValue`\
[out] Ein Zeiger auf [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) eine Struktur, die den formatierten Leistungswert empfängt.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte werden von dieser Funktion zurückgegeben:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | Der Funktionsaufruf ist erfolgreich. |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | Ein erforderliches Argument fehlt oder ist falsch. |
| `PDH_INVALID_HANDLE` | 0xC0000BBC | Das Handle ist kein gültiges PDH-Objekt. |

## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [FormatFromRawValue-Funktion.](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85))

## <a name="requirements"></a>Requirements (Anforderungen)

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

 **Bibliothek:** PerfCounter.dll

 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
