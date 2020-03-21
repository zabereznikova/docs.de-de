---
title: QualifierSet_Next -Funktion (Nicht verwaltete API-Referenz)
description: Die QualifierSet_Next-Funktion ruft den nächsten Qualifizierer in einer Enumeration ab.
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: d3702426bc409d601ccfc6b7a8e93e8d9729c64e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174874"
---
# <a name="qualifierset_next-function"></a><span data-ttu-id="ea331-103">QualifierSet_Next-Funktion</span><span class="sxs-lookup"><span data-stu-id="ea331-103">QualifierSet_Next function</span></span>
<span data-ttu-id="ea331-104">Ruft den nächsten Qualifizierer in einer Enumeration ab, die durch einen Aufruf der [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)-Funktion gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="ea331-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ea331-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea331-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Next (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a><span data-ttu-id="ea331-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ea331-106">Parameters</span></span>

<span data-ttu-id="ea331-107">`vFunc`[in] Dieser Parameter ist nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="ea331-107">`vFunc` [in] This parameter is unused.</span></span>

<span data-ttu-id="ea331-108">`ptr`[in] Ein Zeiger auf eine [IWbemQualifierSet-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)</span><span class="sxs-lookup"><span data-stu-id="ea331-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="ea331-109">`lFlags`[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="ea331-109">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="ea331-110">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="ea331-110">This parameter must be 0.</span></span>

<span data-ttu-id="ea331-111">`pstrName`[out] Der Name des Qualifizierers.</span><span class="sxs-lookup"><span data-stu-id="ea331-111">`pstrName` [out] The name of the qualifier.</span></span> <span data-ttu-id="ea331-112">Wenn `null`, wird dieser Parameter ignoriert. andernfalls `pstrName` sollte nicht auf `BSTR` einen gültigen oder einen Speicherverlust hinweisen.</span><span class="sxs-lookup"><span data-stu-id="ea331-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="ea331-113">Wenn nicht null, weist die `BSTR` Funktion immer `WBEM_S_NO_ERROR`eine neue zu, wenn sie zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ea331-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

<span data-ttu-id="ea331-114">`pVal`[out] Wenn erfolgreich, der Wert für den Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="ea331-114">`pVal` [out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="ea331-115">Wenn die Funktion `VARIANT` fehlschlägt, `pVal` wird der spitz auf durch nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="ea331-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="ea331-116">Wenn dieser `null`Parameter ist , wird der Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ea331-116">If this parameter is `null`, the parameter is ignored.</span></span>

<span data-ttu-id="ea331-117">`plFlavor`[out] Ein Zeiger auf einen LONG, der die Qualifizierer-Variante erhält.</span><span class="sxs-lookup"><span data-stu-id="ea331-117">`plFlavor` [out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="ea331-118">Wenn Geschmacksinformationen nicht gewünscht werden, kann dieser Parameter . `null`</span><span class="sxs-lookup"><span data-stu-id="ea331-118">If flavor information is not desired, this parameter can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="ea331-119">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ea331-119">Return value</span></span>

<span data-ttu-id="ea331-120">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="ea331-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ea331-121">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="ea331-121">Constant</span></span>  |<span data-ttu-id="ea331-122">value</span><span class="sxs-lookup"><span data-stu-id="ea331-122">Value</span></span>  |<span data-ttu-id="ea331-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea331-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ea331-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ea331-124">0x80041008</span></span> | <span data-ttu-id="ea331-125">Ein Parameter ist nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="ea331-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="ea331-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="ea331-126">0x8004101d</span></span> | <span data-ttu-id="ea331-127">Der Anrufer hat [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)nicht angerufen.</span><span class="sxs-lookup"><span data-stu-id="ea331-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ea331-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ea331-128">0x80041006</span></span> | <span data-ttu-id="ea331-129">Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu starten.</span><span class="sxs-lookup"><span data-stu-id="ea331-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="ea331-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="ea331-130">0x40005</span></span> | <span data-ttu-id="ea331-131">In der Enumeration sind keine weiteren Qualifizierer mehr übrig.</span><span class="sxs-lookup"><span data-stu-id="ea331-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ea331-132">0</span><span class="sxs-lookup"><span data-stu-id="ea331-132">0</span></span> | <span data-ttu-id="ea331-133">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="ea331-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ea331-134">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ea331-134">Remarks</span></span>

<span data-ttu-id="ea331-135">Diese Funktion umschließt einen Aufruf der [IWbemQualifierSet::Next-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next)</span><span class="sxs-lookup"><span data-stu-id="ea331-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="ea331-136">Sie rufen `QualifierSet_Next` die Funktion wiederholt auf, um alle Qualifizierer aufzuzählen, bis die Funktion zurückkehrt. `WBEM_S_NO_MORE_DATA`</span><span class="sxs-lookup"><span data-stu-id="ea331-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="ea331-137">Um die Enumeration vorzeitig zu beenden, rufen Sie die [QualifierSet_EndEnumeration-Funktion](qualifierset-endenumeration.md) auf.</span><span class="sxs-lookup"><span data-stu-id="ea331-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="ea331-138">Die Reihenfolge der Qualifizierer, die während der Enumeration zurückgegeben werden, ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="ea331-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="ea331-139">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ea331-139">Requirements</span></span>  
 <span data-ttu-id="ea331-140">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea331-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea331-141">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ea331-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ea331-142">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ea331-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea331-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ea331-143">See also</span></span>

- [<span data-ttu-id="ea331-144">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="ea331-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
