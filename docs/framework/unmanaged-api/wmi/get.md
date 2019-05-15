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
ms.openlocfilehash: b8a1942f903b1c7c15e58077e35b6a72a86a9419
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636529"
---
# <a name="get-function"></a><span data-ttu-id="668eb-103">Get-Funktion</span><span class="sxs-lookup"><span data-stu-id="668eb-103">Get function</span></span>

<span data-ttu-id="668eb-104">Ruft den angegebenen Eigenschaftswert ab, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="668eb-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="668eb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="668eb-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="668eb-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="668eb-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="668eb-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="668eb-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="668eb-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="668eb-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="668eb-109">[in] Der Name der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="668eb-109">[in] The name of the property.</span></span>

`lFlags`\
<span data-ttu-id="668eb-110">[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="668eb-110">[in] Reserved.</span></span> <span data-ttu-id="668eb-111">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="668eb-111">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="668eb-112">[out] Wenn die Funktion erfolgreich zurückgegeben wird, enthält Sie den Wert des der `wszName` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="668eb-112">[out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="668eb-113">Die `pval` Argument erhält, den richtigen Typ und Wert für den Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="668eb-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

`pvtType`\
<span data-ttu-id="668eb-114">[out] Wenn die Funktion erfolgreich zurückgegeben wird, enthält eine [CIM-Typ Konstante](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) , der den Eigenschaftentyp angibt.</span><span class="sxs-lookup"><span data-stu-id="668eb-114">[out] If the function returns successfully, contains a [CIM-type constant](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) that indicates the property type.</span></span> <span data-ttu-id="668eb-115">Der Wert kann auch sein `null`.</span><span class="sxs-lookup"><span data-stu-id="668eb-115">Its value can also be `null`.</span></span> 

`plFlavor`\
<span data-ttu-id="668eb-116">[out] Wenn die Funktion erfolgreich zurückgegeben wird, erhält Informationen über den Ursprung der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="668eb-116">[out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="668eb-117">Die Werte sind möglich `null`, oder eine der folgenden WBEM_FLAVOR_TYPE Konstanten definiert in der *WbemCli.h* Headerdatei:</span><span class="sxs-lookup"><span data-stu-id="668eb-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span> 

|<span data-ttu-id="668eb-118">Konstante</span><span class="sxs-lookup"><span data-stu-id="668eb-118">Constant</span></span>  |<span data-ttu-id="668eb-119">Wert</span><span class="sxs-lookup"><span data-stu-id="668eb-119">Value</span></span>  |<span data-ttu-id="668eb-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="668eb-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="668eb-121">0x40</span><span class="sxs-lookup"><span data-stu-id="668eb-121">0x40</span></span> | <span data-ttu-id="668eb-122">Die Eigenschaft ist eine standard-Systemeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="668eb-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="668eb-123">0x20</span><span class="sxs-lookup"><span data-stu-id="668eb-123">0x20</span></span> | <span data-ttu-id="668eb-124">Für eine Klasse: Die Eigenschaft wird von der übergeordneten Klasse geerbt.</span><span class="sxs-lookup"><span data-stu-id="668eb-124">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="668eb-125">Für eine Instanz: Die Eigenschaft wurde während der von der übergeordneten Klasse geerbt nicht von der Instanz geändert.</span><span class="sxs-lookup"><span data-stu-id="668eb-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="668eb-126">0</span><span class="sxs-lookup"><span data-stu-id="668eb-126">0</span></span> | <span data-ttu-id="668eb-127">Für eine Klasse: Die Eigenschaft gehört der abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="668eb-127">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="668eb-128">Für eine Instanz: Die Eigenschaft wird von der Instanz geändert werden. d. h. ein Wert angegeben wurde, oder ein Qualifizierer hinzugefügt oder geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="668eb-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="668eb-129">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="668eb-129">Return value</span></span>

<span data-ttu-id="668eb-130">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="668eb-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="668eb-131">Konstante</span><span class="sxs-lookup"><span data-stu-id="668eb-131">Constant</span></span>  |<span data-ttu-id="668eb-132">Wert</span><span class="sxs-lookup"><span data-stu-id="668eb-132">Value</span></span>  |<span data-ttu-id="668eb-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="668eb-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="668eb-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="668eb-134">0x80041001</span></span> | <span data-ttu-id="668eb-135">Es wurde ein allgemeiner Fehler.</span><span class="sxs-lookup"><span data-stu-id="668eb-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="668eb-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="668eb-136">0x80041008</span></span> | <span data-ttu-id="668eb-137">Ein oder mehrere Parameter sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="668eb-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="668eb-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="668eb-138">0x80041002</span></span> | <span data-ttu-id="668eb-139">Die angegebene Eigenschaft wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="668eb-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="668eb-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="668eb-140">0x80041006</span></span> | <span data-ttu-id="668eb-141">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="668eb-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="668eb-142">0</span><span class="sxs-lookup"><span data-stu-id="668eb-142">0</span></span> | <span data-ttu-id="668eb-143">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="668eb-143">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="668eb-144">Hinweise</span><span class="sxs-lookup"><span data-stu-id="668eb-144">Remarks</span></span>

<span data-ttu-id="668eb-145">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) Methode.</span><span class="sxs-lookup"><span data-stu-id="668eb-145">This function wraps a call to the [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) method.</span></span>

<span data-ttu-id="668eb-146">Die `Get` Funktion kann auch Systemeigenschaften zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="668eb-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="668eb-147">Die `pVal` Argument erhält, den richtigen Typ und Wert für den Qualifizierer und die COM- [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) Funktion</span><span class="sxs-lookup"><span data-stu-id="668eb-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) function</span></span>

## <a name="requirements"></a><span data-ttu-id="668eb-148">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="668eb-148">Requirements</span></span>

 <span data-ttu-id="668eb-149">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="668eb-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="668eb-150">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="668eb-150">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="668eb-151">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="668eb-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="668eb-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="668eb-152">See also</span></span>

- [<span data-ttu-id="668eb-153">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="668eb-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
