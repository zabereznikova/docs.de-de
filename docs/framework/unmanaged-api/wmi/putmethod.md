---
title: Putmethod-Funktion (Referenz zur nicht verwalteten API)
description: Die Putmethod-Funktion erstellt eine-Methode.
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
ms.openlocfilehash: a2b41cbbade9da5c2095309b9039b8ce2758f6f3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798362"
---
# <a name="putmethod-function"></a><span data-ttu-id="561d3-103">Putmethod-Funktion</span><span class="sxs-lookup"><span data-stu-id="561d3-103">PutMethod function</span></span>
<span data-ttu-id="561d3-104">Erstellt eine Methode.</span><span class="sxs-lookup"><span data-stu-id="561d3-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="561d3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="561d3-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="561d3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="561d3-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="561d3-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="561d3-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="561d3-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="561d3-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="561d3-109">in Der Name der zu erstellenden Methode.</span><span class="sxs-lookup"><span data-stu-id="561d3-109">[in] The name of the method to create.</span></span> 

`lFlags`  
<span data-ttu-id="561d3-110">[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="561d3-110">[in] Reserved.</span></span> <span data-ttu-id="561d3-111">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="561d3-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="561d3-112">in Ein Zeiger auf eine Kopie der [__Parameters-System Klasse](/windows/desktop/WmiSdk/--parameters) , die die `in` Parameter für die Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="561d3-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="561d3-113">Dieser Parameter wird ignoriert, wenn auf `null`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="561d3-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="561d3-114">in  Ein Zeiger auf eine Kopie der [__Parameters-System Klasse](/windows/desktop/WmiSdk/--parameters) , die die `out` Parameter für die Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="561d3-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="561d3-115">Dieser Parameter wird ignoriert, wenn auf `null`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="561d3-115">This parameter is ignored if set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="561d3-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="561d3-116">Return value</span></span>

<span data-ttu-id="561d3-117">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="561d3-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="561d3-118">Konstante</span><span class="sxs-lookup"><span data-stu-id="561d3-118">Constant</span></span>  |<span data-ttu-id="561d3-119">Wert</span><span class="sxs-lookup"><span data-stu-id="561d3-119">Value</span></span>  |<span data-ttu-id="561d3-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="561d3-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="561d3-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="561d3-121">0x80041008</span></span> | <span data-ttu-id="561d3-122">Mindestens ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="561d3-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="561d3-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="561d3-123">0x80041043</span></span> | <span data-ttu-id="561d3-124">Der `[in, out]` in den *pinsignature* -und *poutsignature* -Objekten angegebene Methoden Parameter verfügt über unterschiedliche Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="561d3-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="561d3-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="561d3-125">0x80041036</span></span> | <span data-ttu-id="561d3-126">Bei einem Methoden Parameter fehlt die Spezifikation des **ID** -Qualifizierers.</span><span class="sxs-lookup"><span data-stu-id="561d3-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="561d3-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="561d3-127">0x80041038</span></span> | <span data-ttu-id="561d3-128">Die ID-Reihe, die den Methoden Parametern zugewiesen ist, ist nicht aufeinander folgt oder beginnt nicht bei 0.</span><span class="sxs-lookup"><span data-stu-id="561d3-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="561d3-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="561d3-129">0x80041039</span></span> | <span data-ttu-id="561d3-130">Der Rückgabewert einer Methode hat einen **ID** -Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="561d3-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="561d3-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="561d3-131">0x80041034</span></span> | <span data-ttu-id="561d3-132">Es wurde versucht, einen vorhandenen Methodennamen aus einer übergeordneten Klasse wiederzuverwenden, und die Signaturen stimmen nicht ab.</span><span class="sxs-lookup"><span data-stu-id="561d3-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="561d3-133">0</span><span class="sxs-lookup"><span data-stu-id="561d3-133">0</span></span> | <span data-ttu-id="561d3-134">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="561d3-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="561d3-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="561d3-135">Remarks</span></span>

<span data-ttu-id="561d3-136">Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject::P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) -Methode.</span><span class="sxs-lookup"><span data-stu-id="561d3-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="561d3-137">Dieser Methoden Aufrufwert wird nur `ptr` unterstützt, wenn eine CIM-Klassendefinition ist.</span><span class="sxs-lookup"><span data-stu-id="561d3-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="561d3-138">Die Methoden Bearbeitung ist nicht in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Zeigern verfügbar, die auf CIM-Instanzen verweisen.</span><span class="sxs-lookup"><span data-stu-id="561d3-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="561d3-139">Benutzer können keine Methoden erstellen, deren Namen mit einem Unterstrich beginnen oder enden.</span><span class="sxs-lookup"><span data-stu-id="561d3-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="561d3-140">Dies ist für System Klassen und-Eigenschaften reserviert.</span><span class="sxs-lookup"><span data-stu-id="561d3-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="561d3-141">Für eine-Methode werden `in` die `out` Parameter und als Eigenschaften in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Objekten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="561d3-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="561d3-142">Ein `[in/out]` -Parameter kann definiert werden, indem die gleiche-Eigenschaft zu beiden-Objekten hinzu `pInSignature` gefügt `pOutSignature` wird, auf die die-und-Parameter zeigen</span><span class="sxs-lookup"><span data-stu-id="561d3-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="561d3-143">In diesem Fall haben die Eigenschaften denselben **ID** -qualifiziererwert.</span><span class="sxs-lookup"><span data-stu-id="561d3-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="561d3-144">Jede Eigenschaft in einem anderen [__Parameters](/windows/desktop/WmiSdk/--parameters) -Klassenobjekt `ReturnValue` als muss über einen **ID** -Qualifizierer verfügen, einem NULL basierten numerischen Wert, der die Reihenfolge angibt, in der die Parameter angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="561d3-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="561d3-145">Zwei Parameter können nicht denselben **ID** -Wert haben, und es kann kein **ID** -Wert übersprungen werden.</span><span class="sxs-lookup"><span data-stu-id="561d3-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="561d3-146">Wenn eine Bedingung auftritt, gibt `PutMethod` die Funktion `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`zurück.</span><span class="sxs-lookup"><span data-stu-id="561d3-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="561d3-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="561d3-147">Example</span></span>

<span data-ttu-id="561d3-148">Ein Beispiel finden Sie unter der [IWbemClassObject::P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) -Methode.</span><span class="sxs-lookup"><span data-stu-id="561d3-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="561d3-149">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="561d3-149">Requirements</span></span>  
 <span data-ttu-id="561d3-150">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="561d3-150">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="561d3-151">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="561d3-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="561d3-152">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="561d3-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="561d3-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="561d3-153">See also</span></span>

- [<span data-ttu-id="561d3-154">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="561d3-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
