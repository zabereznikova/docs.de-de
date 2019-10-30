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
ms.openlocfilehash: 0d210795016cd2e0179b902a224ca0c62f4ac01f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128698"
---
# <a name="compareto-function"></a><span data-ttu-id="74a0e-103">CompareTo-Funktion</span><span class="sxs-lookup"><span data-stu-id="74a0e-103">CompareTo function</span></span>

<span data-ttu-id="74a0e-104">Vergleicht ein Objekt mit einem anderen Windows-Verwaltungsobjekt.</span><span class="sxs-lookup"><span data-stu-id="74a0e-104">Compares an object to another Windows management object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="74a0e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="74a0e-105">Syntax</span></span>

```cpp
HRESULT CompareTo (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo
);
```

## <a name="parameters"></a><span data-ttu-id="74a0e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="74a0e-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="74a0e-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="74a0e-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="74a0e-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="74a0e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`flags`\
<span data-ttu-id="74a0e-109">in Eine bitweise Kombination der Flags, die die für den Vergleich zu berücksichtigenden Objekteigenschaften angeben.</span><span class="sxs-lookup"><span data-stu-id="74a0e-109">[in] A bitwise combination of the flags that specify the object characteristics to consider for the comparison.</span></span> <span data-ttu-id="74a0e-110">Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="74a0e-110">See the [Remarks](#remarks) section for more information.</span></span>

`pCompareTo`\
<span data-ttu-id="74a0e-111">in Das Objekt für den Vergleich.</span><span class="sxs-lookup"><span data-stu-id="74a0e-111">[in] The object for comparison.</span></span> <span data-ttu-id="74a0e-112">`pCompareTo` muss eine gültige [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz sein. Es kann nicht `null`werden.</span><span class="sxs-lookup"><span data-stu-id="74a0e-112">`pCompareTo` must be a valid [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance; it cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="74a0e-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="74a0e-113">Return value</span></span>

<span data-ttu-id="74a0e-114">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="74a0e-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="74a0e-115">Konstante</span><span class="sxs-lookup"><span data-stu-id="74a0e-115">Constant</span></span>  |<span data-ttu-id="74a0e-116">Wert</span><span class="sxs-lookup"><span data-stu-id="74a0e-116">Value</span></span>  |<span data-ttu-id="74a0e-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74a0e-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="74a0e-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="74a0e-118">0x80041001</span></span> | <span data-ttu-id="74a0e-119">Ein nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="74a0e-119">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="74a0e-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="74a0e-120">0x80041008</span></span> | <span data-ttu-id="74a0e-121">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="74a0e-121">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="74a0e-122">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="74a0e-122">0x8004101d</span></span> | <span data-ttu-id="74a0e-123">Es wurde ein zweiter `BeginEnumeration` aufgerufen, ohne dass ein dazwischen befindender [`EndEnumeration`](endenumeration.md)aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="74a0e-123">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="74a0e-124">0</span><span class="sxs-lookup"><span data-stu-id="74a0e-124">0</span></span> | <span data-ttu-id="74a0e-125">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="74a0e-125">The function call was successful.</span></span>  |
| `WBEM_S_DIFFERENT` | <span data-ttu-id="74a0e-126">0x40003</span><span class="sxs-lookup"><span data-stu-id="74a0e-126">0x40003</span></span> | <span data-ttu-id="74a0e-127">Die Objekte unterscheiden sich.</span><span class="sxs-lookup"><span data-stu-id="74a0e-127">The objects are different.</span></span> |
| `WBEM_S_SAME` | <span data-ttu-id="74a0e-128">0</span><span class="sxs-lookup"><span data-stu-id="74a0e-128">0</span></span> | <span data-ttu-id="74a0e-129">Die Objekte sind auf der Grundlage der Vergleichsflags identisch.</span><span class="sxs-lookup"><span data-stu-id="74a0e-129">The objects are the same based on the comparison flags.</span></span> |

## <a name="remarks"></a><span data-ttu-id="74a0e-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74a0e-130">Remarks</span></span>

<span data-ttu-id="74a0e-131">Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject:: CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) -Methode.</span><span class="sxs-lookup"><span data-stu-id="74a0e-131">This function wraps a call to the [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) method.</span></span>

<span data-ttu-id="74a0e-132">Die Flags, die als `lEnumFlags` Argument übermittelt werden können, werden in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren.</span><span class="sxs-lookup"><span data-stu-id="74a0e-132">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> <span data-ttu-id="74a0e-133">Sie können die einzelnen Merkmale des Vergleichs angeben, indem Sie eine bitweise Kombination der folgenden Flags angeben:</span><span class="sxs-lookup"><span data-stu-id="74a0e-133">You can specify the individual characteristics involved in the comparison by specifying a bitwise combination of the following flags:</span></span>

|<span data-ttu-id="74a0e-134">Konstante</span><span class="sxs-lookup"><span data-stu-id="74a0e-134">Constant</span></span>  |<span data-ttu-id="74a0e-135">Wert</span><span class="sxs-lookup"><span data-stu-id="74a0e-135">Value</span></span>  |<span data-ttu-id="74a0e-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74a0e-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | <span data-ttu-id="74a0e-137">2</span><span class="sxs-lookup"><span data-stu-id="74a0e-137">2</span></span> | <span data-ttu-id="74a0e-138">Ignorieren Sie die Quelle (Server und Namespace, von denen Sie stammen).</span><span class="sxs-lookup"><span data-stu-id="74a0e-138">Ignore the source (the server and the namespace they came from).</span></span> |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | <span data-ttu-id="74a0e-139">1</span><span class="sxs-lookup"><span data-stu-id="74a0e-139">1</span></span> | <span data-ttu-id="74a0e-140">Alle Qualifizierer ignorieren (einschließlich **Key** und **Dynamic**)</span><span class="sxs-lookup"><span data-stu-id="74a0e-140">Ignore all qualifiers (including **Key** and **Dynamic**)</span></span> |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | <span data-ttu-id="74a0e-141">4</span><span class="sxs-lookup"><span data-stu-id="74a0e-141">4</span></span> | <span data-ttu-id="74a0e-142">Standardwerte von Eigenschaften ignorieren.</span><span class="sxs-lookup"><span data-stu-id="74a0e-142">Ignore default values of properties.</span></span> <span data-ttu-id="74a0e-143">Dieses Flag gilt nur für den Vergleich von-Klassen.</span><span class="sxs-lookup"><span data-stu-id="74a0e-143">This flag only applies to comparison of classes.</span></span> |
| `WBEM_FLAG_IGNORE_FLAVOR` | <span data-ttu-id="74a0e-144">0x20</span><span class="sxs-lookup"><span data-stu-id="74a0e-144">0x20</span></span> | <span data-ttu-id="74a0e-145">Qualifizierervarianten ignorieren.</span><span class="sxs-lookup"><span data-stu-id="74a0e-145">Ignore qualifier flavors.</span></span> <span data-ttu-id="74a0e-146">Dieses Flag berücksichtigt weiterhin Qualifizierer, ignoriert jedoch Unterschiede wie Weiterleitungs Regeln und Überschreibungs Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="74a0e-146">This flag still takes qualifiers into account, but ignores flavor distinctions such as propagation rules and override restrictions.</span></span> |
| `WBEM_FLAG_IGNORE_CASE` | <span data-ttu-id="74a0e-147">0x10</span><span class="sxs-lookup"><span data-stu-id="74a0e-147">0x10</span></span> | <span data-ttu-id="74a0e-148">Groß-/Kleinschreibung beim Vergleichen von Zeichen folgen Werten ignorieren</span><span class="sxs-lookup"><span data-stu-id="74a0e-148">Ignore case in comparing string values.</span></span> <span data-ttu-id="74a0e-149">Dies gilt sowohl für Zeichen folgen als auch für Qualifiziererwerte.</span><span class="sxs-lookup"><span data-stu-id="74a0e-149">This applies both to strings and qualifier values.</span></span> <span data-ttu-id="74a0e-150">Beim Vergleich von Eigenschaften-und Qualifizierernamen wird immer die Groß-/Kleinschreibung beachtet, unabhängig davon, ob dieses Flag festgelegt</span><span class="sxs-lookup"><span data-stu-id="74a0e-150">The comparison of property and qualifier names is always case-sensitive regardless of whether this flag is set.</span></span> |
| `WBEM_FLAG_IGNORE_CLASS` | <span data-ttu-id="74a0e-151">0x8</span><span class="sxs-lookup"><span data-stu-id="74a0e-151">0x8</span></span> | <span data-ttu-id="74a0e-152">Angenommen, die Objekte, die verglichen werden, sind Instanzen derselben Klasse.</span><span class="sxs-lookup"><span data-stu-id="74a0e-152">Assume that the objects being compared are instances of the same class.</span></span> <span data-ttu-id="74a0e-153">Folglich vergleicht dieses Flag nur instanzbezogene Informationen.</span><span class="sxs-lookup"><span data-stu-id="74a0e-153">Consequently, this flag compares instance-related information only.</span></span> <span data-ttu-id="74a0e-154">Verwenden Sie diese Flags, um die Leistung zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="74a0e-154">Use this flags to optimize performance.</span></span> <span data-ttu-id="74a0e-155">Wenn die Objekte nicht der gleichen Klasse entsprechen, sind die Ergebnisse nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="74a0e-155">If the objects are not of the same class, the results are undefined.</span></span> |

<span data-ttu-id="74a0e-156">Oder Sie können ein einzelnes zusammengesetztes Flag wie folgt angeben:</span><span class="sxs-lookup"><span data-stu-id="74a0e-156">Or you can specify a single composite flag as follows:</span></span>

|<span data-ttu-id="74a0e-157">Konstante</span><span class="sxs-lookup"><span data-stu-id="74a0e-157">Constant</span></span>  |<span data-ttu-id="74a0e-158">Wert</span><span class="sxs-lookup"><span data-stu-id="74a0e-158">Value</span></span>  |<span data-ttu-id="74a0e-159">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74a0e-159">Description</span></span>  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | <span data-ttu-id="74a0e-160">0</span><span class="sxs-lookup"><span data-stu-id="74a0e-160">0</span></span> | <span data-ttu-id="74a0e-161">Beachten Sie alle Features im Vergleich.</span><span class="sxs-lookup"><span data-stu-id="74a0e-161">Consider all features in the comparison.</span></span> |

## <a name="requirements"></a><span data-ttu-id="74a0e-162">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="74a0e-162">Requirements</span></span>

<span data-ttu-id="74a0e-163">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74a0e-163">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="74a0e-164">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="74a0e-164">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="74a0e-165">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="74a0e-165">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="74a0e-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74a0e-166">See also</span></span>

- [<span data-ttu-id="74a0e-167">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="74a0e-167">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
