---
title: Beginenumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die beginenumeration-Funktion setzt einen Enumerator auf den Anfang der Enumeration zurück.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de36650aa2b206b5e9734b38c6067a3a79de610c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798794"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="187ba-103">BeginEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="187ba-103">BeginEnumeration function</span></span>
<span data-ttu-id="187ba-104">Setzt einen Enumerator auf den Anfang der-Enumeration zurück.</span><span class="sxs-lookup"><span data-stu-id="187ba-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="187ba-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="187ba-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="187ba-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="187ba-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="187ba-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="187ba-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="187ba-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="187ba-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`\
<span data-ttu-id="187ba-109">in Eine bitweise Kombination der Flags oder Werte, die im Abschnitt " [Hinweise](#remarks) " beschrieben werden, die die in der-Enumeration enthaltenen Eigenschaften steuert.</span><span class="sxs-lookup"><span data-stu-id="187ba-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="187ba-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="187ba-110">Return value</span></span>

<span data-ttu-id="187ba-111">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="187ba-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="187ba-112">Konstante</span><span class="sxs-lookup"><span data-stu-id="187ba-112">Constant</span></span>  |<span data-ttu-id="187ba-113">Wert</span><span class="sxs-lookup"><span data-stu-id="187ba-113">Value</span></span>  |<span data-ttu-id="187ba-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="187ba-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="187ba-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="187ba-115">0x80041008</span></span> | <span data-ttu-id="187ba-116">Die Kombination von Flags `lEnumFlags` in ist ungültig, oder es wurde ein ungültiges Argument angegeben.</span><span class="sxs-lookup"><span data-stu-id="187ba-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="187ba-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="187ba-117">0x8004101d</span></span> | <span data-ttu-id="187ba-118">Es `BeginEnumeration` wurde ein zweiter-Rückruf ohne einen dazwischen liegenden- [`EndEnumeration`](endenumeration.md)Rückruf durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="187ba-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="187ba-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="187ba-119">0x80041006</span></span> | <span data-ttu-id="187ba-120">Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="187ba-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="187ba-121">0</span><span class="sxs-lookup"><span data-stu-id="187ba-121">0</span></span> | <span data-ttu-id="187ba-122">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="187ba-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="187ba-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="187ba-123">Remarks</span></span>

<span data-ttu-id="187ba-124">Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: beginenumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Methode.</span><span class="sxs-lookup"><span data-stu-id="187ba-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="187ba-125">Die Flags, die als `lEnumFlags` Argument übermittelt werden können, werden in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren.</span><span class="sxs-lookup"><span data-stu-id="187ba-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="187ba-126">Sie können ein Flag aus jeder Gruppe mit einem beliebigen Flag aus einer beliebigen anderen Gruppe kombinieren.</span><span class="sxs-lookup"><span data-stu-id="187ba-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="187ba-127">Flags aus derselben Gruppe schließen sich jedoch gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="187ba-127">However, flags from the same group are mutually exclusive.</span></span> 

<span data-ttu-id="187ba-128">**Gruppe 1**</span><span class="sxs-lookup"><span data-stu-id="187ba-128">**Group 1**</span></span>

|<span data-ttu-id="187ba-129">Konstante</span><span class="sxs-lookup"><span data-stu-id="187ba-129">Constant</span></span>  |<span data-ttu-id="187ba-130">Wert</span><span class="sxs-lookup"><span data-stu-id="187ba-130">Value</span></span>  |<span data-ttu-id="187ba-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="187ba-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="187ba-132">0x4</span><span class="sxs-lookup"><span data-stu-id="187ba-132">0x4</span></span> | <span data-ttu-id="187ba-133">Schließt Eigenschaften ein, die nur den Schlüssel bilden.</span><span class="sxs-lookup"><span data-stu-id="187ba-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="187ba-134">0x8</span><span class="sxs-lookup"><span data-stu-id="187ba-134">0x8</span></span> | <span data-ttu-id="187ba-135">Schließt Eigenschaften ein, die nur Objekt Verweise sind.</span><span class="sxs-lookup"><span data-stu-id="187ba-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="187ba-136">**Gruppe 2**</span><span class="sxs-lookup"><span data-stu-id="187ba-136">**Group 2**</span></span>

<span data-ttu-id="187ba-137">Konstante</span><span class="sxs-lookup"><span data-stu-id="187ba-137">Constant</span></span>  |<span data-ttu-id="187ba-138">Wert</span><span class="sxs-lookup"><span data-stu-id="187ba-138">Value</span></span>  |<span data-ttu-id="187ba-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="187ba-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="187ba-140">0x30</span><span class="sxs-lookup"><span data-stu-id="187ba-140">0x30</span></span> | <span data-ttu-id="187ba-141">Beschränken Sie die Enumeration auf Systemeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="187ba-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="187ba-142">0x40</span><span class="sxs-lookup"><span data-stu-id="187ba-142">0x40</span></span> | <span data-ttu-id="187ba-143">Schließt lokale und weitergeleitete Eigenschaften ein, aber schließt Systemeigenschaften aus der-Enumeration aus.</span><span class="sxs-lookup"><span data-stu-id="187ba-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="187ba-144">Für Klassen:</span><span class="sxs-lookup"><span data-stu-id="187ba-144">For classes:</span></span>

<span data-ttu-id="187ba-145">Konstante</span><span class="sxs-lookup"><span data-stu-id="187ba-145">Constant</span></span>  |<span data-ttu-id="187ba-146">Wert</span><span class="sxs-lookup"><span data-stu-id="187ba-146">Value</span></span>  |<span data-ttu-id="187ba-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="187ba-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="187ba-148">0x100</span><span class="sxs-lookup"><span data-stu-id="187ba-148">0x100</span></span> | <span data-ttu-id="187ba-149">Beschränken Sie die Enumeration auf Eigenschaften, die in der Klassendefinition überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="187ba-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="187ba-150">0x100</span><span class="sxs-lookup"><span data-stu-id="187ba-150">0x100</span></span> | <span data-ttu-id="187ba-151">Beschränken Sie die-Enumeration auf Eigenschaften, die in der aktuellen Klassendefinition und auf neue in der-Klasse definierte Eigenschaften überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="187ba-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="187ba-152">0x300</span><span class="sxs-lookup"><span data-stu-id="187ba-152">0x300</span></span> | <span data-ttu-id="187ba-153">Eine Maske (anstelle eines Flags), die auf einen `lEnumFlags` Wert angewendet werden soll, um zu überprüfen, ob entweder `WBEM_FLAG_CLASS_OVERRIDES_ONLY` oder `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="187ba-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="187ba-154">0x10</span><span class="sxs-lookup"><span data-stu-id="187ba-154">0x10</span></span> | <span data-ttu-id="187ba-155">Beschränken Sie die Enumeration auf Eigenschaften, die in der Klasse selbst definiert oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="187ba-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="187ba-156">0x20</span><span class="sxs-lookup"><span data-stu-id="187ba-156">0x20</span></span> | <span data-ttu-id="187ba-157">Beschränken Sie die Enumeration auf Eigenschaften, die von Basisklassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="187ba-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="187ba-158">Für-Instanzen:</span><span class="sxs-lookup"><span data-stu-id="187ba-158">For instances:</span></span>

<span data-ttu-id="187ba-159">Konstante</span><span class="sxs-lookup"><span data-stu-id="187ba-159">Constant</span></span>  |<span data-ttu-id="187ba-160">Wert</span><span class="sxs-lookup"><span data-stu-id="187ba-160">Value</span></span>  |<span data-ttu-id="187ba-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="187ba-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="187ba-162">0x10</span><span class="sxs-lookup"><span data-stu-id="187ba-162">0x10</span></span> | <span data-ttu-id="187ba-163">Beschränken Sie die Enumeration auf Eigenschaften, die in der Klasse selbst definiert oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="187ba-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="187ba-164">0x20</span><span class="sxs-lookup"><span data-stu-id="187ba-164">0x20</span></span> | <span data-ttu-id="187ba-165">Beschränken Sie die Enumeration auf Eigenschaften, die von Basisklassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="187ba-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="187ba-166">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="187ba-166">Requirements</span></span>  
 <span data-ttu-id="187ba-167">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="187ba-167">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="187ba-168">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="187ba-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="187ba-169">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="187ba-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="187ba-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="187ba-170">See also</span></span>

- [<span data-ttu-id="187ba-171">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="187ba-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
