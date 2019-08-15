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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 681d7ce42b2b8d16353e4f5b3523f1a953a49d95
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037885"
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
in Der zähtertyp. Eine Liste der Leistungs Zählers finden Sie unter [WMI-Leistungsdaten Typen](/windows/desktop/WmiSdk/wmi-performance-counter-types). `dwCounterType`kann ein beliebiger zähtertyp `PERF_LARGE_RAW_FRACTION` mit `PERF_LARGE_RAW_BASE`Ausnahme von und sein. 

`dwFormat`\
in Das Format, in das die rohleistungs Daten konvertiert werden sollen. Dies kann einer der folgenden Werte sein:

|Konstante  |Wert  |Beschreibung |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | Gibt den berechneten Wert als Gleit Komma Wert mit doppelter Genauigkeit zurück. | 
| `PDH_FMT_LARGE` | 0x00000400 | Gibt den berechneten Wert als 64-Bit-Ganzzahl zurück. |
| `PDH_FMT_LONG` | 0x00000100 | Gibt den berechneten Wert als 32-Bit-Ganzzahl zurück. |

Einer der vorherigen Werte kann mit einem der folgenden Skalierungsflags ORed lauten:

|Konstante  |Wert  |Beschreibung |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | Wenden Sie die Skalierungsfaktoren des Zählers nicht an. |
| `PDH_FMT_1000` | 0x00002000 | Multiplizieren Sie den endgültigen Wert um 1.000. | 

`pTimeBase`\
in Ein Zeiger auf die Zeitbasis, falls dies für die Formatkonvertierung erforderlich ist. Wenn für die Formatkonvertierung keine Zeit Basisinformationen erforderlich sind, wird der Wert dieses Parameters ignoriert.

`pRawValue1`[in] ein Zeiger auf eine [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) -Struktur, die einen rohleistungs Wert darstellt.

`pRawValue2`\
in Ein Zeiger auf eine [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) -Struktur, die einen zweiten rohleistungs Wert darstellt. Wenn ein zweiter rohleistungs Wert nicht erforderlich ist, sollte dieser Parameter lauten `null`.

`pFmtValue`\
vorgenommen Ein Zeiger auf eine [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) -Struktur, die den formatierten Leistungswert empfängt.

## <a name="return-value"></a>Rückgabewert

Von dieser Funktion werden die folgenden Werte zurückgegeben:

|Konstante  |Wert  |Description  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | Der Funktions Aufrufvorgang ist erfolgreich. |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | Ein erforderliches Argument fehlt oder ist falsch. | 
| `PDH_INVALID_HANDLE` | 0xC0000BBC | Das Handle ist kein gültiges PDH-Objekt. |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufrufen der [formatfromrawvalue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) -Funktion.

## <a name="requirements"></a>Anforderungen

 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

 **Fern** PerfCounter.dll

 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
