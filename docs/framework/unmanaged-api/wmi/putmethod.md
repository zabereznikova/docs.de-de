---
title: PutMethod-Funktion (Nicht verwaltete API-Referenz)
description: Die PutMethod-Funktion erstellt eine Methode.
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
ms.openlocfilehash: 93347b7290211b5d62829604678261fdf4da1ec3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174913"
---
# <a name="putmethod-function"></a><span data-ttu-id="9452f-103">PutMethod-Funktion</span><span class="sxs-lookup"><span data-stu-id="9452f-103">PutMethod function</span></span>
<span data-ttu-id="9452f-104">Erstellt eine Methode.</span><span class="sxs-lookup"><span data-stu-id="9452f-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="9452f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9452f-105">Syntax</span></span>  
  
```cpp  
HRESULT PutMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*  ptr,
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
);
```  

## <a name="parameters"></a><span data-ttu-id="9452f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9452f-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="9452f-107">[in] Dieser Parameter ist nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="9452f-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="9452f-108">[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="9452f-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="9452f-109">[in] Der Name der zu erstellenden Methode.</span><span class="sxs-lookup"><span data-stu-id="9452f-109">[in] The name of the method to create.</span></span>

`lFlags`  
<span data-ttu-id="9452f-110">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="9452f-110">[in] Reserved.</span></span> <span data-ttu-id="9452f-111">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="9452f-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="9452f-112">[in] Ein Zeiger auf eine Kopie der __Parameters `in` [Systemklasse,](/windows/desktop/WmiSdk/--parameters) die die Parameter für die Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="9452f-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="9452f-113">Dieser Parameter wird ignoriert, wenn er auf `null`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9452f-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="9452f-114">[in]  Ein Zeiger auf eine Kopie der __Parameters `out` [Systemklasse,](/windows/desktop/WmiSdk/--parameters) die die Parameter für die Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="9452f-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="9452f-115">Dieser Parameter wird ignoriert, wenn er auf `null`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9452f-115">This parameter is ignored if set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="9452f-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9452f-116">Return value</span></span>

<span data-ttu-id="9452f-117">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="9452f-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9452f-118">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="9452f-118">Constant</span></span>  |<span data-ttu-id="9452f-119">value</span><span class="sxs-lookup"><span data-stu-id="9452f-119">Value</span></span>  |<span data-ttu-id="9452f-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9452f-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="9452f-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="9452f-121">0x80041008</span></span> | <span data-ttu-id="9452f-122">Mindestens ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="9452f-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="9452f-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="9452f-123">0x80041043</span></span> | <span data-ttu-id="9452f-124">Der `[in, out]` in den *pInSignature-* und *pOutSignature-Objekten* angegebene Methodenparameter weist unterschiedliche Qualifizierer auf.</span><span class="sxs-lookup"><span data-stu-id="9452f-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="9452f-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="9452f-125">0x80041036</span></span> | <span data-ttu-id="9452f-126">Ein Methodenparameter fehlt die **ID** Spezifikation des ID-Qualifizierers.</span><span class="sxs-lookup"><span data-stu-id="9452f-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="9452f-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="9452f-127">0x80041038</span></span> | <span data-ttu-id="9452f-128">Die ID-Serie, die den Methodenparametern zugewiesen ist, ist nicht aufeinander folgend oder beginnt nicht bei 0.</span><span class="sxs-lookup"><span data-stu-id="9452f-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="9452f-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="9452f-129">0x80041039</span></span> | <span data-ttu-id="9452f-130">Der Rückgabewert für eine **ID** Methode verfügt über einen ID-Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="9452f-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="9452f-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="9452f-131">0x80041034</span></span> | <span data-ttu-id="9452f-132">Es wurde versucht, einen vorhandenen Methodennamen aus einer übergeordneten Klasse wiederzuverwenden, und die Signaturen stimmen nicht überein.</span><span class="sxs-lookup"><span data-stu-id="9452f-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="9452f-133">0</span><span class="sxs-lookup"><span data-stu-id="9452f-133">0</span></span> | <span data-ttu-id="9452f-134">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="9452f-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="9452f-135">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9452f-135">Remarks</span></span>

<span data-ttu-id="9452f-136">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::PutMethod-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)</span><span class="sxs-lookup"><span data-stu-id="9452f-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="9452f-137">Dieser Methodenaufruf wird `ptr` nur unterstützt, wenn es sich um eine CIM-Klassendefinition handelt.</span><span class="sxs-lookup"><span data-stu-id="9452f-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="9452f-138">Die Methodenmanipulation ist von [IWbemClassObject-Zeigern, die](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) auf CIM-Instanzen verweisen, nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9452f-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="9452f-139">Benutzer können keine Methoden mit Namen erstellen, die mit einem Unterstrich beginnen oder enden.</span><span class="sxs-lookup"><span data-stu-id="9452f-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="9452f-140">Dies ist für Systemklassen und Eigenschaften reserviert.</span><span class="sxs-lookup"><span data-stu-id="9452f-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="9452f-141">Bei einer Methode `in` `out` werden die und parameter als Eigenschaften in [IWbemClassObject-Objekten](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9452f-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="9452f-142">Ein `[in/out]` Parameter kann definiert werden, indem beide Objekte, `pInSignature` `pOutSignature` auf die durch die und Parameter verwiesen wird, dieselbe Eigenschaft hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9452f-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="9452f-143">In diesem Fall haben die **ID** Eigenschaften denselben ID-Qualifiziererwert.</span><span class="sxs-lookup"><span data-stu-id="9452f-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="9452f-144">Jede Eigenschaft [__Parameters](/windows/desktop/WmiSdk/--parameters) in einem __Parameters `ReturnValue` Klassenobjekts außer muss über einen ID-Qualifizierer verfügen, einen nullbasierten numerischen Wert, der die Reihenfolge angibt, in der die Parameter angezeigt werden. **ID**</span><span class="sxs-lookup"><span data-stu-id="9452f-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="9452f-145">Es können keine zwei Parameter denselben **ID-Wert** haben, und kein **ID-Wert** kann übersprungen werden.</span><span class="sxs-lookup"><span data-stu-id="9452f-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="9452f-146">Wenn eine der `PutMethod` beiden `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`Bedingungen auftritt, gibt die Funktion zurück.</span><span class="sxs-lookup"><span data-stu-id="9452f-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="9452f-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9452f-147">Example</span></span>

<span data-ttu-id="9452f-148">Ein Beispiel finden Sie unter die [IWbemClassObject::PutMethod-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)</span><span class="sxs-lookup"><span data-stu-id="9452f-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="9452f-149">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9452f-149">Requirements</span></span>  
 <span data-ttu-id="9452f-150">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9452f-150">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9452f-151">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9452f-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="9452f-152">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9452f-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9452f-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9452f-153">See also</span></span>

- [<span data-ttu-id="9452f-154">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="9452f-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
