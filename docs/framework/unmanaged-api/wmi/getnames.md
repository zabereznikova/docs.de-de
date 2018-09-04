---
title: GetNames-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion "GetNames" Ruft den Namen der Eigenschaften eines Objekts ab.
ms.date: 11/06/2017
api_name:
- GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetNames
helpviewer_keywords:
- GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f53174bf060938d5a55cbd196944ac11916d59cd
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43661393"
---
# <a name="getnames-function"></a><span data-ttu-id="d13e7-103">GetNames-Funktion</span><span class="sxs-lookup"><span data-stu-id="d13e7-103">GetNames function</span></span>
<span data-ttu-id="d13e7-104">Ruft eine Teilmenge oder alle Namen der Eigenschaften eines Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="d13e7-104">Retrieves either a subset or all of the names of the properties of an object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="d13e7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d13e7-105">Syntax</span></span>  
  
```  
HRESULT GetNames (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
); 
```  

## <a name="parameters"></a><span data-ttu-id="d13e7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d13e7-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="d13e7-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="d13e7-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="d13e7-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="d13e7-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="d13e7-109">[in] Ein Zeiger auf ein gültiges `LPCWSTR` , einen Qualifizierer-Namen, die ausgeführt wird als Teil eines Filters angibt.</span><span class="sxs-lookup"><span data-stu-id="d13e7-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="d13e7-110">Weitere Informationen finden Sie unter den ["Hinweise"](#remarks) Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="d13e7-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="d13e7-111">Dieser Parameter kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="d13e7-111">This parameter can be `null`.</span></span> 

`lFlags`  
<span data-ttu-id="d13e7-112">[in] Eine Kombination von Bitfeldern.</span><span class="sxs-lookup"><span data-stu-id="d13e7-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="d13e7-113">Weitere Informationen finden Sie unter den ["Hinweise"](#remarks) Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="d13e7-113">For more information, see the [Remarks](#remarks) section.</span></span>

