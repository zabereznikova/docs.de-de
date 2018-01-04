---
title: QualifierSet_Put-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion QualifierSet_Put schreibt benannte Qualifizierer und seinen Wert.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_Put
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_Put
helpviewer_keywords: QualifierSet_Put function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1bf5c6dbf0f707942d58f4d7cf155636f0532724
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetput-function"></a><span data-ttu-id="cd6aa-103">QualifierSet_Put-Funktion</span><span class="sxs-lookup"><span data-stu-id="cd6aa-103">QualifierSet_Put function</span></span>
<span data-ttu-id="cd6aa-104">Schreibt die benannte Qualifizierer und Wert.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-104">Writes the named qualifier and value.</span></span> <span data-ttu-id="cd6aa-105">Der neue Qualifizierer wird den vorherigen Wert mit dem gleichen Namen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-105">The new qualifier overwrites the previous value of the same name.</span></span> <span data-ttu-id="cd6aa-106">Wenn Sie der Qualifizierer nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-106">If the qualifier does not exist, it is created.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="cd6aa-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd6aa-107">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Put (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
); 
```  

## <a name="parameters"></a><span data-ttu-id="cd6aa-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="cd6aa-108">Parameters</span></span>

`vFunc`   
<span data-ttu-id="cd6aa-109">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-109">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="cd6aa-110">[in] Ein Zeiger auf ein [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-110">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`wszName`   
<span data-ttu-id="cd6aa-111">[in] Der Name des Qualifizierers der geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-111">[in] The name of the qualifier to write.</span></span>

<span data-ttu-id="cd6aa-112">`pVal`[in] Ein Zeiger auf eine gültige `VARIANT` , enthält den Qualifizierer, der zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-112">`pVal` [in] A pointer to a valid `VARIANT` that contains the qualifier to write.</span></span> <span data-ttu-id="cd6aa-113">Dieser Parameter darf nicht sein `null`.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-113">This parameter cannot be `null`.</span></span>

<span data-ttu-id="cd6aa-114">`lFlavor`[in] Einer der folgenden Konstanten, die die gewünschten Qualifizierern für diese Qualifizierer definiert.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-114">`lFlavor` [in] One of the following constants that defines the desired qualifier flavors for this qualifier.</span></span> <span data-ttu-id="cd6aa-115">Der Standardwert ist `WBEM_FLAVOR_OVERRIDABLE` (0).</span><span class="sxs-lookup"><span data-stu-id="cd6aa-115">The default value is `WBEM_FLAVOR_OVERRIDABLE` (0).</span></span>

|<span data-ttu-id="cd6aa-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="cd6aa-116">Constant</span></span>  |<span data-ttu-id="cd6aa-117">Wert</span><span class="sxs-lookup"><span data-stu-id="cd6aa-117">Value</span></span>  |<span data-ttu-id="cd6aa-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd6aa-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | <span data-ttu-id="cd6aa-119">0</span><span class="sxs-lookup"><span data-stu-id="cd6aa-119">0</span></span> | <span data-ttu-id="cd6aa-120">Der Qualifizierer kann in einer abgeleiteten Klasse oder Instanz überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-120">The qualifier can be overridden in a derived class or instance.</span></span> <span data-ttu-id="cd6aa-121">**Dies ist der Standardwert.**</span><span class="sxs-lookup"><span data-stu-id="cd6aa-121">**This is the default value.**</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | <span data-ttu-id="cd6aa-122">1</span><span class="sxs-lookup"><span data-stu-id="cd6aa-122">1</span></span> | <span data-ttu-id="cd6aa-123">Der Qualifizierer wird an Instanzen weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-123">The qualifier is propagated to instances.</span></span> |
| `WBEM_FLAVOR_GLAG_PROPAGATE_TO_DERIVED_CLASS` | <span data-ttu-id="cd6aa-124">2</span><span class="sxs-lookup"><span data-stu-id="cd6aa-124">2</span></span> | <span data-ttu-id="cd6aa-125">Der Qualifizierer wird auf die abgeleitete Klassen weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-125">The qualifier is propagated to derived classes.</span></span> |
| <span data-ttu-id="cd6aa-126">"WBEM_FLAVOR_NOT_OVERRIDABLE</span><span class="sxs-lookup"><span data-stu-id="cd6aa-126">\`WBEM_FLAVOR_NOT_OVERRIDABLE</span></span> | <span data-ttu-id="cd6aa-127">0 x 10</span><span class="sxs-lookup"><span data-stu-id="cd6aa-127">0x10</span></span> | <span data-ttu-id="cd6aa-128">Der Qualifizierer kann in einer abgeleiteten Klasse oder Instanz nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-128">The qualifier cannot be overridden in a derived class or instance.</span></span> |
| <span data-ttu-id="cd6aa-129">"WBEM_FLAVOR_AMENDED</span><span class="sxs-lookup"><span data-stu-id="cd6aa-129">\`WBEM_FLAVOR_AMENDED</span></span> | <span data-ttu-id="cd6aa-130">0 x 80</span><span class="sxs-lookup"><span data-stu-id="cd6aa-130">0x80</span></span> | <span data-ttu-id="cd6aa-131">Der Qualifizierer ist lokalisiert.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-131">The qualifier is localized.</span></span> |

## <a name="return-value"></a><span data-ttu-id="cd6aa-132">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cd6aa-132">Return value</span></span>

<span data-ttu-id="cd6aa-133">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="cd6aa-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="cd6aa-134">Konstante</span><span class="sxs-lookup"><span data-stu-id="cd6aa-134">Constant</span></span>  |<span data-ttu-id="cd6aa-135">Wert</span><span class="sxs-lookup"><span data-stu-id="cd6aa-135">Value</span></span>  |<span data-ttu-id="cd6aa-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd6aa-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | <span data-ttu-id="cd6aa-137">0x8004101f</span><span class="sxs-lookup"><span data-stu-id="cd6aa-137">0x8004101f</span></span> | <span data-ttu-id="cd6aa-138">Es wurde unzulässigerweise versucht, an die **Schlüssel** Qualifizierer für eine Eigenschaft, die kein Schlüssel sein kann.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-138">There was an illegal attempt to specify the **Key** qualifier on a property that cannot be a key.</span></span> <span data-ttu-id="cd6aa-139">Die Schlüssel werden angegeben Om c; Ass-Definition für ein Objekt und kann nicht auf eine instanzweise geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-139">The keys are specified om tje c;ass definition for an object and cannot be altered on a per-instance basis.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="cd6aa-140">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="cd6aa-140">0x80041008</span></span> | <span data-ttu-id="cd6aa-141">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-141">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | <span data-ttu-id="cd6aa-142">0x80041029</span><span class="sxs-lookup"><span data-stu-id="cd6aa-142">0x80041029</span></span> | <span data-ttu-id="cd6aa-143">Die `pVal` Parameter ist nicht von einem gültigen Qualifizierertyp.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-143">The `pVal` parameter is not of a legal qualifier type.</span></span> |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | <span data-ttu-id="cd6aa-144">0x8004101a</span><span class="sxs-lookup"><span data-stu-id="cd6aa-144">0x8004101a</span></span> | <span data-ttu-id="cd6aa-145">Es ist nicht möglich, rufen Sie die `QualifierSet_Put` -Methode für den Qualifizierer überschreibt, da das besitzende Objekt nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-145">It is not possible to call the `QualifierSet_Put` method on the qualifier because the owning object does not permit overrides.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="cd6aa-146">0</span><span class="sxs-lookup"><span data-stu-id="cd6aa-146">0</span></span> | <span data-ttu-id="cd6aa-147">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-147">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="cd6aa-148">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cd6aa-148">Remarks</span></span>

<span data-ttu-id="cd6aa-149">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemQualifierSet::Put](https://msdn.microsoft.com/library/aa391871(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="cd6aa-149">This function wraps a call to the [IWbemQualifierSet::Put](https://msdn.microsoft.com/library/aa391871(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="cd6aa-150">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd6aa-150">Requirements</span></span>  
 <span data-ttu-id="cd6aa-151">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd6aa-151">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd6aa-152">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="cd6aa-152">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="cd6aa-153">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cd6aa-153">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd6aa-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd6aa-154">See also</span></span>  
[<span data-ttu-id="cd6aa-155">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="cd6aa-155">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
