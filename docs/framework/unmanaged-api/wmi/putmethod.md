---
title: PutMethod-Funktion (Referenz zur nicht verwalteten API)
description: Die PutMethod-Funktion erstellt eine Methode an.
ms.date: 11/06/2017
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99bc65b0181a7c0ab7877273b3747ece91544f99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049257"
---
# <a name="putmethod-function"></a><span data-ttu-id="8bd2d-103">PutMethod-Funktion</span><span class="sxs-lookup"><span data-stu-id="8bd2d-103">PutMethod function</span></span>
<span data-ttu-id="8bd2d-104">Erstellt eine Methode.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="8bd2d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8bd2d-105">Syntax</span></span>  
  
```  
HRESULT PutMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*  ptr, 
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
); 
```  

## <a name="parameters"></a><span data-ttu-id="8bd2d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8bd2d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="8bd2d-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="8bd2d-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="8bd2d-109">[in] Der Name der Methode zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-109">[in] The name of the method to create.</span></span> 

`lFlags`  
<span data-ttu-id="8bd2d-110">[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-110">[in] Reserved.</span></span> <span data-ttu-id="8bd2d-111">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="8bd2d-112">[in] Ein Zeiger auf eine Kopie der [__Parameters Systemklasse](/windows/desktop/WmiSdk/--parameters) , enthält die `in` Parameter für die Methode.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="8bd2d-113">Dieser Parameter wird ignoriert, wenn auf festgelegt `null`.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="8bd2d-114">[in]  Ein Zeiger auf eine Kopie der [__Parameters Systemklasse](/windows/desktop/WmiSdk/--parameters) , enthält die `out` Parameter für die Methode.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="8bd2d-115">Dieser Parameter wird ignoriert, wenn auf festgelegt `null`.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-115">This parameter is ignored if set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="8bd2d-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8bd2d-116">Return value</span></span>

<span data-ttu-id="8bd2d-117">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="8bd2d-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8bd2d-118">Konstante</span><span class="sxs-lookup"><span data-stu-id="8bd2d-118">Constant</span></span>  |<span data-ttu-id="8bd2d-119">Wert</span><span class="sxs-lookup"><span data-stu-id="8bd2d-119">Value</span></span>  |<span data-ttu-id="8bd2d-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8bd2d-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8bd2d-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8bd2d-121">0x80041008</span></span> | <span data-ttu-id="8bd2d-122">Ein oder mehrere Parameter sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="8bd2d-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="8bd2d-123">0x80041043</span></span> | <span data-ttu-id="8bd2d-124">Die `[in, out]` Methodenparameter angegeben wird, sowohl die *pInSignature* und *pOutSignature* Objekte verfügen über unterschiedliche Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="8bd2d-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="8bd2d-125">0x80041036</span></span> | <span data-ttu-id="8bd2d-126">Parameter der Methode fehlt die Angabe der **ID** Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="8bd2d-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="8bd2d-127">0x80041038</span></span> | <span data-ttu-id="8bd2d-128">Die ID-Reihe, die die Parameter der Methode zugewiesen ist, nicht aufeinander folgende oder beginnt nicht bei 0.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="8bd2d-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="8bd2d-129">0x80041039</span></span> | <span data-ttu-id="8bd2d-130">Der Rückgabewert für eine Methode hat eine **ID** Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="8bd2d-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="8bd2d-131">0x80041034</span></span> | <span data-ttu-id="8bd2d-132">Es wurde versucht, einen vorhandenen Methodennamen einer übergeordneten Klasse wiederverwendet, und die Signaturen stimmten nicht überein.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="8bd2d-133">0</span><span class="sxs-lookup"><span data-stu-id="8bd2d-133">0</span></span> | <span data-ttu-id="8bd2d-134">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="8bd2d-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8bd2d-135">Remarks</span></span>

<span data-ttu-id="8bd2d-136">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) Methode.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="8bd2d-137">Dieser Methodenaufruf wird nur unterstützt, wenn `ptr` ist die Definition einer CIM-Klasse.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="8bd2d-138">Bearbeitung der Methode ist nicht verfügbar [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Zeigern, die auf das CIM-Instanzen verweisen.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="8bd2d-139">Benutzer können keine Methoden mit Namen erstellen, die mit einem Unterstrich beginnen oder enden.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="8bd2d-140">Dies ist für die Systemklassen und Eigenschaften reserviert.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="8bd2d-141">Für eine Methode die `in` und `out` Parameter werden als Eigenschaften in beschrieben [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Objekte.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="8bd2d-142">Ein `[in/out]` Parameter definiert werden, indem Sie die gleiche Eigenschaft hinzufügen, auf beide Objekte verweist die `pInSignature` und `pOutSignature` Parameter.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="8bd2d-143">In diesem Fall die Eigenschaften verwenden dieselbe **ID** Wert des Qualifizierers.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="8bd2d-144">Jede Eigenschaft im eine [__Parameters](/windows/desktop/WmiSdk/--parameters) Objekt außer Klasse `ReturnValue` benötigen eine **ID** Qualifizierer, eine nullbasierte numerischer Wert, der die Reihenfolge angibt, in der die Parameter angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="8bd2d-145">Keine zwei Parameter haben den gleichen **ID** Wert und keine **ID** Wert übersprungen werden kann.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="8bd2d-146">Wenn eine der Bedingungen auftritt, die `PutMethod` -Funktion zurückgegeben `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="8bd2d-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8bd2d-147">Example</span></span>

<span data-ttu-id="8bd2d-148">Ein Beispiel finden Sie unter den [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) Methode.</span><span class="sxs-lookup"><span data-stu-id="8bd2d-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="8bd2d-149">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8bd2d-149">Requirements</span></span>  
 <span data-ttu-id="8bd2d-150">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bd2d-150">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bd2d-151">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8bd2d-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8bd2d-152">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8bd2d-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd2d-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bd2d-153">See also</span></span>

- [<span data-ttu-id="8bd2d-154">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="8bd2d-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
