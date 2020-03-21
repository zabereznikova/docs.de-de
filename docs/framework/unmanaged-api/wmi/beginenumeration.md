---
title: BeginEnumeration-Funktion (Nicht verwaltete API-Referenz)
description: Die BeginEnumeration-Funktion setzt einen Enumerator auf den Anfang der Enumeration zurück.
ms.date: 11/06/2017
api_name:
- BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginEnumeration
helpviewer_keywords:
- BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: eac23916bd78ec3970a87566e2d2f4d79b379824
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176876"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="80728-103">BeginEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="80728-103">BeginEnumeration function</span></span>
<span data-ttu-id="80728-104">Setzt einen Enumerator auf den Anfang der Enumeration zurück.</span><span class="sxs-lookup"><span data-stu-id="80728-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="80728-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="80728-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lEnumFlags
);
```  

## <a name="parameters"></a><span data-ttu-id="80728-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="80728-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="80728-107">[in] Dieser Parameter ist nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="80728-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="80728-108">[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="80728-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`\
<span data-ttu-id="80728-109">[in] Eine bitweise Kombination der Flags oder Werte, die im Abschnitt ["Hinweise"](#remarks) beschrieben werden und die in der Enumeration enthaltenen Eigenschaften steuern.</span><span class="sxs-lookup"><span data-stu-id="80728-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="80728-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="80728-110">Return value</span></span>

<span data-ttu-id="80728-111">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="80728-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="80728-112">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="80728-112">Constant</span></span>  |<span data-ttu-id="80728-113">value</span><span class="sxs-lookup"><span data-stu-id="80728-113">Value</span></span>  |<span data-ttu-id="80728-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80728-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="80728-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="80728-115">0x80041008</span></span> | <span data-ttu-id="80728-116">Die Kombination von `lEnumFlags` Flags in ist ungültig, oder es wurde ein ungültiges Argument angegeben.</span><span class="sxs-lookup"><span data-stu-id="80728-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="80728-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="80728-117">0x8004101d</span></span> | <span data-ttu-id="80728-118">Ein zweiter `BeginEnumeration` Anruf erfolgte ohne einen dazwischen [`EndEnumeration`](endenumeration.md)liegenden Anruf bei .</span><span class="sxs-lookup"><span data-stu-id="80728-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="80728-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="80728-119">0x80041006</span></span> | <span data-ttu-id="80728-120">Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu starten.</span><span class="sxs-lookup"><span data-stu-id="80728-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="80728-121">0</span><span class="sxs-lookup"><span data-stu-id="80728-121">0</span></span> | <span data-ttu-id="80728-122">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="80728-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="80728-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="80728-123">Remarks</span></span>

<span data-ttu-id="80728-124">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::BeginEnumeration-Methode.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="80728-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="80728-125">Die Flags, die als `lEnumFlags` Argument übergeben werden können, werden in der *Headerdatei WbemCli.h* definiert, oder Sie können sie als Konstanten im Code definieren.</span><span class="sxs-lookup"><span data-stu-id="80728-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="80728-126">Sie können ein Flag aus jeder Gruppe mit einem beliebigen Flag aus einer anderen Gruppe kombinieren.</span><span class="sxs-lookup"><span data-stu-id="80728-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="80728-127">Flags derselben Gruppe schließen sich jedoch gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="80728-127">However, flags from the same group are mutually exclusive.</span></span>

<span data-ttu-id="80728-128">**Gruppe 1**</span><span class="sxs-lookup"><span data-stu-id="80728-128">**Group 1**</span></span>

|<span data-ttu-id="80728-129">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="80728-129">Constant</span></span>  |<span data-ttu-id="80728-130">value</span><span class="sxs-lookup"><span data-stu-id="80728-130">Value</span></span>  |<span data-ttu-id="80728-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80728-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="80728-132">0x4</span><span class="sxs-lookup"><span data-stu-id="80728-132">0x4</span></span> | <span data-ttu-id="80728-133">Schließen Sie Eigenschaften ein, die nur den Schlüssel darstellen.</span><span class="sxs-lookup"><span data-stu-id="80728-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="80728-134">0x8</span><span class="sxs-lookup"><span data-stu-id="80728-134">0x8</span></span> | <span data-ttu-id="80728-135">Schließen Sie Eigenschaften ein, die nur Objektverweise sind.</span><span class="sxs-lookup"><span data-stu-id="80728-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="80728-136">**Gruppe 2**</span><span class="sxs-lookup"><span data-stu-id="80728-136">**Group 2**</span></span>

<span data-ttu-id="80728-137">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="80728-137">Constant</span></span>  |<span data-ttu-id="80728-138">value</span><span class="sxs-lookup"><span data-stu-id="80728-138">Value</span></span>  |<span data-ttu-id="80728-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80728-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="80728-140">0x30</span><span class="sxs-lookup"><span data-stu-id="80728-140">0x30</span></span> | <span data-ttu-id="80728-141">Beschränken Sie die Enumeration auf Systemeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="80728-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="80728-142">0x40</span><span class="sxs-lookup"><span data-stu-id="80728-142">0x40</span></span> | <span data-ttu-id="80728-143">Schließen Sie lokale und weitergegebene Eigenschaften ein, schließen Sie jedoch Systemeigenschaften aus der Enumeration aus.</span><span class="sxs-lookup"><span data-stu-id="80728-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="80728-144">Für Klassen:</span><span class="sxs-lookup"><span data-stu-id="80728-144">For classes:</span></span>

<span data-ttu-id="80728-145">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="80728-145">Constant</span></span>  |<span data-ttu-id="80728-146">value</span><span class="sxs-lookup"><span data-stu-id="80728-146">Value</span></span>  |<span data-ttu-id="80728-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80728-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="80728-148">0x100</span><span class="sxs-lookup"><span data-stu-id="80728-148">0x100</span></span> | <span data-ttu-id="80728-149">Beschränken Sie die Enumeration auf Eigenschaften, die in der Klassendefinition überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="80728-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="80728-150">0x100</span><span class="sxs-lookup"><span data-stu-id="80728-150">0x100</span></span> | <span data-ttu-id="80728-151">Beschränken Sie die Enumeration auf Eigenschaften, die in der aktuellen Klassendefinition überschrieben werden, und auf neue Eigenschaften, die in der Klasse definiert sind.</span><span class="sxs-lookup"><span data-stu-id="80728-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="80728-152">0x300</span><span class="sxs-lookup"><span data-stu-id="80728-152">0x300</span></span> | <span data-ttu-id="80728-153">Eine Maske (anstelle eines Flags), `lEnumFlags` die auf einen `WBEM_FLAG_CLASS_OVERRIDES_ONLY` `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` Wert angewendet werden soll, um zu überprüfen, ob eine oder ist festgelegt.</span><span class="sxs-lookup"><span data-stu-id="80728-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="80728-154">0x10</span><span class="sxs-lookup"><span data-stu-id="80728-154">0x10</span></span> | <span data-ttu-id="80728-155">Beschränken Sie die Enumeration auf Eigenschaften, die in der Klasse selbst definiert oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="80728-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="80728-156">0x20</span><span class="sxs-lookup"><span data-stu-id="80728-156">0x20</span></span> | <span data-ttu-id="80728-157">Beschränken Sie die Enumeration auf Eigenschaften, die von Basisklassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="80728-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="80728-158">Für Instanzen:</span><span class="sxs-lookup"><span data-stu-id="80728-158">For instances:</span></span>

<span data-ttu-id="80728-159">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="80728-159">Constant</span></span>  |<span data-ttu-id="80728-160">value</span><span class="sxs-lookup"><span data-stu-id="80728-160">Value</span></span>  |<span data-ttu-id="80728-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80728-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="80728-162">0x10</span><span class="sxs-lookup"><span data-stu-id="80728-162">0x10</span></span> | <span data-ttu-id="80728-163">Beschränken Sie die Enumeration auf Eigenschaften, die in der Klasse selbst definiert oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="80728-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="80728-164">0x20</span><span class="sxs-lookup"><span data-stu-id="80728-164">0x20</span></span> | <span data-ttu-id="80728-165">Beschränken Sie die Enumeration auf Eigenschaften, die von Basisklassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="80728-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="80728-166">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="80728-166">Requirements</span></span>  
 <span data-ttu-id="80728-167">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80728-167">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80728-168">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="80728-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="80728-169">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="80728-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80728-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="80728-170">See also</span></span>

- [<span data-ttu-id="80728-171">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="80728-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
