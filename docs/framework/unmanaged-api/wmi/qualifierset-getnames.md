---
title: QualifierSet_GetNames-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_GetNames-Funktion Ruft die Namen der Qualifizierer aus einem Objekt oder einer Eigenschaft ab.
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
ms.openlocfilehash: bd0a67987dd8ffa825114726d066249aed40cf05
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141696"
---
# <a name="qualifierset_getnames-function"></a><span data-ttu-id="44ccb-103">QualifierSet_GetNames-Funktion</span><span class="sxs-lookup"><span data-stu-id="44ccb-103">QualifierSet_GetNames function</span></span>

<span data-ttu-id="44ccb-104">Ruft die Namen aller Qualifizierer oder bestimmter Qualifizierer ab, die vom aktuellen-Objekt oder der aktuellen Eigenschaft verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="44ccb-104">Retrieves the names of all the qualifiers or of certain qualifiers that are available from the current object or property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="44ccb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="44ccb-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
);
```

## <a name="parameters"></a><span data-ttu-id="44ccb-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="44ccb-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="44ccb-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="44ccb-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="44ccb-108">in Ein Zeiger auf eine [iwbemqualifierset](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="44ccb-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="44ccb-109">in Eines der folgenden Flags oder Werte, das angibt, welche Namen in die-Enumeration eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="44ccb-109">[in] One of the following flags or values that specifies which names to include in the enumeration.</span></span>

|<span data-ttu-id="44ccb-110">Konstante</span><span class="sxs-lookup"><span data-stu-id="44ccb-110">Constant</span></span>  |<span data-ttu-id="44ccb-111">Wert</span><span class="sxs-lookup"><span data-stu-id="44ccb-111">Value</span></span>  |<span data-ttu-id="44ccb-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="44ccb-112">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="44ccb-113">0</span><span class="sxs-lookup"><span data-stu-id="44ccb-113">0</span></span> | <span data-ttu-id="44ccb-114">Gibt die Namen aller Qualifizierer zurück.</span><span class="sxs-lookup"><span data-stu-id="44ccb-114">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="44ccb-115">0x10</span><span class="sxs-lookup"><span data-stu-id="44ccb-115">0x10</span></span> | <span data-ttu-id="44ccb-116">Gibt nur die Namen der Qualifizierer zurück, die speziell für die aktuelle Eigenschaft oder das aktuelle Objekt</span><span class="sxs-lookup"><span data-stu-id="44ccb-116">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="44ccb-117">Für eine Eigenschaft: gibt nur die Qualifizierer zurück, die für die Eigenschaft spezifisch sind (einschließlich über schreibungen), nicht die Qualifizierer, die von der Klassendefinition weitergegeben werden</span><span class="sxs-lookup"><span data-stu-id="44ccb-117">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="44ccb-118">Für eine-Instanz: gibt nur instanzspezifische Qualifizierernamen zurück.</span><span class="sxs-lookup"><span data-stu-id="44ccb-118">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="44ccb-119">Für eine Klasse: gibt nur Qualifizierer zurück, die für die abgeleitete Klasse spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="44ccb-119">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="44ccb-120">0x20</span><span class="sxs-lookup"><span data-stu-id="44ccb-120">0x20</span></span> | <span data-ttu-id="44ccb-121">Gibt nur die Namen der Qualifizierer zurück, die von einem anderen-Objekt</span><span class="sxs-lookup"><span data-stu-id="44ccb-121">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="44ccb-122">Für eine Eigenschaft: gibt nur die Qualifizierer zurück, die von der Klassendefinition an diese Eigenschaft weitergegeben werden, und nicht die der Eigenschaft selbst.</span><span class="sxs-lookup"><span data-stu-id="44ccb-122">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="44ccb-123">Für eine Instanz: gibt nur die Qualifizierer zurück, die aus der Klassendefinition weitergegeben wurden</span><span class="sxs-lookup"><span data-stu-id="44ccb-123">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="44ccb-124">Für eine Klasse: gibt nur die Qualifizierernamen zurück, die von den übergeordneten Klassen geerbt wurden.</span><span class="sxs-lookup"><span data-stu-id="44ccb-124">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

`pstrNames`\
<span data-ttu-id="44ccb-125">vorgenommen Ein neues `SAFEARRAY`, das die angeforderten Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="44ccb-125">[out] A new `SAFEARRAY` that contains the requested names.</span></span> <span data-ttu-id="44ccb-126">Das Array kann über 0 Elemente verfügen.</span><span class="sxs-lookup"><span data-stu-id="44ccb-126">The array can have 0 elements.</span></span> <span data-ttu-id="44ccb-127">Wenn ein Fehler auftritt, wird keine neue `SAFEARRAY` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="44ccb-127">If an error occurs, a new `SAFEARRAY` is not returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="44ccb-128">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="44ccb-128">Return value</span></span>

<span data-ttu-id="44ccb-129">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="44ccb-129">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="44ccb-130">Konstante</span><span class="sxs-lookup"><span data-stu-id="44ccb-130">Constant</span></span>  |<span data-ttu-id="44ccb-131">Wert</span><span class="sxs-lookup"><span data-stu-id="44ccb-131">Value</span></span>  |<span data-ttu-id="44ccb-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="44ccb-132">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="44ccb-133">0x80041008</span><span class="sxs-lookup"><span data-stu-id="44ccb-133">0x80041008</span></span> | <span data-ttu-id="44ccb-134">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="44ccb-134">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="44ccb-135">0x80041006</span><span class="sxs-lookup"><span data-stu-id="44ccb-135">0x80041006</span></span> | <span data-ttu-id="44ccb-136">Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="44ccb-136">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="44ccb-137">0</span><span class="sxs-lookup"><span data-stu-id="44ccb-137">0</span></span> | <span data-ttu-id="44ccb-138">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="44ccb-138">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="44ccb-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="44ccb-139">Remarks</span></span>

<span data-ttu-id="44ccb-140">Diese Funktion umschließt einen aufzurufenden Befehl der [iwbemqualifierset:: GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) -Methode.</span><span class="sxs-lookup"><span data-stu-id="44ccb-140">This function wraps a call to the [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) method.</span></span>

<span data-ttu-id="44ccb-141">Nachdem Sie die Qualifizierernamen abgerufen haben, können Sie über den Namen auf jeden Qualifizierer zugreifen, indem Sie die Funktion [QualifierSet_Get](qualifierset-get.md) aufrufen.</span><span class="sxs-lookup"><span data-stu-id="44ccb-141">Once you've retrieved the qualifier names, you can access each qualifier by name by calling the [QualifierSet_Get](qualifierset-get.md) function.</span></span>

<span data-ttu-id="44ccb-142">Es ist kein Fehler für ein angegebenes Objekt, wenn keine Qualifizierer vorhanden sind. Daher kann die Anzahl der Zeichen folgen in `pstrNames` bei Rückgabe 0 sein, auch wenn die Funktion `WBEM_S_NO_ERROR`zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="44ccb-142">It is not an error for a given object to have zero qualifiers, so the number of strings in `pstrNames` on return can be 0, even though the function returns `WBEM_S_NO_ERROR`.</span></span>

## <a name="requirements"></a><span data-ttu-id="44ccb-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="44ccb-143">Requirements</span></span>

<span data-ttu-id="44ccb-144">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44ccb-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="44ccb-145">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="44ccb-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="44ccb-146">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="44ccb-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="44ccb-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44ccb-147">See also</span></span>

- [<span data-ttu-id="44ccb-148">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="44ccb-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
