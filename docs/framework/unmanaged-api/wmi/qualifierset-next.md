---
title: QualifierSet_Next-Funktion (Referenz zur nicht verwalteten API)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35ab5b64b3c7e364e0dd11c002b87a0a413f4335
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532434"
---
# <a name="qualifiersetnext-function"></a><span data-ttu-id="b741a-103">QualifierSet_Next-Funktion</span><span class="sxs-lookup"><span data-stu-id="b741a-103">QualifierSet_Next function</span></span>
<span data-ttu-id="b741a-104">Ruft den nächsten Qualifizierer in einer Enumeration ab, die durch einen Aufruf der [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)-Funktion gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="b741a-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="b741a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b741a-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="b741a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b741a-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="b741a-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="b741a-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="b741a-108">[in] Ein Zeiger auf ein [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) Instanz.</span><span class="sxs-lookup"><span data-stu-id="b741a-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`   
<span data-ttu-id="b741a-109">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="b741a-109">[in] Reserved.</span></span> <span data-ttu-id="b741a-110">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="b741a-110">This parameter must be 0.</span></span>

`pstrName`   
<span data-ttu-id="b741a-111">[out] Der Name des Qualifizierers.</span><span class="sxs-lookup"><span data-stu-id="b741a-111">[out] The name of the qualifier.</span></span> <span data-ttu-id="b741a-112">Wenn `null`, dieser Parameter wird ignoriert, andernfalls `pstrName` sollten verweist nicht auf einen gültigen `BSTR` oder ein Speicherverlust auftritt.</span><span class="sxs-lookup"><span data-stu-id="b741a-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="b741a-113">Wenn nicht null ist, die Funktion immer eine neue zuordnet `BSTR` Wenn gibt `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="b741a-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

`pVal`   
<span data-ttu-id="b741a-114">[out] Bei erfolgreicher Ausführung der Wert für den Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="b741a-114">[out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="b741a-115">Wenn die Funktion fehlschlägt, die `VARIANT` verweist `pVal` wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="b741a-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="b741a-116">Wenn dieser Parameter ist `null`, der Parameter wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="b741a-116">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="b741a-117">[out] Ein Zeiger auf einen Long-Wert, der die Qualifizierertyp empfängt.</span><span class="sxs-lookup"><span data-stu-id="b741a-117">[out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="b741a-118">Dieser Parameter kann sein, wenn der Typ-Informationen nicht gewünscht ist, `null`.</span><span class="sxs-lookup"><span data-stu-id="b741a-118">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="b741a-119">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b741a-119">Return value</span></span>

<span data-ttu-id="b741a-120">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="b741a-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b741a-121">Konstante</span><span class="sxs-lookup"><span data-stu-id="b741a-121">Constant</span></span>  |<span data-ttu-id="b741a-122">Wert</span><span class="sxs-lookup"><span data-stu-id="b741a-122">Value</span></span>  |<span data-ttu-id="b741a-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b741a-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b741a-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b741a-124">0x80041008</span></span> | <span data-ttu-id="b741a-125">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="b741a-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="b741a-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="b741a-126">0x8004101d</span></span> | <span data-ttu-id="b741a-127">Der Aufrufer nicht aufrufen [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="b741a-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b741a-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="b741a-128">0x80041006</span></span> | <span data-ttu-id="b741a-129">Es ist nicht genügend Arbeitsspeicher zur Verfügung, um eine neue Enumeration beginnen.</span><span class="sxs-lookup"><span data-stu-id="b741a-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="b741a-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="b741a-130">0x40005</span></span> | <span data-ttu-id="b741a-131">Keine weitere Qualifizierer bleiben in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="b741a-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b741a-132">0</span><span class="sxs-lookup"><span data-stu-id="b741a-132">0</span></span> | <span data-ttu-id="b741a-133">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="b741a-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="b741a-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b741a-134">Remarks</span></span>

<span data-ttu-id="b741a-135">Diese Funktion umschließt einen Aufruf der [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) Methode.</span><span class="sxs-lookup"><span data-stu-id="b741a-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="b741a-136">Rufen Sie die `QualifierSet_Next` Funktion mehrmals, um alle Qualifizierer erst die Funktionsrückgabe aufzählen `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="b741a-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="b741a-137">Um die Enumeration zu einem frühen Zeitpunkt zu beenden, rufen Sie die [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="b741a-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="b741a-138">Die Reihenfolge der Qualifizierer, die zurückgegeben werden, während der Enumeration ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="b741a-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="b741a-139">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b741a-139">Requirements</span></span>  
 <span data-ttu-id="b741a-140">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b741a-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b741a-141">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b741a-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b741a-142">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b741a-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b741a-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b741a-143">See also</span></span>
- [<span data-ttu-id="b741a-144">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="b741a-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
