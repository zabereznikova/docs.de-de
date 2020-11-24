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
ms.openlocfilehash: e678aca5baf82c07ec9fc5c85cef22630af5ab0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672330"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="f0c4c-103">FormatFromRawValue-Funktion</span><span class="sxs-lookup"><span data-stu-id="f0c4c-103">FormatFromRawValue function</span></span>

<span data-ttu-id="f0c4c-104">Konvertiert einen Rohdatenleistungswert in das angegebene Format oder zwei Rohdatenleistungswerte, wenn die Formatkonvertierung zeitabhängig ist.</span><span class="sxs-lookup"><span data-stu-id="f0c4c-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="f0c4c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0c4c-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="f0c4c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f0c4c-106">Parameters</span></span>

`dwCounterType`\
<span data-ttu-id="f0c4c-107">in Der zähtertyp.</span><span class="sxs-lookup"><span data-stu-id="f0c4c-107">[in] The counter type.</span></span> <span data-ttu-id="f0c4c-108">Eine Liste der Leistungs Zählers finden Sie unter [WMI-Leistungsdaten Typen](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span><span class="sxs-lookup"><span data-stu-id="f0c4c-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="f0c4c-109">`dwCounterType` kann ein beliebiger zähtertyp mit Ausnahme von `PERF_LARGE_RAW_FRACTION` und sein `PERF_LARGE_RAW_BASE` .</span><span class="sxs-lookup"><span data-stu-id="f0c4c-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span>

`dwFormat`\
<span data-ttu-id="f0c4c-110">in Das Format, in das die rohleistungs Daten konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f0c4c-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="f0c4c-111">Es kann sich um einen der folgenden Werte handeln:</span><span class="sxs-lookup"><span data-stu-id="f0c4c-111">It can be one of the following values:</span></span>

|<span data-ttu-id="f0c4c-112">Konstante</span><span class="sxs-lookup"><span data-stu-id="f0c4c-112">Constant</span></span>  |<span data-ttu-id="f0c4c-113">Wert</span><span class="sxs-lookup"><span data-stu-id="f0c4c-113">Value</span></span>  |<span data-ttu-id="f0c4c-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f0c4c-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="f0c4c-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="f0c4c-115">0x00000200</span></span> | <span data-ttu-id="f0c4c-116">Gibt den berechneten Wert als Gleit Komma Wert mit doppelter Genauigkeit zurück.</span><span class="sxs-lookup"><span data-stu-id="f0c4c-116">Return the calculated value as a double-precision floating point value.</span></span> |
| `PDH_FMT_LARGE` | <span data-ttu-id="f0c4c-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="f0c4c-117">0x00000400</span></span> | <span data-ttu-id="f0c4c-118">Gibt den berechneten Wert als 64-Bit-Ganzzahl zurück.</span><span class="sxs-lookup"><span data-stu-id="f0c4c-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="f0c4c-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="f0c4c-119">0x00000100</span></span> | <span data-ttu-id="f0c4c-120">Gibt den berechneten Wert als 32-Bit-Ganzzahl zurück.</span><span class="sxs-lookup"><span data-stu-id="f0c4c-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="f0c4c-121">Einer der vorherigen Werte kann mit einem der folgenden Skalierungsflags ORed lauten:</span><span class="sxs-lookup"><span data-stu-id="f0c4c-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="f0c4c-122">Konstante</span><span class="sxs-lookup"><span data-stu-id="f0c4c-122">Constant</span></span>  |<span data-ttu-id="f0c4c-123">Wert</span><span class="sxs-lookup"><span data-stu-id="f0c4c-123">Value</span></span>  |<span data-ttu-id="f0c4c-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f0c4c-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="f0c4c-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="f0c4c-125">0x00001000</span></span> | <span data-ttu-id="f0c4c-126">Wenden Sie die Skalierungsfaktoren des Zählers nicht an.</span><span class="sxs-lookup"><span data-stu-id="f0c4c-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="f0c4c-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="f0c4c-127">0x00002000</span></span> | <span data-ttu-id="f0c4c-128">Multiplizieren Sie den endgültigen Wert um 1.000.</span><span class="sxs-lookup"><span data-stu-id="f0c4c-128">Multiply the final value by 1,000.</span></span> |

`pTimeBase`\
<span data-ttu-id="f0c4c-129">in Ein Zeiger auf die Zeitbasis, falls dies für die Formatkonvertierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f0c4c-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="f0c4c-130">Wenn für die Formatkonvertierung keine Zeit Basisinformationen erforderlich sind, wird der Wert dieses Parameters ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f0c4c-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

`pRawValue1`\
<span data-ttu-id="f0c4c-131">in Ein Zeiger auf eine- [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) Struktur, die einen rohleistungs Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="f0c4c-131">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a raw performance value.</span></span>

`pRawValue2`\
<span data-ttu-id="f0c4c-132">in Ein Zeiger auf eine- [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) Struktur, die einen zweiten rohleistungs Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="f0c4c-132">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a second raw performance value.</span></span> <span data-ttu-id="f0c4c-133">Wenn ein zweiter rohleistungs Wert nicht erforderlich ist, sollte dieser Parameter lauten `null` .</span><span class="sxs-lookup"><span data-stu-id="f0c4c-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

`pFmtValue`\
<span data-ttu-id="f0c4c-134">vorgenommen Ein Zeiger auf eine- [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) Struktur, die den formatierten Leistungswert empfängt.</span><span class="sxs-lookup"><span data-stu-id="f0c4c-134">[out] A pointer to a [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="f0c4c-135">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f0c4c-135">Return value</span></span>

<span data-ttu-id="f0c4c-136">Von dieser Funktion werden die folgenden Werte zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="f0c4c-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="f0c4c-137">Konstante</span><span class="sxs-lookup"><span data-stu-id="f0c4c-137">Constant</span></span>  |<span data-ttu-id="f0c4c-138">Wert</span><span class="sxs-lookup"><span data-stu-id="f0c4c-138">Value</span></span>  |<span data-ttu-id="f0c4c-139">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f0c4c-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="f0c4c-140">0</span><span class="sxs-lookup"><span data-stu-id="f0c4c-140">0</span></span> | <span data-ttu-id="f0c4c-141">Der Funktions Aufrufvorgang ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="f0c4c-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="f0c4c-142">0xc0000bbd</span><span class="sxs-lookup"><span data-stu-id="f0c4c-142">0xC0000BBD</span></span> | <span data-ttu-id="f0c4c-143">Ein erforderliches Argument fehlt oder ist falsch.</span><span class="sxs-lookup"><span data-stu-id="f0c4c-143">A required argument is missing or incorrect.</span></span> |
| `PDH_INVALID_HANDLE` | <span data-ttu-id="f0c4c-144">0xc0000bbc</span><span class="sxs-lookup"><span data-stu-id="f0c4c-144">0xC0000BBC</span></span> | <span data-ttu-id="f0c4c-145">Das Handle ist kein gültiges PDH-Objekt.</span><span class="sxs-lookup"><span data-stu-id="f0c4c-145">The handle is not a valid PDH object.</span></span> |

## <a name="remarks"></a><span data-ttu-id="f0c4c-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0c4c-146">Remarks</span></span>

<span data-ttu-id="f0c4c-147">Diese Funktion umschließt einen Aufrufen der [formatfromrawvalue](/previous-versions/ms231047(v=vs.85)) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="f0c4c-147">This function wraps a call to the [FormatFromRawValue](/previous-versions/ms231047(v=vs.85)) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="f0c4c-148">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f0c4c-148">Requirements</span></span>

 <span data-ttu-id="f0c4c-149">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0c4c-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="f0c4c-150">**Bibliothek:** PerfCounter.dll</span><span class="sxs-lookup"><span data-stu-id="f0c4c-150">**Library:** PerfCounter.dll</span></span>

 <span data-ttu-id="f0c4c-151">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f0c4c-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f0c4c-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0c4c-152">See also</span></span>

- [<span data-ttu-id="f0c4c-153">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="f0c4c-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