`pQualifierValue`   
<span data-ttu-id="d13e7-114">[in] Ein Zeiger auf ein gültiges `VARIANT` -Struktur mit einem Filterwert initialisiert.</span><span class="sxs-lookup"><span data-stu-id="d13e7-114">[in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="d13e7-115">Dieser Parameter kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="d13e7-115">This parameter can be `null`.</span></span> 

`pstrNames`  
<span data-ttu-id="d13e7-116">[out] Ein `SAFEARRAY` Struktur, die Eigenschaftennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="d13e7-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="d13e7-117">Dieser Parameter muss bei einem Eintrag sein immer ein Zeiger auf `null`.</span><span class="sxs-lookup"><span data-stu-id="d13e7-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="d13e7-118">Finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="d13e7-118">See the [Remarks](#remarks) section for more information.</span></span> 

## <a name="return-value"></a><span data-ttu-id="d13e7-119">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d13e7-119">Return value</span></span>

<span data-ttu-id="d13e7-120">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="d13e7-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d13e7-121">Konstante</span><span class="sxs-lookup"><span data-stu-id="d13e7-121">Constant</span></span>  |<span data-ttu-id="d13e7-122">Wert</span><span class="sxs-lookup"><span data-stu-id="d13e7-122">Value</span></span>  |<span data-ttu-id="d13e7-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d13e7-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="d13e7-124">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="d13e7-124">0x80041001</span></span> | <span data-ttu-id="d13e7-125">Es wurde ein allgemeiner Fehler.</span><span class="sxs-lookup"><span data-stu-id="d13e7-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d13e7-126">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="d13e7-126">0x80041008</span></span> | <span data-ttu-id="d13e7-127">Eine oder mehrere Parameter sind ungültig, oder es wurde eine falsche Kombination von Flags und Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="d13e7-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="d13e7-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="d13e7-128">0x80041006</span></span> | <span data-ttu-id="d13e7-129">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d13e7-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="d13e7-130">0</span><span class="sxs-lookup"><span data-stu-id="d13e7-130">0</span></span> | <span data-ttu-id="d13e7-131">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="d13e7-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="d13e7-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d13e7-132">Remarks</span></span>

<span data-ttu-id="d13e7-133">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) Methode.</span><span class="sxs-lookup"><span data-stu-id="d13e7-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="d13e7-134">Der benannte zurückgegeben werden durch eine Kombination von Flags und Parameter gesteuert.</span><span class="sxs-lookup"><span data-stu-id="d13e7-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="d13e7-135">Die Funktion kann z. B. die Namen aller Eigenschaften oder nur die Namen der wichtigsten Eigenschaften zurück.</span><span class="sxs-lookup"><span data-stu-id="d13e7-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="d13e7-136">In der primäre Filter angegeben wird die `lFlags` Parameter und die anderen Parameter hängen sie.</span><span class="sxs-lookup"><span data-stu-id="d13e7-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="d13e7-137">Das Flag-Werte im `lFlags` Bitfelder werden</span><span class="sxs-lookup"><span data-stu-id="d13e7-137">The flag values in `lFlags` are bit fields</span></span>


<span data-ttu-id="d13e7-138">Die Flags, die als übergeben werden können die `lEnumFlags` Argument sind Bitfeldern, die in definierten die *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="d13e7-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="d13e7-139">Sie können einen Flag aus jeder Gruppe mit einem Flag aus einer anderen Gruppe kombinieren.</span><span class="sxs-lookup"><span data-stu-id="d13e7-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="d13e7-140">Allerdings sind Flags aus der gleichen Gruppe sich gegenseitig ausschließende.</span><span class="sxs-lookup"><span data-stu-id="d13e7-140">However, flags from the same group are mutually exclusive.</span></span> 

| <span data-ttu-id="d13e7-141">Gruppe 1-flags</span><span class="sxs-lookup"><span data-stu-id="d13e7-141">Group 1 flags</span></span> |<span data-ttu-id="d13e7-142">Wert</span><span class="sxs-lookup"><span data-stu-id="d13e7-142">Value</span></span>  |<span data-ttu-id="d13e7-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d13e7-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="d13e7-144">0</span><span class="sxs-lookup"><span data-stu-id="d13e7-144">0</span></span> | <span data-ttu-id="d13e7-145">Geben Sie bei allen Eigenschaftsnamen zurück.</span><span class="sxs-lookup"><span data-stu-id="d13e7-145">Return all property names.</span></span> <span data-ttu-id="d13e7-146">`strQualifierName` und `pQualifierVal` werden nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="d13e7-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="d13e7-147">1</span><span class="sxs-lookup"><span data-stu-id="d13e7-147">1</span></span> | <span data-ttu-id="d13e7-148">Nur Eigenschaften, die einen Qualifizierer, der den Namen trägt Zurückgeben der `strQualifierName` Parameter.</span><span class="sxs-lookup"><span data-stu-id="d13e7-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="d13e7-149">Wenn dieses Flag verwendet wird, müssen Sie angeben `strQualifierName`.</span><span class="sxs-lookup"><span data-stu-id="d13e7-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="d13e7-150">2</span><span class="sxs-lookup"><span data-stu-id="d13e7-150">2</span></span> |  <span data-ttu-id="d13e7-151">Zurückgeben von Eigenschaften, die nicht über einen Qualifizierer mit dem vom angegebenen Namen verfügen die `strQualifierName` Parameter.</span><span class="sxs-lookup"><span data-stu-id="d13e7-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="d13e7-152">Wenn dieses Flag verwendet wird, müssen Sie angeben `strQualifierName`.</span><span class="sxs-lookup"><span data-stu-id="d13e7-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="d13e7-153">3</span><span class="sxs-lookup"><span data-stu-id="d13e7-153">3</span></span> | <span data-ttu-id="d13e7-154">Nur Eigenschaften, die einen Qualifizierer, der den Namen trägt Zurückgeben der `wszQualifierName` Parameter und außerdem einen Wert, der identisch mit dem angegeben wird, indem die `pQualifierVal` Struktur.</span><span class="sxs-lookup"><span data-stu-id="d13e7-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="d13e7-155">Wenn dieses Flag verwendet wird, müssen Sie angeben, sowohl eine `wszQualifierName` und `pQualifierValue`.</span><span class="sxs-lookup"><span data-stu-id="d13e7-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="d13e7-156">Gruppe 2-flags</span><span class="sxs-lookup"><span data-stu-id="d13e7-156">Group 2 flags</span></span> |<span data-ttu-id="d13e7-157">Wert</span><span class="sxs-lookup"><span data-stu-id="d13e7-157">Value</span></span>  |<span data-ttu-id="d13e7-158">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d13e7-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="d13e7-159">0 x 4</span><span class="sxs-lookup"><span data-stu-id="d13e7-159">0x4</span></span> | <span data-ttu-id="d13e7-160">Zurückgeben Sie, nur die Namen der Eigenschaften, die die Schlüssel zu definieren.</span><span class="sxs-lookup"><span data-stu-id="d13e7-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="d13e7-161">0x8</span><span class="sxs-lookup"><span data-stu-id="d13e7-161">0x8</span></span> | <span data-ttu-id="d13e7-162">Rückgabe nur Eigenschaftennamen, die Objektverweise sind.</span><span class="sxs-lookup"><span data-stu-id="d13e7-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="d13e7-163">Gruppe 3-flags</span><span class="sxs-lookup"><span data-stu-id="d13e7-163">Group 3 flags</span></span> |<span data-ttu-id="d13e7-164">Wert</span><span class="sxs-lookup"><span data-stu-id="d13e7-164">Value</span></span>  |<span data-ttu-id="d13e7-165">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d13e7-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="d13e7-166">0x10</span><span class="sxs-lookup"><span data-stu-id="d13e7-166">0x10</span></span> | <span data-ttu-id="d13e7-167">Zurückgeben von nur für den Eigenschaftennamen, die am stärksten abgeleitete Klasse angehören.</span><span class="sxs-lookup"><span data-stu-id="d13e7-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="d13e7-168">Ausschließen von Eigenschaften aus der übergeordneten Klassen.</span><span class="sxs-lookup"><span data-stu-id="d13e7-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="d13e7-169">0x20</span><span class="sxs-lookup"><span data-stu-id="d13e7-169">0x20</span></span> | <span data-ttu-id="d13e7-170">Zurückgeben von nur für den Eigenschaftennamen, die die übergeordneten Klassen angehören.</span><span class="sxs-lookup"><span data-stu-id="d13e7-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="d13e7-171">0 x 30</span><span class="sxs-lookup"><span data-stu-id="d13e7-171">0x30</span></span> | <span data-ttu-id="d13e7-172">Geben Sie nur die Namen der Systemeigenschaften zurück.</span><span class="sxs-lookup"><span data-stu-id="d13e7-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="d13e7-173">0 x 40</span><span class="sxs-lookup"><span data-stu-id="d13e7-173">0x40</span></span> | <span data-ttu-id="d13e7-174">Geben Sie nur die Namen der Eigenschaften, die nicht zum System zurück.</span><span class="sxs-lookup"><span data-stu-id="d13e7-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="d13e7-175">Die Funktion weist immer einen neuen `SAFEARRAY` zurückgegeben `WBEM_S_NO_ERROR`, und `pstrNames` ist immer festgelegt, um darauf zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="d13e7-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="d13e7-176">Das zurückgegebene Array kann 0 Elemente verfügen, wenn keine Eigenschaften mit den angegebenen Filtern übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d13e7-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="d13e7-177">Wenn die Funktion einen Wert zurückgibt, die als `WBM_S_NO_ERROR`, ein neues `SAFEARRAY` Struktur wird nicht zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d13e7-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>
 
## <a name="requirements"></a><span data-ttu-id="d13e7-178">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d13e7-178">Requirements</span></span>  
 <span data-ttu-id="d13e7-179">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d13e7-179">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d13e7-180">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d13e7-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d13e7-181">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d13e7-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d13e7-182">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d13e7-182">See also</span></span>  
[<span data-ttu-id="d13e7-183">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="d13e7-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
