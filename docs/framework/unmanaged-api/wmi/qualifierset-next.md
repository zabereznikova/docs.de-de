---
title: QualifierSet_Next-Funktion (Referenz zur nicht verwalteten API)
description: "Die QualifierSet_Next-Funktion ruft den nächsten Qualifizierer in einer Enumeration ab."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_Next
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_Next
helpviewer_keywords: QualifierSet_Next function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6b66eeab2cba18268b602350c8bc8f489d943309
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetnext-function"></a><span data-ttu-id="06569-103">QualifierSet_Next-Funktion</span><span class="sxs-lookup"><span data-stu-id="06569-103">QualifierSet_Next function</span></span>
<span data-ttu-id="06569-104">Ruft den nächsten Qualifizierer in einer Enumeration, die durch einen Aufruf gestartet der [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="06569-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="06569-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="06569-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Next (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,        
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a><span data-ttu-id="06569-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="06569-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="06569-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="06569-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="06569-108">[in] Ein Zeiger auf ein [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="06569-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`lFlags`   
<span data-ttu-id="06569-109">[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="06569-109">[in] Reserved.</span></span> <span data-ttu-id="06569-110">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="06569-110">This parameter must be 0.</span></span>

`pstrName`   
<span data-ttu-id="06569-111">[out] Der Name des Qualifizierers.</span><span class="sxs-lookup"><span data-stu-id="06569-111">[out] The name of the qualifier.</span></span> <span data-ttu-id="06569-112">Wenn `null`, dieser Parameter wird ignoriert, andernfalls `pstrName` sollte nicht auf eine gültige verweisen `BSTR` oder tritt ein Speicherverlust auf.</span><span class="sxs-lookup"><span data-stu-id="06569-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="06569-113">Wenn nicht null ist, die Funktion immer ein neues ordnet `BSTR` bei Rückgabe `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="06569-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

`pVal`   
<span data-ttu-id="06569-114">[out] Bei erfolgreicher Ausführung der Wert für den Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="06569-114">[out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="06569-115">Wenn die Funktion fehlschlägt, die `VARIANT` verweist `pVal` wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="06569-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="06569-116">Wenn dieser Parameter ist `null`, der Parameter wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="06569-116">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="06569-117">[out] Ein Zeiger auf einen Long-Wert, der die Qualifizierertyp empfängt.</span><span class="sxs-lookup"><span data-stu-id="06569-117">[out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="06569-118">Dieser Parameter kann sein, wenn Flavor-Informationen nicht erwünscht ist, `null`.</span><span class="sxs-lookup"><span data-stu-id="06569-118">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="06569-119">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="06569-119">Return value</span></span>

<span data-ttu-id="06569-120">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="06569-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="06569-121">Konstante</span><span class="sxs-lookup"><span data-stu-id="06569-121">Constant</span></span>  |<span data-ttu-id="06569-122">Wert</span><span class="sxs-lookup"><span data-stu-id="06569-122">Value</span></span>  |<span data-ttu-id="06569-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="06569-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="06569-124">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="06569-124">0x80041008</span></span> | <span data-ttu-id="06569-125">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="06569-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="06569-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="06569-126">0x8004101d</span></span> | <span data-ttu-id="06569-127">Der Aufrufer nicht aufrufen [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="06569-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="06569-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="06569-128">0x80041006</span></span> | <span data-ttu-id="06569-129">Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="06569-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="06569-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="06569-130">0x40005</span></span> | <span data-ttu-id="06569-131">Keine weitere Qualifizierer befinden sich in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="06569-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="06569-132">0</span><span class="sxs-lookup"><span data-stu-id="06569-132">0</span></span> | <span data-ttu-id="06569-133">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="06569-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="06569-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="06569-134">Remarks</span></span>

<span data-ttu-id="06569-135">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemQualifierSet::Next](https://msdn.microsoft.com/library/aa391870(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="06569-135">This function wraps a call to the [IWbemQualifierSet::Next](https://msdn.microsoft.com/library/aa391870(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="06569-136">Rufen Sie die `QualifierSet_Next` Funktion mehrmals, um alle Qualifizierer erst die Funktionsrückgabe aufzählen `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="06569-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="06569-137">Um die Enumeration frühzeitig zu beenden, rufen Sie die [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="06569-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="06569-138">Die Reihenfolge der Qualifizierer, die zurückgegeben werden, während der Enumeration ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="06569-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="06569-139">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="06569-139">Requirements</span></span>  
 <span data-ttu-id="06569-140">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06569-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06569-141">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="06569-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="06569-142">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="06569-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06569-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06569-143">See also</span></span>  
[<span data-ttu-id="06569-144">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="06569-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
