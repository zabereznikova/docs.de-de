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
ms.openlocfilehash: 2d20701237501834c611c4e498c39597cf275176
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2018
ms.locfileid: "43001462"
---
# <a name="qualifiersetbeginenumeration-function"></a><span data-ttu-id="4b985-103">QualifierSet_BeginEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="4b985-103">QualifierSet_BeginEnumeration function</span></span>
<span data-ttu-id="4b985-104">Setzt einen Enumerator der Qualifizierer eines Objekts an den Anfang der Enumeration zurück.</span><span class="sxs-lookup"><span data-stu-id="4b985-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="4b985-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b985-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="4b985-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4b985-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="4b985-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="4b985-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="4b985-108">[in] Ein Zeiger auf ein [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) Instanz.</span><span class="sxs-lookup"><span data-stu-id="4b985-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`   
<span data-ttu-id="4b985-109">[in] Eine bitweise Kombination der Flags oder Werte, die in beschriebenen der ["Hinweise"](#remarks) Abschnitt, der angibt, die Qualifizierer in der Enumeration einschließen.</span><span class="sxs-lookup"><span data-stu-id="4b985-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="4b985-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4b985-110">Return value</span></span>

<span data-ttu-id="4b985-111">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="4b985-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4b985-112">Konstante</span><span class="sxs-lookup"><span data-stu-id="4b985-112">Constant</span></span>  |<span data-ttu-id="4b985-113">Wert</span><span class="sxs-lookup"><span data-stu-id="4b985-113">Value</span></span>  |<span data-ttu-id="4b985-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b985-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4b985-115">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="4b985-115">0x80041008</span></span> | <span data-ttu-id="4b985-116">Die `lFlags` -Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="4b985-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="4b985-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="4b985-117">0x8004101d</span></span> | <span data-ttu-id="4b985-118">Einen zweiten Aufruf von `QualifierSet_BeginEnumeration` wurde ohne einen zwischenzeitlichen Aufruf versucht [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="4b985-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="4b985-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="4b985-119">0x80041006</span></span> | <span data-ttu-id="4b985-120">Es ist nicht genügend Arbeitsspeicher zur Verfügung, um eine neue Enumeration beginnen.</span><span class="sxs-lookup"><span data-stu-id="4b985-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4b985-121">0</span><span class="sxs-lookup"><span data-stu-id="4b985-121">0</span></span> | <span data-ttu-id="4b985-122">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="4b985-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="4b985-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4b985-123">Remarks</span></span>

<span data-ttu-id="4b985-124">Diese Funktion umschließt einen Aufruf der [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) Methode.</span><span class="sxs-lookup"><span data-stu-id="4b985-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) method.</span></span>

<span data-ttu-id="4b985-125">Zum Aufzählen aller die Qualifizierer für ein Objekt muss vor dem ersten Aufruf dieser Methode aufgerufen werden [QualifierSet_Next](qualifierset-next.md).</span><span class="sxs-lookup"><span data-stu-id="4b985-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="4b985-126">Die Reihenfolge, in der aufgelisteten Qualifizierer, ist garantiert Invarianten für eine angegebene Enumeration.</span><span class="sxs-lookup"><span data-stu-id="4b985-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="4b985-127">Die Flags, die als übergeben werden können die `lEnumFlags` Argument definiert werden, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="4b985-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>   

|<span data-ttu-id="4b985-128">Konstante</span><span class="sxs-lookup"><span data-stu-id="4b985-128">Constant</span></span>  |<span data-ttu-id="4b985-129">Wert</span><span class="sxs-lookup"><span data-stu-id="4b985-129">Value</span></span>  |<span data-ttu-id="4b985-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b985-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="4b985-131">0</span><span class="sxs-lookup"><span data-stu-id="4b985-131">0</span></span> | <span data-ttu-id="4b985-132">Die Namen aller Qualifizierer zurück</span><span class="sxs-lookup"><span data-stu-id="4b985-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="4b985-133">0x10</span><span class="sxs-lookup"><span data-stu-id="4b985-133">0x10</span></span> | <span data-ttu-id="4b985-134">Nur die Namen der Qualifizierer an die current-Eigenschaft oder das Objekt bestimmte zurück.</span><span class="sxs-lookup"><span data-stu-id="4b985-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="4b985-135">Für eine Eigenschaft: nur der Qualifizierer der Eigenschaft (einschließlich Außerkraftsetzungen) bestimmte zurückgeben und nicht diese Qualifizierer aus der Klassendefinition weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="4b985-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="4b985-136">Für eine Instanz: nur instanzspezifischen Qualifizierer Namen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="4b985-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="4b985-137">Für eine Klasse: nur die Qualifizierer, die abgeleitete Klasse Beiong bestimmte zurück.</span><span class="sxs-lookup"><span data-stu-id="4b985-137">For a class: Return only qualifiers specific to the class beiong derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="4b985-138">0x20</span><span class="sxs-lookup"><span data-stu-id="4b985-138">0x20</span></span> | <span data-ttu-id="4b985-139">Rückgabe, nur die Namen der Qualifizierer weitergegeben aus einem anderen Objekt.</span><span class="sxs-lookup"><span data-stu-id="4b985-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="4b985-140">Für eine Eigenschaft: Rückgabe, nur die Qualifizierer weitergegeben für diese Eigenschaft aus der Klassendefinition und nicht die von der Eigenschaft selbst.</span><span class="sxs-lookup"><span data-stu-id="4b985-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="4b985-141">Für eine Instanz: zurück, die nur diese Qualifizierer weitergegeben werden, aus der Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="4b985-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="4b985-142">Für eine Klasse: zurück, die nur für die Qualifizierer Namen, die von der übergeordneten Klassen geerbt.</span><span class="sxs-lookup"><span data-stu-id="4b985-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="4b985-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4b985-143">Requirements</span></span>  
 <span data-ttu-id="4b985-144">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b985-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b985-145">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4b985-145">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4b985-146">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4b985-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b985-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b985-147">See also</span></span>  
[<span data-ttu-id="4b985-148">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="4b985-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
