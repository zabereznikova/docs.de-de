---
title: Formatfromrawvalue-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion "formatfromrawvalue" konvertiert rohleistungs Daten in ein angegebenes Format.
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
ms.openlocfilehash: e7f3e4eef4a7e378529c2097a8fe1a753a98c961
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553713"
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
in Der zähtertyp. Eine Liste der Leistungs Zählers finden Sie unter [WMI-Leistungsdaten Typen](/windows/desktop/WmiSdk/wmi-performance-counter-types). `dwCounterType` kann ein beliebiger zähtertyp mit Ausnahme von `PERF_LARGE_RAW_FRACTION` und sein `PERF_LARGE_RAW_BASE` .

`dwFormat`\
in Das Format, in das die rohleistungs Daten konvertiert werden sollen. Es kann sich um einen der folgenden Werte handeln:

|Konstant  |Wert  |BESCHREIBUNG |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | Gibt den berechneten Wert als Gleit Komma Wert mit doppelter Genauigkeit zurück. |
| `PDH_FMT_LARGE` | 0x00000400 | Gibt den berechneten Wert als 64-Bit-Ganzzahl zurück. |
| `PDH_FMT_LONG` | 0x00000100 | Gibt den berechneten Wert als 32-Bit-Ganzzahl zurück. |

Einer der vorherigen Werte kann mit einem der folgenden Skalierungsflags ORed lauten:

|Konstant  |Wert  |BESCHREIBUNG |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | Wenden Sie die Skalierungsfaktoren des Zählers nicht an. |
| `PDH_FMT_1000` | 0x00002000 | Multiplizieren Sie den endgültigen Wert um 1.000. |

`pTimeBase`\
in Ein Zeiger auf die Zeitbasis, falls dies für die Formatkonvertierung erforderlich ist. Wenn für die Formatkonvertierung keine Zeit Basisinformationen erforderlich sind, wird der Wert dieses Parameters ignoriert.

`pRawValue1`\
in Ein Zeiger auf eine- [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) Struktur, die einen rohleistungs Wert darstellt.

`pRawValue2`\
in Ein Zeiger auf eine- [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) Struktur, die einen zweiten rohleistungs Wert darstellt. Wenn ein zweiter rohleistungs Wert nicht erforderlich ist, sollte dieser Parameter lauten `null` .

`pFmtValue`\
vorgenommen Ein Zeiger auf eine- [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) Struktur, die den formatierten Leistungswert empfängt.

## <a name="return-value"></a>Rückgabewert

Von dieser Funktion werden die folgenden Werte zurückgegeben:

|Konstant  |Wert  |BESCHREIBUNG  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | Der Funktions Aufrufvorgang ist erfolgreich. |
| `PDH_INVALID_ARGUMENT` | 0xc0000bbd | Ein erforderliches Argument fehlt oder ist falsch. |
| `PDH_INVALID_HANDLE` | 0xc0000bbc | Das Handle ist kein gültiges PDH-Objekt. |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufrufen der [formatfromrawvalue](/previous-versions/ms231047(v=vs.85)) -Funktion.

## <a name="requirements"></a>Anforderungen

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

 **Bibliothek:** PerfCounter.dll

 **.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
