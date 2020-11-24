---
title: GetNames-Funktion (Referenz zur nicht verwalteten API)
description: Die GetNames-Funktion Ruft die Namen der Eigenschaften eines Objekts ab.
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
ms.openlocfilehash: fd889158e61b86f42d88bcf86eda7d816277e6ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687657"
---
# <a name="getnames-function"></a><span data-ttu-id="1e0cb-103">GetNames-Funktion</span><span class="sxs-lookup"><span data-stu-id="1e0cb-103">GetNames function</span></span>

<span data-ttu-id="1e0cb-104">Ruft eine Teilmenge oder alle Namen der Eigenschaften eines Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-104">Retrieves either a subset or all of the names of the properties of an object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="1e0cb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e0cb-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="1e0cb-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1e0cb-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1e0cb-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="1e0cb-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="1e0cb-109">in Ein Zeiger auf einen gültigen `LPCWSTR` , der einen Qualifizierernamen angibt, der als Teil eines Filters fungiert.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="1e0cb-110">Weitere Informationen finden Sie im Abschnitt [Hinweise](#remarks).</span><span class="sxs-lookup"><span data-stu-id="1e0cb-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="1e0cb-111">Dieser Parameter kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-111">This parameter can be `null`.</span></span>

`lFlags`  
<span data-ttu-id="1e0cb-112">in Eine Kombination von Bitfeldern.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="1e0cb-113">Weitere Informationen finden Sie im Abschnitt [Hinweise](#remarks).</span><span class="sxs-lookup"><span data-stu-id="1e0cb-113">For more information, see the [Remarks](#remarks) section.</span></span>

<span data-ttu-id="1e0cb-114">`pQualifierValue` in Ein Zeiger auf eine gültige- `VARIANT` Struktur, die mit einem Filter Wert initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-114">`pQualifierValue` [in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="1e0cb-115">Dieser Parameter kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-115">This parameter can be `null`.</span></span>

`pstrNames`  
<span data-ttu-id="1e0cb-116">vorgenommen Eine- `SAFEARRAY` Struktur, die Eigenschaftsnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="1e0cb-117">Bei einem Eintrag muss dieser Parameter immer ein Zeiger auf sein `null` .</span><span class="sxs-lookup"><span data-stu-id="1e0cb-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="1e0cb-118">Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="1e0cb-118">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="1e0cb-119">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1e0cb-119">Return value</span></span>

<span data-ttu-id="1e0cb-120">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="1e0cb-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1e0cb-121">Konstante</span><span class="sxs-lookup"><span data-stu-id="1e0cb-121">Constant</span></span>  |<span data-ttu-id="1e0cb-122">Wert</span><span class="sxs-lookup"><span data-stu-id="1e0cb-122">Value</span></span>  |<span data-ttu-id="1e0cb-123">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1e0cb-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="1e0cb-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="1e0cb-124">0x80041001</span></span> | <span data-ttu-id="1e0cb-125">Es ist ein allgemeiner Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1e0cb-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1e0cb-126">0x80041008</span></span> | <span data-ttu-id="1e0cb-127">Mindestens ein Parameter ist ungültig, oder es wurde eine falsche Kombination von Flags und Parametern angegeben.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="1e0cb-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="1e0cb-128">0x80041006</span></span> | <span data-ttu-id="1e0cb-129">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1e0cb-130">0</span><span class="sxs-lookup"><span data-stu-id="1e0cb-130">0</span></span> | <span data-ttu-id="1e0cb-131">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1e0cb-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1e0cb-132">Remarks</span></span>

<span data-ttu-id="1e0cb-133">Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject:: GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) -Methode.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="1e0cb-134">Der zurückgegebene benannte wird durch eine Kombination von Flags und Parametern gesteuert.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="1e0cb-135">Die-Funktion kann z. b. die Namen aller Eigenschaften oder nur die Namen der Schlüsseleigenschaften zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="1e0cb-136">Der primäre Filter wird im `lFlags` -Parameter angegeben, und die anderen Parameter variieren in Abhängigkeit davon.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="1e0cb-137">Die Flagwerte in `lFlags` sind Bitfelder.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-137">The flag values in `lFlags` are bit fields</span></span>

<span data-ttu-id="1e0cb-138">Die Flags, die als Argument übermittelt werden können `lEnumFlags` , sind Bitfelder, die in der *wbemcli. h* -Header Datei definiert sind, oder Sie können Sie als Konstanten im Code definieren.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="1e0cb-139">Sie können ein Flag aus jeder Gruppe mit einem beliebigen Flag aus einer beliebigen anderen Gruppe kombinieren.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="1e0cb-140">Flags aus derselben Gruppe schließen sich jedoch gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-140">However, flags from the same group are mutually exclusive.</span></span>

| <span data-ttu-id="1e0cb-141">Gruppen-1-Flags</span><span class="sxs-lookup"><span data-stu-id="1e0cb-141">Group 1 flags</span></span> |<span data-ttu-id="1e0cb-142">Wert</span><span class="sxs-lookup"><span data-stu-id="1e0cb-142">Value</span></span>  |<span data-ttu-id="1e0cb-143">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1e0cb-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="1e0cb-144">0</span><span class="sxs-lookup"><span data-stu-id="1e0cb-144">0</span></span> | <span data-ttu-id="1e0cb-145">Gibt alle Eigenschaftsnamen zurück.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-145">Return all property names.</span></span> <span data-ttu-id="1e0cb-146">`strQualifierName` und `pQualifierVal` werden nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="1e0cb-147">1</span><span class="sxs-lookup"><span data-stu-id="1e0cb-147">1</span></span> | <span data-ttu-id="1e0cb-148">Gibt nur Eigenschaften zurück, die einen Qualifizierer des Namens aufweisen, der durch den-Parameter angegeben wird `strQualifierName` .</span><span class="sxs-lookup"><span data-stu-id="1e0cb-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="1e0cb-149">Wenn dieses Flag verwendet wird, müssen Sie angeben `strQualifierName` .</span><span class="sxs-lookup"><span data-stu-id="1e0cb-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="1e0cb-150">2</span><span class="sxs-lookup"><span data-stu-id="1e0cb-150">2</span></span> |  <span data-ttu-id="1e0cb-151">Gibt nur Eigenschaften zurück, die über keinen Qualifizierer des Namens verfügen, der durch den-Parameter angegeben wird `strQualifierName` .</span><span class="sxs-lookup"><span data-stu-id="1e0cb-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="1e0cb-152">Wenn dieses Flag verwendet wird, müssen Sie angeben `strQualifierName` .</span><span class="sxs-lookup"><span data-stu-id="1e0cb-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="1e0cb-153">3</span><span class="sxs-lookup"><span data-stu-id="1e0cb-153">3</span></span> | <span data-ttu-id="1e0cb-154">Gibt nur Eigenschaften zurück, die über einen Qualifizierer des Namens verfügen, der durch den-Parameter angegeben wird, `wszQualifierName` und einen Wert aufweisen, der mit dem von der- `pQualifierVal` Struktur angegebenen</span><span class="sxs-lookup"><span data-stu-id="1e0cb-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="1e0cb-155">Wenn dieses Flag verwendet wird, müssen Sie sowohl ein `wszQualifierName` als auch ein angeben `pQualifierValue` .</span><span class="sxs-lookup"><span data-stu-id="1e0cb-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="1e0cb-156">Gruppen-2-Flags</span><span class="sxs-lookup"><span data-stu-id="1e0cb-156">Group 2 flags</span></span> |<span data-ttu-id="1e0cb-157">Wert</span><span class="sxs-lookup"><span data-stu-id="1e0cb-157">Value</span></span>  |<span data-ttu-id="1e0cb-158">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1e0cb-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="1e0cb-159">0x4</span><span class="sxs-lookup"><span data-stu-id="1e0cb-159">0x4</span></span> | <span data-ttu-id="1e0cb-160">Gibt nur die Namen von Eigenschaften zurück, die die Schlüssel definieren.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="1e0cb-161">0x8</span><span class="sxs-lookup"><span data-stu-id="1e0cb-161">0x8</span></span> | <span data-ttu-id="1e0cb-162">Gibt nur Eigenschaftsnamen zurück, die Objekt Verweise sind.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="1e0cb-163">Gruppen-3-Flags</span><span class="sxs-lookup"><span data-stu-id="1e0cb-163">Group 3 flags</span></span> |<span data-ttu-id="1e0cb-164">Wert</span><span class="sxs-lookup"><span data-stu-id="1e0cb-164">Value</span></span>  |<span data-ttu-id="1e0cb-165">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1e0cb-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="1e0cb-166">0x10</span><span class="sxs-lookup"><span data-stu-id="1e0cb-166">0x10</span></span> | <span data-ttu-id="1e0cb-167">Gibt nur Eigenschaftsnamen zurück, die zur am weitesten abgeleiteten Klasse gehören.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="1e0cb-168">Schließt Eigenschaften aus den übergeordneten Klassen aus.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="1e0cb-169">0x20</span><span class="sxs-lookup"><span data-stu-id="1e0cb-169">0x20</span></span> | <span data-ttu-id="1e0cb-170">Gibt nur Eigenschaftsnamen zurück, die zu den übergeordneten Klassen gehören.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="1e0cb-171">0x30</span><span class="sxs-lookup"><span data-stu-id="1e0cb-171">0x30</span></span> | <span data-ttu-id="1e0cb-172">Gibt nur die Namen der Systemeigenschaften zurück.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="1e0cb-173">0x40</span><span class="sxs-lookup"><span data-stu-id="1e0cb-173">0x40</span></span> | <span data-ttu-id="1e0cb-174">Gibt nur die Namen von nicht-Systemeigenschaften zurück.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="1e0cb-175">Die-Funktion weist immer einen neuen `SAFEARRAY` zu, wenn Sie zurückgibt `WBEM_S_NO_ERROR` , und `pstrNames` ist immer darauf festgelegt, darauf zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="1e0cb-176">Das zurückgegebene Array kann 0 Elemente aufweisen, wenn keine Eigenschaften den angegebenen Filtern entsprechen.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="1e0cb-177">Wenn die Funktion einen anderen Wert als zurückgibt `WBM_S_NO_ERROR` , `SAFEARRAY` wird keine neue Struktur zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1e0cb-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="1e0cb-178">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1e0cb-178">Requirements</span></span>  

 <span data-ttu-id="1e0cb-179">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e0cb-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e0cb-180">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="1e0cb-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1e0cb-181">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1e0cb-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e0cb-182">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1e0cb-182">See also</span></span>

- [<span data-ttu-id="1e0cb-183">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="1e0cb-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
