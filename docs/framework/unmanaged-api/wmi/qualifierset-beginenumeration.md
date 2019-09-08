---
title: QualifierSet_BeginEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_BeginEnumeration-Funktion setzt einen Enumerator der Qualifizierer eines Objekts zurück.
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
ms.openlocfilehash: 3b75c51ebddd78e447fed57b22a96c2d5c35004e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798346"
---
# <a name="qualifierset_beginenumeration-function"></a><span data-ttu-id="d4d4e-103">QualifierSet_BeginEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="d4d4e-103">QualifierSet_BeginEnumeration function</span></span>

<span data-ttu-id="d4d4e-104">Setzt einen Enumerator der Qualifizierer eines Objekts auf den Anfang der Enumeration zurück.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="d4d4e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4d4e-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags
);
```

## <a name="parameters"></a><span data-ttu-id="d4d4e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d4d4e-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="d4d4e-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="d4d4e-108">in Ein Zeiger auf eine [iwbemqualifierset](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="d4d4e-109">in Eine bitweise Kombination der im Abschnitt " [Hinweise](#remarks) " beschriebenen Flags oder Werte, die die Qualifizierer angibt, die in der-Enumeration enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="d4d4e-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d4d4e-110">Return value</span></span>

<span data-ttu-id="d4d4e-111">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="d4d4e-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d4d4e-112">Konstante</span><span class="sxs-lookup"><span data-stu-id="d4d4e-112">Constant</span></span>  |<span data-ttu-id="d4d4e-113">Wert</span><span class="sxs-lookup"><span data-stu-id="d4d4e-113">Value</span></span>  |<span data-ttu-id="d4d4e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4d4e-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d4d4e-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="d4d4e-115">0x80041008</span></span> | <span data-ttu-id="d4d4e-116">Der `lFlags`-Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="d4d4e-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="d4d4e-117">0x8004101d</span></span> | <span data-ttu-id="d4d4e-118">Es `QualifierSet_BeginEnumeration` wurde ein zweiter-Rückruf ohne einen dazwischen liegenden- [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md)Rückruf durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="d4d4e-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="d4d4e-119">0x80041006</span></span> | <span data-ttu-id="d4d4e-120">Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="d4d4e-121">0</span><span class="sxs-lookup"><span data-stu-id="d4d4e-121">0</span></span> | <span data-ttu-id="d4d4e-122">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-122">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="d4d4e-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d4d4e-123">Remarks</span></span>

<span data-ttu-id="d4d4e-124">Diese Funktion umschließt einen aufzurufenden Befehl der [iwbemqualifierset:: beginenumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) -Methode.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) method.</span></span>

<span data-ttu-id="d4d4e-125">Um alle Qualifizierer eines Objekts aufzulisten, muss diese Methode vor dem ersten Aufruf von [QualifierSet_Next](qualifierset-next.md)aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="d4d4e-126">Die Reihenfolge, in der Qualifizierer aufgelistet werden, ist für eine bestimmte Enumeration garantiert invariante.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="d4d4e-127">Die Flags, die als `lEnumFlags` Argument übermittelt werden können, werden in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

|<span data-ttu-id="d4d4e-128">Konstante</span><span class="sxs-lookup"><span data-stu-id="d4d4e-128">Constant</span></span>  |<span data-ttu-id="d4d4e-129">Wert</span><span class="sxs-lookup"><span data-stu-id="d4d4e-129">Value</span></span>  |<span data-ttu-id="d4d4e-130">Description</span><span class="sxs-lookup"><span data-stu-id="d4d4e-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="d4d4e-131">0</span><span class="sxs-lookup"><span data-stu-id="d4d4e-131">0</span></span> | <span data-ttu-id="d4d4e-132">Gibt die Namen aller Qualifizierer zurück.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="d4d4e-133">0x10</span><span class="sxs-lookup"><span data-stu-id="d4d4e-133">0x10</span></span> | <span data-ttu-id="d4d4e-134">Gibt nur die Namen der Qualifizierer zurück, die speziell für die aktuelle Eigenschaft oder das aktuelle Objekt</span><span class="sxs-lookup"><span data-stu-id="d4d4e-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="d4d4e-135">Für eine Eigenschaft: Gibt nur die Qualifizierer zurück, die für die Eigenschaft spezifisch sind (einschließlich außer Kraft setzungen), und nicht die Qualifizierer, die aus der Klassendefinition</span><span class="sxs-lookup"><span data-stu-id="d4d4e-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="d4d4e-136">Für eine-Instanz: Gibt nur instanzspezifische Qualifizierernamen zurück.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="d4d4e-137">Für eine Klasse: Gibt nur Qualifizierer zurück, die für die abgeleitete Klasse spezifisch sind</span><span class="sxs-lookup"><span data-stu-id="d4d4e-137">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="d4d4e-138">0x20</span><span class="sxs-lookup"><span data-stu-id="d4d4e-138">0x20</span></span> | <span data-ttu-id="d4d4e-139">Gibt nur die Namen der Qualifizierer zurück, die von einem anderen-Objekt</span><span class="sxs-lookup"><span data-stu-id="d4d4e-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="d4d4e-140">Für eine Eigenschaft: Gibt nur die Qualifizierer zurück, die von der Klassendefinition an diese Eigenschaft weitergegeben werden, nicht die der Eigenschaft selbst.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="d4d4e-141">Für eine-Instanz: Gibt nur die Qualifizierer zurück, die aus der Klassendefinition verteilt werden</span><span class="sxs-lookup"><span data-stu-id="d4d4e-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="d4d4e-142">Für eine Klasse: Gibt nur die von den übergeordneten Klassen geerbten Qualifizierernamen zurück.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="d4d4e-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d4d4e-143">Requirements</span></span>

<span data-ttu-id="d4d4e-144">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4d4e-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="d4d4e-145">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d4d4e-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="d4d4e-146">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d4d4e-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d4d4e-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4d4e-147">See also</span></span>

- [<span data-ttu-id="d4d4e-148">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="d4d4e-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
