---
title: QualifierSet_BeginEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion QualifierSet_BeginEnumeration setzt einen Enumerator der Qualifizierer eines Objekts zurück.
ms.date: 11/06/2017
api_name:
- QualifierSet_BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_BeginEnumeration
helpviewer_keywords:
- QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f663434d3e3d44dc0c406e71592651493bd8f8dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597238"
---
# <a name="qualifiersetbeginenumeration-function"></a><span data-ttu-id="dfdfa-103">QualifierSet_BeginEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="dfdfa-103">QualifierSet_BeginEnumeration function</span></span>

<span data-ttu-id="dfdfa-104">Setzt einen Enumerator der Qualifizierer eines Objekts auf den Anfang der Enumeration zurück.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="dfdfa-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="dfdfa-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags
);
```

## <a name="parameters"></a><span data-ttu-id="dfdfa-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="dfdfa-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="dfdfa-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="dfdfa-108">[in] Ein Zeiger auf ein [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) Instanz.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="dfdfa-109">[in] Eine bitweise Kombination der Flags oder Werte, die in beschriebenen der ["Hinweise"](#remarks) Abschnitt, der angibt, die Qualifizierer in der Enumeration einschließen.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="dfdfa-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dfdfa-110">Return value</span></span>

<span data-ttu-id="dfdfa-111">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="dfdfa-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="dfdfa-112">Konstante</span><span class="sxs-lookup"><span data-stu-id="dfdfa-112">Constant</span></span>  |<span data-ttu-id="dfdfa-113">Wert</span><span class="sxs-lookup"><span data-stu-id="dfdfa-113">Value</span></span>  |<span data-ttu-id="dfdfa-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dfdfa-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="dfdfa-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="dfdfa-115">0x80041008</span></span> | <span data-ttu-id="dfdfa-116">Der `lFlags`-Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="dfdfa-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="dfdfa-117">0x8004101d</span></span> | <span data-ttu-id="dfdfa-118">Einen zweiten Aufruf von `QualifierSet_BeginEnumeration` wurde ohne einen zwischenzeitlichen Aufruf versucht [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="dfdfa-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="dfdfa-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="dfdfa-119">0x80041006</span></span> | <span data-ttu-id="dfdfa-120">Es ist nicht genügend Arbeitsspeicher zur Verfügung, um eine neue Enumeration beginnen.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="dfdfa-121">0</span><span class="sxs-lookup"><span data-stu-id="dfdfa-121">0</span></span> | <span data-ttu-id="dfdfa-122">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-122">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="dfdfa-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dfdfa-123">Remarks</span></span>

<span data-ttu-id="dfdfa-124">Diese Funktion umschließt einen Aufruf der [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) Methode.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) method.</span></span>

<span data-ttu-id="dfdfa-125">Zum Aufzählen aller die Qualifizierer für ein Objekt muss vor dem ersten Aufruf dieser Methode aufgerufen werden [QualifierSet_Next](qualifierset-next.md).</span><span class="sxs-lookup"><span data-stu-id="dfdfa-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="dfdfa-126">Die Reihenfolge, in der aufgelisteten Qualifizierer, ist garantiert Invarianten für eine angegebene Enumeration.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="dfdfa-127">Die Flags, die als übergeben werden können die `lEnumFlags` Argument definiert werden, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

|<span data-ttu-id="dfdfa-128">Konstante</span><span class="sxs-lookup"><span data-stu-id="dfdfa-128">Constant</span></span>  |<span data-ttu-id="dfdfa-129">Wert</span><span class="sxs-lookup"><span data-stu-id="dfdfa-129">Value</span></span>  |<span data-ttu-id="dfdfa-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dfdfa-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="dfdfa-131">0</span><span class="sxs-lookup"><span data-stu-id="dfdfa-131">0</span></span> | <span data-ttu-id="dfdfa-132">Die Namen aller Qualifizierer zurück</span><span class="sxs-lookup"><span data-stu-id="dfdfa-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="dfdfa-133">0x10</span><span class="sxs-lookup"><span data-stu-id="dfdfa-133">0x10</span></span> | <span data-ttu-id="dfdfa-134">Nur die Namen der Qualifizierer an die current-Eigenschaft oder das Objekt bestimmte zurück.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="dfdfa-135">Für eine Eigenschaft: Nur die Qualifizierer, die spezifisch für die Eigenschaft (einschließlich Außerkraftsetzungen) und nicht die Qualifizierer, die aus der Definition der Klasse weitergegeben zurück.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="dfdfa-136">Für eine Instanz: Geben Sie nur instanzspezifischen Qualifizierer-Namen zurück.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="dfdfa-137">Für eine Klasse: Nur Qualifizierer an der abgeleiteten Klasse bestimmte zurück.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-137">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="dfdfa-138">0x20</span><span class="sxs-lookup"><span data-stu-id="dfdfa-138">0x20</span></span> | <span data-ttu-id="dfdfa-139">Rückgabe, nur die Namen der Qualifizierer weitergegeben aus einem anderen Objekt.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="dfdfa-140">Für eine Eigenschaft: Rückgabe, nur die Qualifizierer weitergegeben für diese Eigenschaft aus der Klassendefinition und nicht die von der Eigenschaft selbst.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="dfdfa-141">Für eine Instanz: Rückgabe, nur diese Qualifizierer weitergegeben aus der Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="dfdfa-142">Für eine Klasse: Die Rückgabe nur die Namen dieser Qualifizierer von den übergeordneten Klassen geerbt.</span><span class="sxs-lookup"><span data-stu-id="dfdfa-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="dfdfa-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dfdfa-143">Requirements</span></span>

<span data-ttu-id="dfdfa-144">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfdfa-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="dfdfa-145">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="dfdfa-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="dfdfa-146">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dfdfa-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="dfdfa-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfdfa-147">See also</span></span>

- [<span data-ttu-id="dfdfa-148">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="dfdfa-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)