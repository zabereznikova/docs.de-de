---
title: FormatFromRawValue-Funktion (Referenz zur nicht verwalteten API)
description: Die FormatFromRawValue-Funktion konvertiert rohleistungsdaten in einem angegebenen Format.
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
ms.openlocfilehash: e0710b26237b350f1dfbc7d2464b7a131373604e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="formatfromrawvalue-function"></a>FormatFromRawValue-Funktion
Wenn die formatkonvertierung zeitbasierte ist ein Leistungszählers Datenwert in das angegebene Format oder zwei Leistungszählers Datenwerte konvertiert werden soll.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
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

`dwCounterType`  
[in] Der Leistungsindikator-Typ. Eine Liste der Indikatortypen, finden Sie unter [WMI Performance Counter Types](https://msdn.microsoft.com/library/aa394569(v=vs.85).aspx). `dwCounterType` kann alle Leistungsindikator vom Typ mit Ausnahme von `PERF_LARGE_RAW_FRACTION` und `PERF_LARGE_RAW_BASE`. 

`dwFormat`  
[in] Das Format, in dem die Daten für nicht formatierte Leistungsdaten zu konvertieren. Die folgenden Werte sind möglich:

|Konstante  |Wert  |Beschreibung |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | Geben Sie den berechneten Wert als einen Gleitkommawert mit doppelter Genauigkeit zurück. | 
| `PDH_FMT_LARGE` | 0x00000400 | Geben Sie den berechneten Wert als 64-Bit-Ganzzahl zurück. |
| `PDH_FMT_LONG` | 0x00000100 | Geben Sie den berechneten Wert als 32-Bit-Ganzzahl zurück. |

Die vorherigen Werte können ORed mit einem der folgenden Flags Skalierung möglich:

|Konstante  |Wert  |Beschreibung |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | Der Zähler Skalierungsfaktoren werden nicht angewendet werden. |
| `PDH_FMT_1000` | 0x00002000 | Multiplizieren Sie den endgültigen Wert von 1.000. | 

`pTimeBase`  
[in] Ein Zeiger auf die Zeitbasis, bei Bedarf für die formatkonvertierung. Wenn Basis Zeitinformationen nicht für die formatkonvertierung erforderlich ist, wird der Wert dieses Parameters ignoriert.

`pRawValue1` [in] Ein Zeiger auf eine [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) -Struktur, die einen Wert für nicht formatierte Leistungsdaten darstellt.

`pRawValue2` [in] Ein Zeiger auf eine [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) -Struktur, die einen zweiten Leistungszählers angibt. Dieser Parameter sollte sein, wenn ein zweiter Leistungszählers Wert nicht erforderlich ist, `null`.

`pFmtValue` [out] Ein Zeiger auf eine [ `PDH_FMT_COUNTERVALUE` ](https://msdn.microsoft.com/library/windows/desktop/aa373050(v=vs.85).aspx) -Struktur, die die formatierte Leistungswert empfängt.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte werden von dieser Funktion zurückgegeben:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | Der Funktionsaufruf ist erfolgreich. |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | Ein erforderliches Argument ist fehlt oder falsch. | 
| `PDH_INVALID_HANDLE` | 0xC0000BBC | Das Handle ist kein gültiges PDH-Objekt. |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [FormatFromRawValue](https://msdn.microsoft.com/library/ms231047(v=vs.85).aspx) Funktion.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Bibliothek:** PerfCounter.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
