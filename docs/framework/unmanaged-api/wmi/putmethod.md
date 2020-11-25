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
ms.openlocfilehash: 8edbb8074573b98c017f98197d370c2ad37db80c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726755"
---
# <a name="putmethod-function"></a><span data-ttu-id="7a194-103">PutMethod-Funktion</span><span class="sxs-lookup"><span data-stu-id="7a194-103">PutMethod function</span></span>

<span data-ttu-id="7a194-104">Erstellt eine Methode.</span><span class="sxs-lookup"><span data-stu-id="7a194-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="7a194-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a194-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="7a194-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="7a194-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="7a194-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7a194-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="7a194-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="7a194-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="7a194-109">in Der Name der zu erstellenden Methode.</span><span class="sxs-lookup"><span data-stu-id="7a194-109">[in] The name of the method to create.</span></span>

`lFlags`  
<span data-ttu-id="7a194-110">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="7a194-110">[in] Reserved.</span></span> <span data-ttu-id="7a194-111">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="7a194-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="7a194-112">in Ein Zeiger auf eine Kopie der [__Parameters System Klasse](/windows/desktop/WmiSdk/--parameters) , die die `in` Parameter für die Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="7a194-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="7a194-113">Dieser Parameter wird ignoriert, wenn auf festgelegt `null` .</span><span class="sxs-lookup"><span data-stu-id="7a194-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="7a194-114">in  Ein Zeiger auf eine Kopie der [__Parameters System Klasse](/windows/desktop/WmiSdk/--parameters) , die die `out` Parameter für die Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="7a194-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="7a194-115">Dieser Parameter wird ignoriert, wenn auf festgelegt `null` .</span><span class="sxs-lookup"><span data-stu-id="7a194-115">This parameter is ignored if set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="7a194-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7a194-116">Return value</span></span>

<span data-ttu-id="7a194-117">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="7a194-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7a194-118">Konstante</span><span class="sxs-lookup"><span data-stu-id="7a194-118">Constant</span></span>  |<span data-ttu-id="7a194-119">Wert</span><span class="sxs-lookup"><span data-stu-id="7a194-119">Value</span></span>  |<span data-ttu-id="7a194-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7a194-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7a194-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7a194-121">0x80041008</span></span> | <span data-ttu-id="7a194-122">Mindestens ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="7a194-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="7a194-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="7a194-123">0x80041043</span></span> | <span data-ttu-id="7a194-124">Der `[in, out]` in den *pinsignature* -und *poutsignature* -Objekten angegebene Methoden Parameter verfügt über unterschiedliche Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="7a194-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="7a194-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="7a194-125">0x80041036</span></span> | <span data-ttu-id="7a194-126">Bei einem Methoden Parameter fehlt die Spezifikation des **ID** -Qualifizierers.</span><span class="sxs-lookup"><span data-stu-id="7a194-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="7a194-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="7a194-127">0x80041038</span></span> | <span data-ttu-id="7a194-128">Die ID-Reihe, die den Methoden Parametern zugewiesen ist, ist nicht aufeinander folgt oder beginnt nicht bei 0.</span><span class="sxs-lookup"><span data-stu-id="7a194-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="7a194-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="7a194-129">0x80041039</span></span> | <span data-ttu-id="7a194-130">Der Rückgabewert einer Methode hat einen **ID** -Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="7a194-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="7a194-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="7a194-131">0x80041034</span></span> | <span data-ttu-id="7a194-132">Es wurde versucht, einen vorhandenen Methodennamen aus einer übergeordneten Klasse wiederzuverwenden, und die Signaturen stimmen nicht ab.</span><span class="sxs-lookup"><span data-stu-id="7a194-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="7a194-133">0</span><span class="sxs-lookup"><span data-stu-id="7a194-133">0</span></span> | <span data-ttu-id="7a194-134">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="7a194-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="7a194-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7a194-135">Remarks</span></span>

<span data-ttu-id="7a194-136">Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject::P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) -Methode.</span><span class="sxs-lookup"><span data-stu-id="7a194-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="7a194-137">Dieser Methoden Aufrufwert wird nur unterstützt, wenn `ptr` eine CIM-Klassendefinition ist.</span><span class="sxs-lookup"><span data-stu-id="7a194-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="7a194-138">Die Methoden Bearbeitung ist nicht in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Zeigern verfügbar, die auf CIM-Instanzen verweisen.</span><span class="sxs-lookup"><span data-stu-id="7a194-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="7a194-139">Benutzer können keine Methoden erstellen, deren Namen mit einem Unterstrich beginnen oder enden.</span><span class="sxs-lookup"><span data-stu-id="7a194-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="7a194-140">Dies ist für System Klassen und-Eigenschaften reserviert.</span><span class="sxs-lookup"><span data-stu-id="7a194-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="7a194-141">Für eine `in` -Methode werden die `out` Parameter und als Eigenschaften in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Objekten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7a194-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="7a194-142">Ein- `[in/out]` Parameter kann definiert werden, indem die gleiche-Eigenschaft zu beiden-Objekten hinzugefügt wird, auf die die `pInSignature` -und- `pOutSignature` Parameter zeigen</span><span class="sxs-lookup"><span data-stu-id="7a194-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="7a194-143">In diesem Fall haben die Eigenschaften denselben **ID** -qualifiziererwert.</span><span class="sxs-lookup"><span data-stu-id="7a194-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="7a194-144">Jede Eigenschaft in einem [__Parameters](/windows/desktop/WmiSdk/--parameters) -Klassenobjekt als `ReturnValue` muss über einen **ID** -Qualifizierer verfügen, einem NULL basierten numerischen Wert, der die Reihenfolge angibt, in der die Parameter angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7a194-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="7a194-145">Zwei Parameter können nicht denselben **ID** -Wert haben, und es kann kein **ID** -Wert übersprungen werden.</span><span class="sxs-lookup"><span data-stu-id="7a194-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="7a194-146">Wenn eine Bedingung auftritt, `PutMethod` gibt die Funktion zurück `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` .</span><span class="sxs-lookup"><span data-stu-id="7a194-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="7a194-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a194-147">Example</span></span>

<span data-ttu-id="7a194-148">Ein Beispiel finden Sie unter der [IWbemClassObject::P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) -Methode.</span><span class="sxs-lookup"><span data-stu-id="7a194-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="7a194-149">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7a194-149">Requirements</span></span>  

 <span data-ttu-id="7a194-150">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a194-150">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a194-151">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="7a194-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7a194-152">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7a194-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a194-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7a194-153">See also</span></span>

- [<span data-ttu-id="7a194-154">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="7a194-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
