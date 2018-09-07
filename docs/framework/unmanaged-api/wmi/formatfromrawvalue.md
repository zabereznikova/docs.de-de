---
title: FormatFromRawValue-Funktion (Referenz zur nicht verwalteten API)
description: FormatFromRawValue-Funktion konvertiert rohleistungsdaten mehr in einem angegebenen Format.
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
ms.openlocfilehash: 95ef445d41672c5c2895bd7115afb6a73a57e8f9
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086136"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="aa572-103">FormatFromRawValue-Funktion</span><span class="sxs-lookup"><span data-stu-id="aa572-103">FormatFromRawValue function</span></span>
<span data-ttu-id="aa572-104">Konvertiert einen Rohdatenleistungswert in das angegebene Format oder zwei Rohdatenleistungswerte, wenn die Formatkonvertierung zeitabhängig ist.</span><span class="sxs-lookup"><span data-stu-id="aa572-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="aa572-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa572-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="aa572-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="aa572-106">Parameters</span></span>

`dwCounterType`  
<span data-ttu-id="aa572-107">[in] Der Leistungsindikator-Typ.</span><span class="sxs-lookup"><span data-stu-id="aa572-107">[in] The counter type.</span></span> <span data-ttu-id="aa572-108">Eine Liste der Indikatortypen, finden Sie unter [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span><span class="sxs-lookup"><span data-stu-id="aa572-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="aa572-109">`dwCounterType` kann jeder Typ Leistungsindikator, mit Ausnahme von sein `PERF_LARGE_RAW_FRACTION` und `PERF_LARGE_RAW_BASE`.</span><span class="sxs-lookup"><span data-stu-id="aa572-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span> 

`dwFormat`  
<span data-ttu-id="aa572-110">[in] Das Format, die die unformatierte Leistungsdaten konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="aa572-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="aa572-111">Es kann eine der folgenden Werte sein:</span><span class="sxs-lookup"><span data-stu-id="aa572-111">It can be one of the following values:</span></span>

|<span data-ttu-id="aa572-112">Konstante</span><span class="sxs-lookup"><span data-stu-id="aa572-112">Constant</span></span>  |<span data-ttu-id="aa572-113">Wert</span><span class="sxs-lookup"><span data-stu-id="aa572-113">Value</span></span>  |<span data-ttu-id="aa572-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa572-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="aa572-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="aa572-115">0x00000200</span></span> | <span data-ttu-id="aa572-116">Geben Sie den berechneten Wert als einen Gleitkommawert mit doppelter Genauigkeit zurück.</span><span class="sxs-lookup"><span data-stu-id="aa572-116">Return the calculated value as a double-precision floating point value.</span></span> | 
| `PDH_FMT_LARGE` | <span data-ttu-id="aa572-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="aa572-117">0x00000400</span></span> | <span data-ttu-id="aa572-118">Geben Sie den berechneten Wert als eine 64-Bit-Ganzzahl zurück.</span><span class="sxs-lookup"><span data-stu-id="aa572-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="aa572-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="aa572-119">0x00000100</span></span> | <span data-ttu-id="aa572-120">Geben Sie den berechneten Wert als eine 32-Bit-Ganzzahl zurück.</span><span class="sxs-lookup"><span data-stu-id="aa572-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="aa572-121">Die vorherigen Werte kann ORed mit einem der folgenden Flags, die Skalierung möglich:</span><span class="sxs-lookup"><span data-stu-id="aa572-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="aa572-122">Konstante</span><span class="sxs-lookup"><span data-stu-id="aa572-122">Constant</span></span>  |<span data-ttu-id="aa572-123">Wert</span><span class="sxs-lookup"><span data-stu-id="aa572-123">Value</span></span>  |<span data-ttu-id="aa572-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa572-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="aa572-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="aa572-125">0x00001000</span></span> | <span data-ttu-id="aa572-126">Skalierungsfaktoren des Zählers werden nicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="aa572-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="aa572-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="aa572-127">0x00002000</span></span> | <span data-ttu-id="aa572-128">Multiplizieren Sie den endgültigen Wert von 1.000 ein.</span><span class="sxs-lookup"><span data-stu-id="aa572-128">Multiply the final value by 1,000.</span></span> | 

`pTimeBase`  
<span data-ttu-id="aa572-129">[in] Ein Zeiger auf die Basis, bei Bedarf für die formatkonvertierung.</span><span class="sxs-lookup"><span data-stu-id="aa572-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="aa572-130">Wenn Basis Uhrzeitinformationen nicht für die formatkonvertierung erforderlich ist, wird der Wert dieses Parameters ignoriert.</span><span class="sxs-lookup"><span data-stu-id="aa572-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

<span data-ttu-id="aa572-131">`pRawValue1` [in] Ein Zeiger auf eine [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) -Struktur, die einen rohleistung-Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="aa572-131">`pRawValue1` [in] A pointer to a [`PDH_RAW_COUNTER`](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) structure that represents a raw performance value.</span></span>

<span data-ttu-id="aa572-132">`pRawValue2` [in] Ein Zeiger auf eine [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) Struktur, die einen zweiten rohleistung-Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="aa572-132">`pRawValue2` [in] A pointer to a [`PDH_RAW_COUNTER`](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) structure that represents a second raw performance value.</span></span> <span data-ttu-id="aa572-133">Dieser Parameter sollte sein, wenn Sie ein zweiter rohleistung bei der Wert nicht erforderlich ist, `null`.</span><span class="sxs-lookup"><span data-stu-id="aa572-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

<span data-ttu-id="aa572-134">`pFmtValue` [out] Ein Zeiger auf eine [ `PDH_FMT_COUNTERVALUE` ](https://msdn.microsoft.com/library/windows/desktop/aa373050(v=vs.85).aspx) Struktur, die dem Wert für die formatierte empfängt.</span><span class="sxs-lookup"><span data-stu-id="aa572-134">`pFmtValue` [out] A pointer to a [`PDH_FMT_COUNTERVALUE`](https://msdn.microsoft.com/library/windows/desktop/aa373050(v=vs.85).aspx) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="aa572-135">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="aa572-135">Return value</span></span>

<span data-ttu-id="aa572-136">Die folgenden Werte werden von dieser Funktion zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="aa572-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="aa572-137">Konstante</span><span class="sxs-lookup"><span data-stu-id="aa572-137">Constant</span></span>  |<span data-ttu-id="aa572-138">Wert</span><span class="sxs-lookup"><span data-stu-id="aa572-138">Value</span></span>  |<span data-ttu-id="aa572-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa572-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="aa572-140">0</span><span class="sxs-lookup"><span data-stu-id="aa572-140">0</span></span> | <span data-ttu-id="aa572-141">Der Funktionsaufruf ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="aa572-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="aa572-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="aa572-142">0xC0000BBD</span></span> | <span data-ttu-id="aa572-143">Ein erforderliches Argument ist nicht vorhanden oder falsch.</span><span class="sxs-lookup"><span data-stu-id="aa572-143">A required argument is missing or incorrect.</span></span> | 
| `PDH_INVALID_HANDLE` | <span data-ttu-id="aa572-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="aa572-144">0xC0000BBC</span></span> | <span data-ttu-id="aa572-145">Das Handle ist kein gültiges PDH-Objekt.</span><span class="sxs-lookup"><span data-stu-id="aa572-145">The handle is not a valid PDH object.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="aa572-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aa572-146">Remarks</span></span>

<span data-ttu-id="aa572-147">Diese Funktion umschließt einen Aufruf der [FormatFromRawValue](https://msdn.microsoft.com/library/ms231047(v=vs.85).aspx) Funktion.</span><span class="sxs-lookup"><span data-stu-id="aa572-147">This function wraps a call to the [FormatFromRawValue](https://msdn.microsoft.com/library/ms231047(v=vs.85).aspx) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="aa572-148">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aa572-148">Requirements</span></span>  
 <span data-ttu-id="aa572-149">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa572-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa572-150">**Bibliothek:** "PerfCounter.dll"</span><span class="sxs-lookup"><span data-stu-id="aa572-150">**Library:** PerfCounter.dll</span></span>  
  
 <span data-ttu-id="aa572-151">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="aa572-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa572-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa572-152">See also</span></span>  
[<span data-ttu-id="aa572-153">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="aa572-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
