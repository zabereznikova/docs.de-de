---
title: CompareTo-Funktion (Referenz zur nicht verwalteten API)
description: Die CompareTo-Funktion vergleicht ein Objekt in ein anderes WMI-Objekt.
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
ms.openlocfilehash: db4431da90842f4f96a0f09a2f28dc473d956ee3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460407"
---
# <a name="compareto-function"></a><span data-ttu-id="9f30b-103">CompareTo-Funktion</span><span class="sxs-lookup"><span data-stu-id="9f30b-103">CompareTo function</span></span>
<span data-ttu-id="9f30b-104">Vergleicht ein Objekt in ein anderes Windows-Management-Objekt.</span><span class="sxs-lookup"><span data-stu-id="9f30b-104">Compares an object to another Windows management object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="9f30b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f30b-105">Syntax</span></span>  
  
```
HRESULT CompareTo (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo 
); 
```  

## <a name="parameters"></a><span data-ttu-id="9f30b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9f30b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="9f30b-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="9f30b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="9f30b-108">[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="9f30b-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`flags`  
<span data-ttu-id="9f30b-109">[in] Eine bitweise Kombination der Flags, die angeben, die Merkmale für den Vergleich zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="9f30b-109">[in] A bitwise combination of the flags that specify the object characteristics to consider for the comparison.</span></span> <span data-ttu-id="9f30b-110">Finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="9f30b-110">See the [Remarks](#remarks) section for more information.</span></span>

`pCompareTo`  

<span data-ttu-id="9f30b-111">[in] Das zu vergleichende Objekt.</span><span class="sxs-lookup"><span data-stu-id="9f30b-111">[in] The object for comparison.</span></span> <span data-ttu-id="9f30b-112">`pcompareTo` muss ein gültiger [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) -Instanz; er darf nicht `null`.</span><span class="sxs-lookup"><span data-stu-id="9f30b-112">`pcompareTo` must be a valid [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance; it cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="9f30b-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9f30b-113">Return value</span></span>

<span data-ttu-id="9f30b-114">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="9f30b-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9f30b-115">Konstante</span><span class="sxs-lookup"><span data-stu-id="9f30b-115">Constant</span></span>  |<span data-ttu-id="9f30b-116">Wert</span><span class="sxs-lookup"><span data-stu-id="9f30b-116">Value</span></span>  |<span data-ttu-id="9f30b-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f30b-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="9f30b-118">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="9f30b-118">0x80041001</span></span> | <span data-ttu-id="9f30b-119">Nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9f30b-119">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="9f30b-120">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="9f30b-120">0x80041008</span></span> | <span data-ttu-id="9f30b-121">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="9f30b-121">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="9f30b-122">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="9f30b-122">0x8004101d</span></span> | <span data-ttu-id="9f30b-123">Einen zweiten Aufruf von `BeginEnumeration` wurde versucht, ohne einen zwischenzeitlichen Aufruf von [ `EndEnumeration` ](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="9f30b-123">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="9f30b-124">0</span><span class="sxs-lookup"><span data-stu-id="9f30b-124">0</span></span> | <span data-ttu-id="9f30b-125">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="9f30b-125">The function call was successful.</span></span>  |
| `WBEM_S_DIFFERENT` | <span data-ttu-id="9f30b-126">0x40003</span><span class="sxs-lookup"><span data-stu-id="9f30b-126">0x40003</span></span> | <span data-ttu-id="9f30b-127">Die Objekte unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="9f30b-127">The objects are different.</span></span> |
| `WBEM_S_SAME` | <span data-ttu-id="9f30b-128">0</span><span class="sxs-lookup"><span data-stu-id="9f30b-128">0</span></span> | <span data-ttu-id="9f30b-129">Die Objekte sind gleich basierend auf die Vergleichsflags.</span><span class="sxs-lookup"><span data-stu-id="9f30b-129">The objects are the same based on the comparison flags.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="9f30b-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9f30b-130">Remarks</span></span>

<span data-ttu-id="9f30b-131">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::CompareTo](https://msdn.microsoft.com/library/aa391437(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="9f30b-131">This function wraps a call to the [IWbemClassObject::CompareTo](https://msdn.microsoft.com/library/aa391437(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="9f30b-132">Die Flags, die als übergeben werden können die `lEnumFlags` Argument definiert werden, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="9f30b-132">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> <span data-ttu-id="9f30b-133">Sie können die einzelnen Eigenschaften Beteiligten im Vergleich angeben, indem eine bitweise Kombination der folgenden Flags angeben:</span><span class="sxs-lookup"><span data-stu-id="9f30b-133">You can specify the individual characteristics involved in the comparison by specifying a bitwise combination of the following flags:</span></span>

|<span data-ttu-id="9f30b-134">Konstante</span><span class="sxs-lookup"><span data-stu-id="9f30b-134">Constant</span></span>  |<span data-ttu-id="9f30b-135">Wert</span><span class="sxs-lookup"><span data-stu-id="9f30b-135">Value</span></span>  |<span data-ttu-id="9f30b-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f30b-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | <span data-ttu-id="9f30b-137">2</span><span class="sxs-lookup"><span data-stu-id="9f30b-137">2</span></span> | <span data-ttu-id="9f30b-138">Ignorieren Sie die Quelle (die Server und der Namespace, dem sie stammt).</span><span class="sxs-lookup"><span data-stu-id="9f30b-138">Ignore the source (the server and the namespace they came from).</span></span> |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | <span data-ttu-id="9f30b-139">1</span><span class="sxs-lookup"><span data-stu-id="9f30b-139">1</span></span> | <span data-ttu-id="9f30b-140">Ignorieren Sie alle Qualifizierer (einschließlich **Schlüssel** und **dynamische**)</span><span class="sxs-lookup"><span data-stu-id="9f30b-140">Ignore all qualifiers (including **Key** and **Dynamic**)</span></span> |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | <span data-ttu-id="9f30b-141">4</span><span class="sxs-lookup"><span data-stu-id="9f30b-141">4</span></span> | <span data-ttu-id="9f30b-142">Ignorieren Sie die Standardwerte der Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="9f30b-142">Ignore default values of properties.</span></span> <span data-ttu-id="9f30b-143">Dieses Flag gilt nur für Vergleich von Klassen.</span><span class="sxs-lookup"><span data-stu-id="9f30b-143">This flag only applies to comparison of classes.</span></span> |
| `WBEM_FLAG_IGNORE_FLAVOR` | <span data-ttu-id="9f30b-144">0x20</span><span class="sxs-lookup"><span data-stu-id="9f30b-144">0x20</span></span> | <span data-ttu-id="9f30b-145">Ignorieren Sie Qualifizierern.</span><span class="sxs-lookup"><span data-stu-id="9f30b-145">Ignore qualifier flavors.</span></span> <span data-ttu-id="9f30b-146">Dieses Flag immer noch Qualifizierer Abhängigkeitslinks berücksichtigen, aber ignoriert Flavor Unterschiede wie Weitergabe Regeln und Überschreiben von Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="9f30b-146">This flag still takes qualifiers into account, but ignores flavor distinctions such as propagation rules and override restrictions.</span></span> |
| `WBEM_FLAG_IGNORE_CASE` | <span data-ttu-id="9f30b-147">0x10</span><span class="sxs-lookup"><span data-stu-id="9f30b-147">0x10</span></span> | <span data-ttu-id="9f30b-148">Ignorieren Sie Groß-/Kleinschreibung, in das Vergleichen von Zeichenfolgenwerten.</span><span class="sxs-lookup"><span data-stu-id="9f30b-148">Ignore case in comparing string values.</span></span> <span data-ttu-id="9f30b-149">Dies gilt sowohl für Zeichenfolgen und Qualifiziererwerte.</span><span class="sxs-lookup"><span data-stu-id="9f30b-149">This applies both to strings and qualifier values.</span></span> <span data-ttu-id="9f30b-150">Beim Vergleich von Eigenschaften-und Qualifizierer wird immer Groß-/Kleinschreibung beachtet, unabhängig davon, ob dieses Flag festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9f30b-150">The comparison of property and qualifier names is always case-sensitive regardless of whether this flag is set.</span></span> |
| `WBEM_FLAG_IGNORE_CLASS` | <span data-ttu-id="9f30b-151">0x8</span><span class="sxs-lookup"><span data-stu-id="9f30b-151">0x8</span></span> | <span data-ttu-id="9f30b-152">Angenommen Sie, die zu vergleichenden Objekte Instanes derselben Klasse sind.</span><span class="sxs-lookup"><span data-stu-id="9f30b-152">Assume that the objects being compared are instanes of the same class.</span></span> <span data-ttu-id="9f30b-153">Daher wird dieses Flag nur Zielinstanzen zu verglichen.</span><span class="sxs-lookup"><span data-stu-id="9f30b-153">Consequently, this flag compares instance-related information only.</span></span> <span data-ttu-id="9f30b-154">Verwenden Sie diese Flags, um die Leistung zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="9f30b-154">Use this flags to optimize performance.</span></span> <span data-ttu-id="9f30b-155">Wenn die Objekte nicht von derselben Klasse sind, sind die Ergebnisse nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="9f30b-155">If the objects are not of the same class, the results are undefined.</span></span> |

<span data-ttu-id="9f30b-156">Oder Sie können einem einzelnen zusammengesetzten Flag wie folgt angeben:</span><span class="sxs-lookup"><span data-stu-id="9f30b-156">Or you can specify a single composite flag as follows:</span></span>

|<span data-ttu-id="9f30b-157">Konstante</span><span class="sxs-lookup"><span data-stu-id="9f30b-157">Constant</span></span>  |<span data-ttu-id="9f30b-158">Wert</span><span class="sxs-lookup"><span data-stu-id="9f30b-158">Value</span></span>  |<span data-ttu-id="9f30b-159">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f30b-159">Description</span></span>  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | <span data-ttu-id="9f30b-160">0</span><span class="sxs-lookup"><span data-stu-id="9f30b-160">0</span></span> | <span data-ttu-id="9f30b-161">Berücksichtigen Sie alle Funktionen im Vergleich.</span><span class="sxs-lookup"><span data-stu-id="9f30b-161">Consider all features in the comparison.</span></span> |

## <a name="requirements"></a><span data-ttu-id="9f30b-162">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9f30b-162">Requirements</span></span>  
 <span data-ttu-id="9f30b-163">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f30b-163">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f30b-164">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9f30b-164">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="9f30b-165">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9f30b-165">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f30b-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f30b-166">See also</span></span>  
[<span data-ttu-id="9f30b-167">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="9f30b-167">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
