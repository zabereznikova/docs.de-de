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
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="cd017-103">FormatFromRawValue-Funktion</span><span class="sxs-lookup"><span data-stu-id="cd017-103">FormatFromRawValue function</span></span>
<span data-ttu-id="cd017-104">Konvertiert einen Rohdatenleistungswert in das angegebene Format oder zwei Rohdatenleistungswerte, wenn die Formatkonvertierung zeitabhängig ist.</span><span class="sxs-lookup"><span data-stu-id="cd017-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="cd017-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd017-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="cd017-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="cd017-106">Parameters</span></span>

`dwCounterType`\
<span data-ttu-id="cd017-107">[in] Der Zählertyp.</span><span class="sxs-lookup"><span data-stu-id="cd017-107">[in] The counter type.</span></span> <span data-ttu-id="cd017-108">Eine Liste der Leistungsindikatortypen finden Sie unter [WMI-Leistungszählertypen](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span><span class="sxs-lookup"><span data-stu-id="cd017-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="cd017-109">`dwCounterType`kann ein beliebiger `PERF_LARGE_RAW_FRACTION` Zählertyp mit Ausnahme von und `PERF_LARGE_RAW_BASE`sein.</span><span class="sxs-lookup"><span data-stu-id="cd017-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span>

`dwFormat`\
<span data-ttu-id="cd017-110">[in] Das Format, in das die Rohleistungsdaten konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cd017-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="cd017-111">Es kann sich um einen der folgenden Werte handeln:</span><span class="sxs-lookup"><span data-stu-id="cd017-111">It can be one of the following values:</span></span>

|<span data-ttu-id="cd017-112">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="cd017-112">Constant</span></span>  |<span data-ttu-id="cd017-113">value</span><span class="sxs-lookup"><span data-stu-id="cd017-113">Value</span></span>  |<span data-ttu-id="cd017-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd017-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="cd017-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="cd017-115">0x00000200</span></span> | <span data-ttu-id="cd017-116">Geben Sie den berechneten Wert als Gleitkommawert mit doppelter Genauigkeit zurück.</span><span class="sxs-lookup"><span data-stu-id="cd017-116">Return the calculated value as a double-precision floating point value.</span></span> |
| `PDH_FMT_LARGE` | <span data-ttu-id="cd017-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="cd017-117">0x00000400</span></span> | <span data-ttu-id="cd017-118">Geben Sie den berechneten Wert als 64-Bit-Ganzzahl zurück.</span><span class="sxs-lookup"><span data-stu-id="cd017-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="cd017-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="cd017-119">0x00000100</span></span> | <span data-ttu-id="cd017-120">Geben Sie den berechneten Wert als 32-Bit-Ganzzahl zurück.</span><span class="sxs-lookup"><span data-stu-id="cd017-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="cd017-121">Einer der vorherigen Werte kann ORed mit einem der folgenden Skalierungsflags sein:</span><span class="sxs-lookup"><span data-stu-id="cd017-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="cd017-122">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="cd017-122">Constant</span></span>  |<span data-ttu-id="cd017-123">value</span><span class="sxs-lookup"><span data-stu-id="cd017-123">Value</span></span>  |<span data-ttu-id="cd017-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd017-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="cd017-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="cd017-125">0x00001000</span></span> | <span data-ttu-id="cd017-126">Wenden Sie die Skalierungsfaktoren des Leistungsindikators nicht an.</span><span class="sxs-lookup"><span data-stu-id="cd017-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="cd017-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="cd017-127">0x00002000</span></span> | <span data-ttu-id="cd017-128">Multiplizieren Sie den Endwert mit 1.000.</span><span class="sxs-lookup"><span data-stu-id="cd017-128">Multiply the final value by 1,000.</span></span> |

`pTimeBase`\
<span data-ttu-id="cd017-129">[in] Ein Zeiger auf die Zeitbasis, falls erforderlich für die Formatkonvertierung.</span><span class="sxs-lookup"><span data-stu-id="cd017-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="cd017-130">Wenn zeitbasisviele Informationen für die Formatkonvertierung nicht erforderlich sind, wird der Wert dieses Parameters ignoriert.</span><span class="sxs-lookup"><span data-stu-id="cd017-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

`pRawValue1`\
<span data-ttu-id="cd017-131">[in] Ein Zeiger auf [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) eine Struktur, die einen rohen Leistungswert darstellt.</span><span class="sxs-lookup"><span data-stu-id="cd017-131">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a raw performance value.</span></span>

`pRawValue2`\
<span data-ttu-id="cd017-132">[in] Ein Zeiger auf [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) eine Struktur, die einen zweiten rohen Leistungswert darstellt.</span><span class="sxs-lookup"><span data-stu-id="cd017-132">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a second raw performance value.</span></span> <span data-ttu-id="cd017-133">Wenn kein zweiter unformatierter Leistungswert `null`erforderlich ist, sollte dieser Parameter .</span><span class="sxs-lookup"><span data-stu-id="cd017-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

`pFmtValue`\
<span data-ttu-id="cd017-134">[out] Ein Zeiger auf [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) eine Struktur, die den formatierten Leistungswert empfängt.</span><span class="sxs-lookup"><span data-stu-id="cd017-134">[out] A pointer to a [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="cd017-135">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cd017-135">Return value</span></span>

<span data-ttu-id="cd017-136">Die folgenden Werte werden von dieser Funktion zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="cd017-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="cd017-137">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="cd017-137">Constant</span></span>  |<span data-ttu-id="cd017-138">value</span><span class="sxs-lookup"><span data-stu-id="cd017-138">Value</span></span>  |<span data-ttu-id="cd017-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd017-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="cd017-140">0</span><span class="sxs-lookup"><span data-stu-id="cd017-140">0</span></span> | <span data-ttu-id="cd017-141">Der Funktionsaufruf ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="cd017-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="cd017-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="cd017-142">0xC0000BBD</span></span> | <span data-ttu-id="cd017-143">Ein erforderliches Argument fehlt oder ist falsch.</span><span class="sxs-lookup"><span data-stu-id="cd017-143">A required argument is missing or incorrect.</span></span> |
| `PDH_INVALID_HANDLE` | <span data-ttu-id="cd017-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="cd017-144">0xC0000BBC</span></span> | <span data-ttu-id="cd017-145">Das Handle ist kein gültiges PDH-Objekt.</span><span class="sxs-lookup"><span data-stu-id="cd017-145">The handle is not a valid PDH object.</span></span> |

## <a name="remarks"></a><span data-ttu-id="cd017-146">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cd017-146">Remarks</span></span>

<span data-ttu-id="cd017-147">Diese Funktion umschließt einen Aufruf der [FormatFromRawValue-Funktion.](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="cd017-147">This function wraps a call to the [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="cd017-148">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cd017-148">Requirements</span></span>

 <span data-ttu-id="cd017-149">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd017-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="cd017-150">**Bibliothek:** PerfCounter.dll</span><span class="sxs-lookup"><span data-stu-id="cd017-150">**Library:** PerfCounter.dll</span></span>

 <span data-ttu-id="cd017-151">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cd017-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cd017-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cd017-152">See also</span></span>

- [<span data-ttu-id="cd017-153">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="cd017-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
