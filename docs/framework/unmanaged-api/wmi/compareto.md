---
title: CompareTo-Funktion (Referenz zur nicht verwalteten API)
description: Die CompareTo-Funktion vergleicht ein Objekt mit einem anderen WMI-Objekt.
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ec42dff333422e247a11b4a3a5b9aed9bd316fa
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798770"
---
# <a name="compareto-function"></a><span data-ttu-id="da5d9-103">CompareTo-Funktion</span><span class="sxs-lookup"><span data-stu-id="da5d9-103">CompareTo function</span></span>

<span data-ttu-id="da5d9-104">Vergleicht ein Objekt mit einem anderen Windows-Verwaltungsobjekt.</span><span class="sxs-lookup"><span data-stu-id="da5d9-104">Compares an object to another Windows management object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="da5d9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="da5d9-105">Syntax</span></span>

```cpp
HRESULT CompareTo (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo
);
```

## <a name="parameters"></a><span data-ttu-id="da5d9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="da5d9-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="da5d9-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="da5d9-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="da5d9-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="da5d9-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`flags`\
<span data-ttu-id="da5d9-109">in Eine bitweise Kombination der Flags, die die für den Vergleich zu berücksichtigenden Objekteigenschaften angeben.</span><span class="sxs-lookup"><span data-stu-id="da5d9-109">[in] A bitwise combination of the flags that specify the object characteristics to consider for the comparison.</span></span> <span data-ttu-id="da5d9-110">Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="da5d9-110">See the [Remarks](#remarks) section for more information.</span></span>

`pCompareTo`\
<span data-ttu-id="da5d9-111">in Das Objekt für den Vergleich.</span><span class="sxs-lookup"><span data-stu-id="da5d9-111">[in] The object for comparison.</span></span> <span data-ttu-id="da5d9-112">`pCompareTo`muss eine gültige [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz sein. der Wert kann `null`nicht sein.</span><span class="sxs-lookup"><span data-stu-id="da5d9-112">`pCompareTo` must be a valid [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance; it cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="da5d9-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="da5d9-113">Return value</span></span>

<span data-ttu-id="da5d9-114">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="da5d9-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="da5d9-115">Konstante</span><span class="sxs-lookup"><span data-stu-id="da5d9-115">Constant</span></span>  |<span data-ttu-id="da5d9-116">Wert</span><span class="sxs-lookup"><span data-stu-id="da5d9-116">Value</span></span>  |<span data-ttu-id="da5d9-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da5d9-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="da5d9-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="da5d9-118">0x80041001</span></span> | <span data-ttu-id="da5d9-119">Ein nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="da5d9-119">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="da5d9-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="da5d9-120">0x80041008</span></span> | <span data-ttu-id="da5d9-121">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="da5d9-121">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="da5d9-122">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="da5d9-122">0x8004101d</span></span> | <span data-ttu-id="da5d9-123">Es `BeginEnumeration` wurde ein zweiter-Rückruf ohne einen dazwischen liegenden- [`EndEnumeration`](endenumeration.md)Rückruf durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="da5d9-123">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="da5d9-124">0</span><span class="sxs-lookup"><span data-stu-id="da5d9-124">0</span></span> | <span data-ttu-id="da5d9-125">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="da5d9-125">The function call was successful.</span></span>  |
| `WBEM_S_DIFFERENT` | <span data-ttu-id="da5d9-126">0x40003</span><span class="sxs-lookup"><span data-stu-id="da5d9-126">0x40003</span></span> | <span data-ttu-id="da5d9-127">Die Objekte unterscheiden sich.</span><span class="sxs-lookup"><span data-stu-id="da5d9-127">The objects are different.</span></span> |
| `WBEM_S_SAME` | <span data-ttu-id="da5d9-128">0</span><span class="sxs-lookup"><span data-stu-id="da5d9-128">0</span></span> | <span data-ttu-id="da5d9-129">Die Objekte sind auf der Grundlage der Vergleichsflags identisch.</span><span class="sxs-lookup"><span data-stu-id="da5d9-129">The objects are the same based on the comparison flags.</span></span> |

## <a name="remarks"></a><span data-ttu-id="da5d9-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="da5d9-130">Remarks</span></span>

<span data-ttu-id="da5d9-131">Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject:: CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) -Methode.</span><span class="sxs-lookup"><span data-stu-id="da5d9-131">This function wraps a call to the [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) method.</span></span>

<span data-ttu-id="da5d9-132">Die Flags, die als `lEnumFlags` Argument übermittelt werden können, werden in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren.</span><span class="sxs-lookup"><span data-stu-id="da5d9-132">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> <span data-ttu-id="da5d9-133">Sie können die einzelnen Merkmale des Vergleichs angeben, indem Sie eine bitweise Kombination der folgenden Flags angeben:</span><span class="sxs-lookup"><span data-stu-id="da5d9-133">You can specify the individual characteristics involved in the comparison by specifying a bitwise combination of the following flags:</span></span>

|<span data-ttu-id="da5d9-134">Konstante</span><span class="sxs-lookup"><span data-stu-id="da5d9-134">Constant</span></span>  |<span data-ttu-id="da5d9-135">Wert</span><span class="sxs-lookup"><span data-stu-id="da5d9-135">Value</span></span>  |<span data-ttu-id="da5d9-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da5d9-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | <span data-ttu-id="da5d9-137">2</span><span class="sxs-lookup"><span data-stu-id="da5d9-137">2</span></span> | <span data-ttu-id="da5d9-138">Ignorieren Sie die Quelle (Server und Namespace, von denen Sie stammen).</span><span class="sxs-lookup"><span data-stu-id="da5d9-138">Ignore the source (the server and the namespace they came from).</span></span> |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | <span data-ttu-id="da5d9-139">1</span><span class="sxs-lookup"><span data-stu-id="da5d9-139">1</span></span> | <span data-ttu-id="da5d9-140">Alle Qualifizierer ignorieren (einschließlich **Key** und **Dynamic**)</span><span class="sxs-lookup"><span data-stu-id="da5d9-140">Ignore all qualifiers (including **Key** and **Dynamic**)</span></span> |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | <span data-ttu-id="da5d9-141">4</span><span class="sxs-lookup"><span data-stu-id="da5d9-141">4</span></span> | <span data-ttu-id="da5d9-142">Standardwerte von Eigenschaften ignorieren.</span><span class="sxs-lookup"><span data-stu-id="da5d9-142">Ignore default values of properties.</span></span> <span data-ttu-id="da5d9-143">Dieses Flag gilt nur für den Vergleich von-Klassen.</span><span class="sxs-lookup"><span data-stu-id="da5d9-143">This flag only applies to comparison of classes.</span></span> |
| `WBEM_FLAG_IGNORE_FLAVOR` | <span data-ttu-id="da5d9-144">0x20</span><span class="sxs-lookup"><span data-stu-id="da5d9-144">0x20</span></span> | <span data-ttu-id="da5d9-145">Qualifizierervarianten ignorieren.</span><span class="sxs-lookup"><span data-stu-id="da5d9-145">Ignore qualifier flavors.</span></span> <span data-ttu-id="da5d9-146">Dieses Flag berücksichtigt weiterhin Qualifizierer, ignoriert jedoch Unterschiede wie Weiterleitungs Regeln und Überschreibungs Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="da5d9-146">This flag still takes qualifiers into account, but ignores flavor distinctions such as propagation rules and override restrictions.</span></span> |
| `WBEM_FLAG_IGNORE_CASE` | <span data-ttu-id="da5d9-147">0x10</span><span class="sxs-lookup"><span data-stu-id="da5d9-147">0x10</span></span> | <span data-ttu-id="da5d9-148">Groß-/Kleinschreibung beim Vergleichen von Zeichen folgen Werten ignorieren</span><span class="sxs-lookup"><span data-stu-id="da5d9-148">Ignore case in comparing string values.</span></span> <span data-ttu-id="da5d9-149">Dies gilt sowohl für Zeichen folgen als auch für Qualifiziererwerte.</span><span class="sxs-lookup"><span data-stu-id="da5d9-149">This applies both to strings and qualifier values.</span></span> <span data-ttu-id="da5d9-150">Beim Vergleich von Eigenschaften-und Qualifizierernamen wird immer die Groß-/Kleinschreibung beachtet, unabhängig davon, ob dieses Flag festgelegt</span><span class="sxs-lookup"><span data-stu-id="da5d9-150">The comparison of property and qualifier names is always case-sensitive regardless of whether this flag is set.</span></span> |
| `WBEM_FLAG_IGNORE_CLASS` | <span data-ttu-id="da5d9-151">0x8</span><span class="sxs-lookup"><span data-stu-id="da5d9-151">0x8</span></span> | <span data-ttu-id="da5d9-152">Angenommen, die Objekte, die verglichen werden, sind Instanzen derselben Klasse.</span><span class="sxs-lookup"><span data-stu-id="da5d9-152">Assume that the objects being compared are instances of the same class.</span></span> <span data-ttu-id="da5d9-153">Folglich vergleicht dieses Flag nur instanzbezogene Informationen.</span><span class="sxs-lookup"><span data-stu-id="da5d9-153">Consequently, this flag compares instance-related information only.</span></span> <span data-ttu-id="da5d9-154">Verwenden Sie diese Flags, um die Leistung zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="da5d9-154">Use this flags to optimize performance.</span></span> <span data-ttu-id="da5d9-155">Wenn die Objekte nicht der gleichen Klasse entsprechen, sind die Ergebnisse nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="da5d9-155">If the objects are not of the same class, the results are undefined.</span></span> |

<span data-ttu-id="da5d9-156">Oder Sie können ein einzelnes zusammengesetztes Flag wie folgt angeben:</span><span class="sxs-lookup"><span data-stu-id="da5d9-156">Or you can specify a single composite flag as follows:</span></span>

|<span data-ttu-id="da5d9-157">Konstante</span><span class="sxs-lookup"><span data-stu-id="da5d9-157">Constant</span></span>  |<span data-ttu-id="da5d9-158">Wert</span><span class="sxs-lookup"><span data-stu-id="da5d9-158">Value</span></span>  |<span data-ttu-id="da5d9-159">Description</span><span class="sxs-lookup"><span data-stu-id="da5d9-159">Description</span></span>  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | <span data-ttu-id="da5d9-160">0</span><span class="sxs-lookup"><span data-stu-id="da5d9-160">0</span></span> | <span data-ttu-id="da5d9-161">Beachten Sie alle Features im Vergleich.</span><span class="sxs-lookup"><span data-stu-id="da5d9-161">Consider all features in the comparison.</span></span> |

## <a name="requirements"></a><span data-ttu-id="da5d9-162">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="da5d9-162">Requirements</span></span>

<span data-ttu-id="da5d9-163">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da5d9-163">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="da5d9-164">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="da5d9-164">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="da5d9-165">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="da5d9-165">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="da5d9-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da5d9-166">See also</span></span>

- [<span data-ttu-id="da5d9-167">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="da5d9-167">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
