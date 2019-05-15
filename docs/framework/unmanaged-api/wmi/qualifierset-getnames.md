---
title: QualifierSet_GetNames-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_GetNames-Funktion ruft die Namen der Qualifizierer aus einem Objekt oder die Eigenschaft ab.
ms.date: 11/06/2017
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 402d56b44c2b6f53f901e35c6d7b965811a40344
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636589"
---
# <a name="qualifiersetgetnames-function"></a><span data-ttu-id="20cbb-103">QualifierSet_GetNames-Funktion</span><span class="sxs-lookup"><span data-stu-id="20cbb-103">QualifierSet_GetNames function</span></span>

<span data-ttu-id="20cbb-104">Ruft die Namen der alle Qualifizierer oder bestimmte Qualifizierer angegeben, die aus dem aktuellen Objekt oder eine Eigenschaft verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="20cbb-104">Retrieves the names of all the qualifiers or of certain qualifiers that are available from the current object or property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="20cbb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="20cbb-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
);
```

## <a name="parameters"></a><span data-ttu-id="20cbb-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="20cbb-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="20cbb-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="20cbb-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="20cbb-108">[in] Ein Zeiger auf ein [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) Instanz.</span><span class="sxs-lookup"><span data-stu-id="20cbb-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="20cbb-109">[in] Einer der folgenden Flags oder Werte, der angibt, welche Namen in der Enumeration einschließen.</span><span class="sxs-lookup"><span data-stu-id="20cbb-109">[in] One of the following flags or values that specifies which names to include in the enumeration.</span></span>

|<span data-ttu-id="20cbb-110">Konstante</span><span class="sxs-lookup"><span data-stu-id="20cbb-110">Constant</span></span>  |<span data-ttu-id="20cbb-111">Wert</span><span class="sxs-lookup"><span data-stu-id="20cbb-111">Value</span></span>  |<span data-ttu-id="20cbb-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="20cbb-112">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="20cbb-113">0</span><span class="sxs-lookup"><span data-stu-id="20cbb-113">0</span></span> | <span data-ttu-id="20cbb-114">Die Namen aller Qualifizierer zurück</span><span class="sxs-lookup"><span data-stu-id="20cbb-114">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="20cbb-115">0x10</span><span class="sxs-lookup"><span data-stu-id="20cbb-115">0x10</span></span> | <span data-ttu-id="20cbb-116">Nur die Namen der Qualifizierer an die current-Eigenschaft oder das Objekt bestimmte zurück.</span><span class="sxs-lookup"><span data-stu-id="20cbb-116">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="20cbb-117">Für eine Eigenschaft: Nur die Qualifizierer, die spezifisch für die Eigenschaft (einschließlich Außerkraftsetzungen) und nicht die Qualifizierer, die aus der Definition der Klasse weitergegeben zurück.</span><span class="sxs-lookup"><span data-stu-id="20cbb-117">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="20cbb-118">Für eine Instanz: Geben Sie nur instanzspezifischen Qualifizierer-Namen zurück.</span><span class="sxs-lookup"><span data-stu-id="20cbb-118">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="20cbb-119">Für eine Klasse: Nur Qualifizierer an der abgeleiteten Klasse bestimmte zurück.</span><span class="sxs-lookup"><span data-stu-id="20cbb-119">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="20cbb-120">0x20</span><span class="sxs-lookup"><span data-stu-id="20cbb-120">0x20</span></span> | <span data-ttu-id="20cbb-121">Rückgabe, nur die Namen der Qualifizierer weitergegeben aus einem anderen Objekt.</span><span class="sxs-lookup"><span data-stu-id="20cbb-121">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="20cbb-122">Für eine Eigenschaft: Rückgabe, nur die Qualifizierer weitergegeben für diese Eigenschaft aus der Klassendefinition und nicht die von der Eigenschaft selbst.</span><span class="sxs-lookup"><span data-stu-id="20cbb-122">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="20cbb-123">Für eine Instanz: Rückgabe, nur diese Qualifizierer weitergegeben aus der Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="20cbb-123">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="20cbb-124">Für eine Klasse: Die Rückgabe nur die Namen dieser Qualifizierer von den übergeordneten Klassen geerbt.</span><span class="sxs-lookup"><span data-stu-id="20cbb-124">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

`pstrNames`\
<span data-ttu-id="20cbb-125">[out] Ein neues `SAFEARRAY` , die den angeforderten Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="20cbb-125">[out] A new `SAFEARRAY` that contains the requested names.</span></span> <span data-ttu-id="20cbb-126">Das Array kann 0 Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="20cbb-126">The array can have 0 elements.</span></span> <span data-ttu-id="20cbb-127">Wenn ein Fehler auftritt, ein neues `SAFEARRAY` wird nicht zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="20cbb-127">If an error occurs, a new `SAFEARRAY` is not returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="20cbb-128">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="20cbb-128">Return value</span></span>

<span data-ttu-id="20cbb-129">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="20cbb-129">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="20cbb-130">Konstante</span><span class="sxs-lookup"><span data-stu-id="20cbb-130">Constant</span></span>  |<span data-ttu-id="20cbb-131">Wert</span><span class="sxs-lookup"><span data-stu-id="20cbb-131">Value</span></span>  |<span data-ttu-id="20cbb-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="20cbb-132">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="20cbb-133">0x80041008</span><span class="sxs-lookup"><span data-stu-id="20cbb-133">0x80041008</span></span> | <span data-ttu-id="20cbb-134">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="20cbb-134">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="20cbb-135">0x80041006</span><span class="sxs-lookup"><span data-stu-id="20cbb-135">0x80041006</span></span> | <span data-ttu-id="20cbb-136">Es ist nicht genügend Arbeitsspeicher zur Verfügung, um eine neue Enumeration beginnen.</span><span class="sxs-lookup"><span data-stu-id="20cbb-136">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="20cbb-137">0</span><span class="sxs-lookup"><span data-stu-id="20cbb-137">0</span></span> | <span data-ttu-id="20cbb-138">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="20cbb-138">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="20cbb-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20cbb-139">Remarks</span></span>

<span data-ttu-id="20cbb-140">Diese Funktion umschließt einen Aufruf der [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) Methode.</span><span class="sxs-lookup"><span data-stu-id="20cbb-140">This function wraps a call to the [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) method.</span></span>

<span data-ttu-id="20cbb-141">Nachdem Sie die Namen des Qualifizierers abgerufen haben, können Sie jede Qualifizierer anhand des Namens zugreifen, durch den Aufruf der [QualifierSet_Get](qualifierset-get.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="20cbb-141">Once you've retrieved the qualifier names, you can access each qualifier by name by calling the [QualifierSet_Get](qualifierset-get.md) function.</span></span>

<span data-ttu-id="20cbb-142">Es ist kein Fehler für ein bestimmtes Objekt auf 0 (null) Qualifizierer enthalten, also die Anzahl der Zeichenfolgen in `pstrNames` bei der Rückgabe "0" sein, obwohl die Funktion gibt `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="20cbb-142">It is not an error for a given object to have zero qualifiers, so the number of strings in `pstrNames` on return can be 0, even though the function returns `WBEM_S_NO_ERROR`.</span></span>

## <a name="requirements"></a><span data-ttu-id="20cbb-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="20cbb-143">Requirements</span></span>

<span data-ttu-id="20cbb-144">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20cbb-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="20cbb-145">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="20cbb-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="20cbb-146">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="20cbb-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="20cbb-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20cbb-147">See also</span></span>

- [<span data-ttu-id="20cbb-148">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="20cbb-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
