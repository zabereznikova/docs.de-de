---
title: Get-Funktion (Referenz zur nicht verwalteten API)
description: Die Get-Funktion ruft den angegebenen Eigenschaftswert ab.
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd85ac8b98d8613924a4acd73ac74a69f3d9b41d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535345"
---
# <a name="get-function"></a><span data-ttu-id="c7129-103">Get-Funktion</span><span class="sxs-lookup"><span data-stu-id="c7129-103">Get function</span></span>
<span data-ttu-id="c7129-104">Ruft den angegebenen Eigenschaftswert ab, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="c7129-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="c7129-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7129-105">Syntax</span></span>  
  
```  
HRESULT Get (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
); 
```  

## <a name="parameters"></a><span data-ttu-id="c7129-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c7129-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="c7129-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c7129-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="c7129-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="c7129-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="c7129-109">[in] Der Name der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c7129-109">[in] The name of the property.</span></span>

<span data-ttu-id="c7129-110">`lFlags` [in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="c7129-110">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="c7129-111">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="c7129-111">This parameter must be 0.</span></span>

<span data-ttu-id="c7129-112">`pVal` [out] Wenn die Funktion erfolgreich zurückgegeben wird, enthält Sie den Wert des der `wszName` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c7129-112">`pVal` [out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="c7129-113">Die `pval` Argument erhält, den richtigen Typ und Wert für den Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="c7129-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

<span data-ttu-id="c7129-114">`pvtType` [out] Wenn die Funktion erfolgreich zurückgegeben wird, enthält eine [CIM-Typ Konstante](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) , der den Eigenschaftentyp angibt.</span><span class="sxs-lookup"><span data-stu-id="c7129-114">`pvtType` [out] If the function returns successfully, contains a [CIM-type constant](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) that indicates the property type.</span></span> <span data-ttu-id="c7129-115">Der Wert kann auch sein `null`.</span><span class="sxs-lookup"><span data-stu-id="c7129-115">Its value can also be `null`.</span></span> 

<span data-ttu-id="c7129-116">`plFlavor` [out] Wenn die Funktion erfolgreich zurückgegeben wird, erhält Informationen über den Ursprung der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c7129-116">`plFlavor` [out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="c7129-117">Die Werte sind möglich `null`, oder eine der folgenden WBEM_FLAVOR_TYPE Konstanten definiert in der *WbemCli.h* Headerdatei:</span><span class="sxs-lookup"><span data-stu-id="c7129-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span> 

|<span data-ttu-id="c7129-118">Konstante</span><span class="sxs-lookup"><span data-stu-id="c7129-118">Constant</span></span>  |<span data-ttu-id="c7129-119">Wert</span><span class="sxs-lookup"><span data-stu-id="c7129-119">Value</span></span>  |<span data-ttu-id="c7129-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7129-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="c7129-121">0x40</span><span class="sxs-lookup"><span data-stu-id="c7129-121">0x40</span></span> | <span data-ttu-id="c7129-122">Die Eigenschaft ist eine standard-Systemeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c7129-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="c7129-123">0x20</span><span class="sxs-lookup"><span data-stu-id="c7129-123">0x20</span></span> | <span data-ttu-id="c7129-124">Für eine Klasse: Die Eigenschaft wird von der übergeordneten Klasse geerbt.</span><span class="sxs-lookup"><span data-stu-id="c7129-124">For a class: The property is inherited from the parent class.</span></span> </br> <span data-ttu-id="c7129-125">Für eine Instanz: Die Eigenschaft wurde während der von der übergeordneten Klasse geerbt nicht von der Instanz geändert.</span><span class="sxs-lookup"><span data-stu-id="c7129-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="c7129-126">0</span><span class="sxs-lookup"><span data-stu-id="c7129-126">0</span></span> | <span data-ttu-id="c7129-127">Für eine Klasse: Die Eigenschaft gehört der abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="c7129-127">For a class: The property belongs to the derived class.</span></span> </br> <span data-ttu-id="c7129-128">Für eine Instanz: Die Eigenschaft wird von der Instanz geändert werden. d. h. ein Wert angegeben wurde, oder ein Qualifizierer hinzugefügt oder geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="c7129-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="c7129-129">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c7129-129">Return value</span></span>

<span data-ttu-id="c7129-130">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="c7129-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c7129-131">Konstante</span><span class="sxs-lookup"><span data-stu-id="c7129-131">Constant</span></span>  |<span data-ttu-id="c7129-132">Wert</span><span class="sxs-lookup"><span data-stu-id="c7129-132">Value</span></span>  |<span data-ttu-id="c7129-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7129-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="c7129-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="c7129-134">0x80041001</span></span> | <span data-ttu-id="c7129-135">Es wurde ein allgemeiner Fehler.</span><span class="sxs-lookup"><span data-stu-id="c7129-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c7129-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c7129-136">0x80041008</span></span> | <span data-ttu-id="c7129-137">Ein oder mehrere Parameter sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="c7129-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="c7129-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="c7129-138">0x80041002</span></span> | <span data-ttu-id="c7129-139">Die angegebene Eigenschaft wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="c7129-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="c7129-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="c7129-140">0x80041006</span></span> | <span data-ttu-id="c7129-141">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="c7129-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="c7129-142">0</span><span class="sxs-lookup"><span data-stu-id="c7129-142">0</span></span> | <span data-ttu-id="c7129-143">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="c7129-143">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="c7129-144">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c7129-144">Remarks</span></span>

<span data-ttu-id="c7129-145">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) Methode.</span><span class="sxs-lookup"><span data-stu-id="c7129-145">This function wraps a call to the [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) method.</span></span>

<span data-ttu-id="c7129-146">Die `Get` Funktion kann auch Systemeigenschaften zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="c7129-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="c7129-147">Die `pVal` Argument erhält, den richtigen Typ und Wert für den Qualifizierer und die COM- [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) Funktion</span><span class="sxs-lookup"><span data-stu-id="c7129-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) function</span></span>

## <a name="requirements"></a><span data-ttu-id="c7129-148">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c7129-148">Requirements</span></span>  
 <span data-ttu-id="c7129-149">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7129-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7129-150">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c7129-150">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c7129-151">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c7129-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7129-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7129-152">See also</span></span>
- [<span data-ttu-id="c7129-153">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="c7129-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
