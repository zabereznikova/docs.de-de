---
title: GetNames-Funktion (Nicht verwaltete API-Referenz)
description: Die GetNames-Funktion ruft die Namen der Eigenschaften eines Objekts ab.
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
ms.openlocfilehash: 449f0ce9c291d4bbcad4947214e56ff46f55beed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174952"
---
# <a name="getnames-function"></a><span data-ttu-id="81946-103">GetNames-Funktion</span><span class="sxs-lookup"><span data-stu-id="81946-103">GetNames function</span></span>
<span data-ttu-id="81946-104">Ruft eine Teilmenge oder alle Namen der Eigenschaften eines Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="81946-104">Retrieves either a subset or all of the names of the properties of an object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="81946-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="81946-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNames (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
);
```  

## <a name="parameters"></a><span data-ttu-id="81946-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="81946-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="81946-107">[in] Dieser Parameter ist nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="81946-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="81946-108">[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="81946-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="81946-109">[in] Ein Zeiger auf `LPCWSTR` einen gültigen, der einen Qualifizierernamen angibt, der als Teil eines Filters funktioniert.</span><span class="sxs-lookup"><span data-stu-id="81946-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="81946-110">Weitere Informationen finden Sie im Abschnitt ["Bemerkungen".](#remarks)</span><span class="sxs-lookup"><span data-stu-id="81946-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="81946-111">Dieser Parameter kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="81946-111">This parameter can be `null`.</span></span>

`lFlags`  
<span data-ttu-id="81946-112">[in] Eine Kombination von Bitfeldern.</span><span class="sxs-lookup"><span data-stu-id="81946-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="81946-113">Weitere Informationen finden Sie im Abschnitt ["Bemerkungen".](#remarks)</span><span class="sxs-lookup"><span data-stu-id="81946-113">For more information, see the [Remarks](#remarks) section.</span></span>

<span data-ttu-id="81946-114">`pQualifierValue`[in] Ein Zeiger auf `VARIANT` eine gültige Struktur, die auf einen Filterwert initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="81946-114">`pQualifierValue` [in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="81946-115">Dieser Parameter kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="81946-115">This parameter can be `null`.</span></span>

`pstrNames`  
<span data-ttu-id="81946-116">[out] Eine `SAFEARRAY` Struktur, die Eigenschaftsnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="81946-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="81946-117">Bei der Eingabe muss dieser Parameter `null`immer ein Zeiger auf sein.</span><span class="sxs-lookup"><span data-stu-id="81946-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="81946-118">Weitere Informationen finden Sie im Abschnitt ["Bemerkungen".](#remarks)</span><span class="sxs-lookup"><span data-stu-id="81946-118">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="81946-119">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="81946-119">Return value</span></span>

<span data-ttu-id="81946-120">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="81946-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="81946-121">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="81946-121">Constant</span></span>  |<span data-ttu-id="81946-122">value</span><span class="sxs-lookup"><span data-stu-id="81946-122">Value</span></span>  |<span data-ttu-id="81946-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81946-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="81946-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="81946-124">0x80041001</span></span> | <span data-ttu-id="81946-125">Es ist ein allgemeines Versagen aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="81946-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="81946-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="81946-126">0x80041008</span></span> | <span data-ttu-id="81946-127">Mindestens ein Parameter ist ungültig, oder es wurde eine falsche Kombination von Flags und Parametern angegeben.</span><span class="sxs-lookup"><span data-stu-id="81946-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="81946-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="81946-128">0x80041006</span></span> | <span data-ttu-id="81946-129">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="81946-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="81946-130">0</span><span class="sxs-lookup"><span data-stu-id="81946-130">0</span></span> | <span data-ttu-id="81946-131">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="81946-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="81946-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="81946-132">Remarks</span></span>

<span data-ttu-id="81946-133">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetNames-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames)</span><span class="sxs-lookup"><span data-stu-id="81946-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="81946-134">Die zurückgegebenen Namen werden durch eine Kombination von Flags und Parametern gesteuert.</span><span class="sxs-lookup"><span data-stu-id="81946-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="81946-135">Beispielsweise kann die Funktion die Namen aller Eigenschaften oder nur die Namen der Schlüsseleigenschaften zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="81946-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="81946-136">Der primäre Filter wird `lFlags` im Parameter angegeben, und die anderen Parameter variieren je danach.</span><span class="sxs-lookup"><span data-stu-id="81946-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="81946-137">Die Flagwerte `lFlags` in sind Bitfelder</span><span class="sxs-lookup"><span data-stu-id="81946-137">The flag values in `lFlags` are bit fields</span></span>

<span data-ttu-id="81946-138">Die Flags, die `lEnumFlags` als Argument übergeben werden können, sind Bitfelder, die in der *Headerdatei WbemCli.h* definiert sind, oder Sie können sie als Konstanten im Code definieren.</span><span class="sxs-lookup"><span data-stu-id="81946-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="81946-139">Sie können ein Flag aus jeder Gruppe mit einem beliebigen Flag aus einer anderen Gruppe kombinieren.</span><span class="sxs-lookup"><span data-stu-id="81946-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="81946-140">Flags derselben Gruppe schließen sich jedoch gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="81946-140">However, flags from the same group are mutually exclusive.</span></span>

| <span data-ttu-id="81946-141">Flagge der Gruppe 1</span><span class="sxs-lookup"><span data-stu-id="81946-141">Group 1 flags</span></span> |<span data-ttu-id="81946-142">value</span><span class="sxs-lookup"><span data-stu-id="81946-142">Value</span></span>  |<span data-ttu-id="81946-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81946-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="81946-144">0</span><span class="sxs-lookup"><span data-stu-id="81946-144">0</span></span> | <span data-ttu-id="81946-145">Gibt alle Eigenschaftsnamen zurück.</span><span class="sxs-lookup"><span data-stu-id="81946-145">Return all property names.</span></span> <span data-ttu-id="81946-146">`strQualifierName`und `pQualifierVal` ungenutzt sind.</span><span class="sxs-lookup"><span data-stu-id="81946-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="81946-147">1</span><span class="sxs-lookup"><span data-stu-id="81946-147">1</span></span> | <span data-ttu-id="81946-148">Geben Sie nur Eigenschaften zurück, die `strQualifierName` über einen Qualifizierer des durch den Parameter angegebenen Namens verfügen.</span><span class="sxs-lookup"><span data-stu-id="81946-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="81946-149">Wenn dieses Flag verwendet wird, müssen Sie angeben. `strQualifierName`</span><span class="sxs-lookup"><span data-stu-id="81946-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="81946-150">2</span><span class="sxs-lookup"><span data-stu-id="81946-150">2</span></span> |  <span data-ttu-id="81946-151">Geben Sie nur Eigenschaften zurück, die keinen `strQualifierName` Qualifizierer des durch den Parameter angegebenen Namens haben.</span><span class="sxs-lookup"><span data-stu-id="81946-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="81946-152">Wenn dieses Flag verwendet wird, müssen Sie angeben. `strQualifierName`</span><span class="sxs-lookup"><span data-stu-id="81946-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="81946-153">3</span><span class="sxs-lookup"><span data-stu-id="81946-153">3</span></span> | <span data-ttu-id="81946-154">Geben Sie nur Eigenschaften zurück, die `wszQualifierName` einen Qualifizierer des durch `pQualifierVal` den Parameter angegebenen Namens haben und außerdem einen Wert haben, der mit dem von der Struktur angegebenen wertist.</span><span class="sxs-lookup"><span data-stu-id="81946-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="81946-155">Wenn dieses Flag verwendet wird, `wszQualifierName` müssen `pQualifierValue`Sie sowohl a als auch a angeben.</span><span class="sxs-lookup"><span data-stu-id="81946-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="81946-156">Flagge der Gruppe 2</span><span class="sxs-lookup"><span data-stu-id="81946-156">Group 2 flags</span></span> |<span data-ttu-id="81946-157">value</span><span class="sxs-lookup"><span data-stu-id="81946-157">Value</span></span>  |<span data-ttu-id="81946-158">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81946-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="81946-159">0x4</span><span class="sxs-lookup"><span data-stu-id="81946-159">0x4</span></span> | <span data-ttu-id="81946-160">Geben Sie nur die Namen der Eigenschaften zurück, die die Schlüssel definieren.</span><span class="sxs-lookup"><span data-stu-id="81946-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="81946-161">0x8</span><span class="sxs-lookup"><span data-stu-id="81946-161">0x8</span></span> | <span data-ttu-id="81946-162">Gibt nur Eigenschaftsnamen zurück, die Objektverweise sind.</span><span class="sxs-lookup"><span data-stu-id="81946-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="81946-163">Flagge der Gruppe 3</span><span class="sxs-lookup"><span data-stu-id="81946-163">Group 3 flags</span></span> |<span data-ttu-id="81946-164">value</span><span class="sxs-lookup"><span data-stu-id="81946-164">Value</span></span>  |<span data-ttu-id="81946-165">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81946-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="81946-166">0x10</span><span class="sxs-lookup"><span data-stu-id="81946-166">0x10</span></span> | <span data-ttu-id="81946-167">Gibt nur Eigenschaftsnamen zurück, die zur am häufigsten abgeleiteten Klasse gehören.</span><span class="sxs-lookup"><span data-stu-id="81946-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="81946-168">Ausschließen von Eigenschaften aus den übergeordneten Klassen.</span><span class="sxs-lookup"><span data-stu-id="81946-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="81946-169">0x20</span><span class="sxs-lookup"><span data-stu-id="81946-169">0x20</span></span> | <span data-ttu-id="81946-170">Gibt nur Eigenschaftsnamen zurück, die zu den übergeordneten Klassen gehören.</span><span class="sxs-lookup"><span data-stu-id="81946-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="81946-171">0x30</span><span class="sxs-lookup"><span data-stu-id="81946-171">0x30</span></span> | <span data-ttu-id="81946-172">Geben Sie nur die Namen der Systemeigenschaften zurück.</span><span class="sxs-lookup"><span data-stu-id="81946-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="81946-173">0x40</span><span class="sxs-lookup"><span data-stu-id="81946-173">0x40</span></span> | <span data-ttu-id="81946-174">Geben Sie nur die Namen von Nicht-Systemeigenschaften zurück.</span><span class="sxs-lookup"><span data-stu-id="81946-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="81946-175">Die Funktion weist immer `SAFEARRAY` eine `WBEM_S_NO_ERROR`neue `pstrNames` zu, wenn sie zurückkehrt, und ist immer so eingestellt, dass sie darauf zeigen soll.</span><span class="sxs-lookup"><span data-stu-id="81946-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="81946-176">Das zurückgegebene Array kann 0 Elemente enthalten, wenn keine Eigenschaften mit den angegebenen Filtern übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="81946-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="81946-177">Wenn die Funktion einen `WBM_S_NO_ERROR`anderen Wert `SAFEARRAY` als zurückgibt, wird keine neue Struktur zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="81946-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="81946-178">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="81946-178">Requirements</span></span>  
 <span data-ttu-id="81946-179">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81946-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81946-180">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="81946-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="81946-181">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="81946-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81946-182">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="81946-182">See also</span></span>

- [<span data-ttu-id="81946-183">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="81946-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
