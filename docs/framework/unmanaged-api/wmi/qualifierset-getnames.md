---
title: QualifierSet_GetNames-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_GetNames-Funktion ruft die Namen der Qualifizierer aus einem Objekt oder die Eigenschaft ab.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_GetNames
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_GetNames
helpviewer_keywords: QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b87518bdc1f6ac19eb48991538be5904fdb63f1f
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetgetnames-function"></a><span data-ttu-id="044a2-103">QualifierSet_GetNames-Funktion</span><span class="sxs-lookup"><span data-stu-id="044a2-103">QualifierSet_GetNames function</span></span>
<span data-ttu-id="044a2-104">Ruft die Namen der Qualifizierer alle oder bestimmte Qualifizierer angegeben, die aus dem aktuellen Objekt oder eine Eigenschaft verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="044a2-104">Retrieves the names of all the qualifiers or of certain qualifiers that are available from the current object or property.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="044a2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="044a2-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
); 
```  

## <a name="parameters"></a><span data-ttu-id="044a2-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="044a2-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="044a2-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="044a2-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="044a2-108">[in] Ein Zeiger auf ein [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="044a2-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`lFlags`   
<span data-ttu-id="044a2-109">[in] Einer der folgenden Flags oder Werte, der angibt, welche Namen in der Enumeration einschließen.</span><span class="sxs-lookup"><span data-stu-id="044a2-109">[in] One of the following flags or values that specifies which names to include in the enumeration.</span></span>

|<span data-ttu-id="044a2-110">Konstante</span><span class="sxs-lookup"><span data-stu-id="044a2-110">Constant</span></span>  |<span data-ttu-id="044a2-111">Wert</span><span class="sxs-lookup"><span data-stu-id="044a2-111">Value</span></span>  |<span data-ttu-id="044a2-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="044a2-112">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="044a2-113">0</span><span class="sxs-lookup"><span data-stu-id="044a2-113">0</span></span> | <span data-ttu-id="044a2-114">Geben Sie die Namen aller Qualifizierer zurück.</span><span class="sxs-lookup"><span data-stu-id="044a2-114">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="044a2-115">0 x 10</span><span class="sxs-lookup"><span data-stu-id="044a2-115">0x10</span></span> | <span data-ttu-id="044a2-116">Nur die Namen der Qualifizierer, die current-Eigenschaft oder das Objekt bestimmte zurück.</span><span class="sxs-lookup"><span data-stu-id="044a2-116">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="044a2-117">Für eine Eigenschaft: nur die Qualifizierer in dieser Eigenschaft (einschließlich Außerkraftsetzungen) bestimmte zurück, und nicht diese Qualifizierer aus der Klassendefinition weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="044a2-117">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="044a2-118">Für eine Instanz: nur instanzspezifischen Qualifizierer Namen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="044a2-118">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="044a2-119">Für eine Klasse: nur Qualifizierer, die abgeleitete Klasse Beiong bestimmte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="044a2-119">For a class: Return only qualifiers specific to the class beiong derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="044a2-120">0 x 20</span><span class="sxs-lookup"><span data-stu-id="044a2-120">0x20</span></span> | <span data-ttu-id="044a2-121">Rückgabe, nur die Namen der Qualifizierer weitergegeben aus einem anderen Objekt.</span><span class="sxs-lookup"><span data-stu-id="044a2-121">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="044a2-122">Für eine Eigenschaft: Rückgabe nur der Qualifizierer weitergegeben auf diese Eigenschaft aus der Klassendefinition, und nicht die von der Eigenschaft selbst.</span><span class="sxs-lookup"><span data-stu-id="044a2-122">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="044a2-123">Für eine Instanz: zurück, die nur diese Qualifizierer weitergegeben werden, aus der Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="044a2-123">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="044a2-124">Für eine Klasse: zurück, die nur diese Qualifizierer Namen, die von der übergeordneten Klassen geerbt.</span><span class="sxs-lookup"><span data-stu-id="044a2-124">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

<span data-ttu-id="044a2-125">`pstrNames`[out] Ein neues `SAFEARRAY` , die den angeforderten Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="044a2-125">`pstrNames` [out] A new `SAFEARRAY` that contains the requested names.</span></span> <span data-ttu-id="044a2-126">Das Array kann 0 Elemente verfügen.</span><span class="sxs-lookup"><span data-stu-id="044a2-126">The array can have 0 elements.</span></span> <span data-ttu-id="044a2-127">Wenn ein Fehler auftritt, eine neue `SAFEARRAY` wird nicht zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="044a2-127">If an error occurs, a new `SAFEARRAY` is not returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="044a2-128">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="044a2-128">Return value</span></span>

<span data-ttu-id="044a2-129">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="044a2-129">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="044a2-130">Konstante</span><span class="sxs-lookup"><span data-stu-id="044a2-130">Constant</span></span>  |<span data-ttu-id="044a2-131">Wert</span><span class="sxs-lookup"><span data-stu-id="044a2-131">Value</span></span>  |<span data-ttu-id="044a2-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="044a2-132">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="044a2-133">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="044a2-133">0x80041008</span></span> | <span data-ttu-id="044a2-134">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="044a2-134">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="044a2-135">0x80041006</span><span class="sxs-lookup"><span data-stu-id="044a2-135">0x80041006</span></span> | <span data-ttu-id="044a2-136">Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="044a2-136">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="044a2-137">0</span><span class="sxs-lookup"><span data-stu-id="044a2-137">0</span></span> | <span data-ttu-id="044a2-138">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="044a2-138">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="044a2-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="044a2-139">Remarks</span></span>

<span data-ttu-id="044a2-140">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemQualifierSet::GetNames](https://msdn.microsoft.com/library/aa391868(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="044a2-140">This function wraps a call to the [IWbemQualifierSet::GetNames](https://msdn.microsoft.com/library/aa391868(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="044a2-141">Nachdem Sie die Qualifizierer Namen abgerufen haben, können Sie jede Qualifizierer namentlich zugreifen, durch Aufrufen der [QualifierSet_Get](qualifierset-get.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="044a2-141">Once you've retrieved the qualifier names, you can access each qualifier by name by calling the [QualifierSet_Get](qualifierset-get.md) function.</span></span> 

<span data-ttu-id="044a2-142">Es ist kein Fehler für ein angegebenes Objekt, daher keine NULL-Qualifizierer, die Anzahl der Zeichenfolgen in `pstrNames` bei der Rückgabe "0" sein, auch wenn die Funktion gibt `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="044a2-142">It is not an error for a given object to have zero qualifiers, so the number of strings in `pstrNames` on return can be 0, even though the function returns `WBEM_S_NO_ERROR`.</span></span>

## <a name="requirements"></a><span data-ttu-id="044a2-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="044a2-143">Requirements</span></span>  
 <span data-ttu-id="044a2-144">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="044a2-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="044a2-145">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="044a2-145">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="044a2-146">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="044a2-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="044a2-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="044a2-147">See also</span></span>  
[<span data-ttu-id="044a2-148">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="044a2-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
