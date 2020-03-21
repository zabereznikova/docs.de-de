---
title: Get-Funktion (Nicht verwaltete API-Referenz)
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
ms.openlocfilehash: 67fcfb301eebfcf4ed4fdcaa5c9ddf85c47a6073
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174978"
---
# <a name="get-function"></a><span data-ttu-id="58960-103">Get-Funktion</span><span class="sxs-lookup"><span data-stu-id="58960-103">Get function</span></span>

<span data-ttu-id="58960-104">Ruft den angegebenen Eigenschaftswert ab, sofern er vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="58960-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="58960-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="58960-105">Syntax</span></span>

```cpp
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

## <a name="parameters"></a><span data-ttu-id="58960-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="58960-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="58960-107">[in] Dieser Parameter ist nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="58960-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="58960-108">[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="58960-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="58960-109">[in] Der Name der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="58960-109">[in] The name of the property.</span></span>

`lFlags`\
<span data-ttu-id="58960-110">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="58960-110">[in] Reserved.</span></span> <span data-ttu-id="58960-111">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="58960-111">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="58960-112">[out] Wenn die Funktion erfolgreich zurückgegeben wird, enthält den Wert der `wszName` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="58960-112">[out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="58960-113">Dem `pval` Argument wird der richtige Typ und Wert für den Qualifizierer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="58960-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

`pvtType`\
<span data-ttu-id="58960-114">[out] Wenn die Funktion erfolgreich zurückgegeben wird, enthält eine [CIM-Typkonstante,](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) die den Eigenschaftstyp angibt.</span><span class="sxs-lookup"><span data-stu-id="58960-114">[out] If the function returns successfully, contains a [CIM-type constant](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) that indicates the property type.</span></span> <span data-ttu-id="58960-115">Sein Wert kann `null`auch sein.</span><span class="sxs-lookup"><span data-stu-id="58960-115">Its value can also be `null`.</span></span>

`plFlavor`\
<span data-ttu-id="58960-116">[out] Wenn die Funktion erfolgreich zurückkehrt, erhält Informationen über den Ursprung der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="58960-116">[out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="58960-117">Sein Wert `null`kann , oder eine der folgenden WBEM_FLAVOR_TYPE konstanten sein, die in der *WbemCli.h-Headerdatei* definiert sind:</span><span class="sxs-lookup"><span data-stu-id="58960-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span>

|<span data-ttu-id="58960-118">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="58960-118">Constant</span></span>  |<span data-ttu-id="58960-119">value</span><span class="sxs-lookup"><span data-stu-id="58960-119">Value</span></span>  |<span data-ttu-id="58960-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58960-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="58960-121">0x40</span><span class="sxs-lookup"><span data-stu-id="58960-121">0x40</span></span> | <span data-ttu-id="58960-122">Die Eigenschaft ist eine Standard-Systemeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="58960-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="58960-123">0x20</span><span class="sxs-lookup"><span data-stu-id="58960-123">0x20</span></span> | <span data-ttu-id="58960-124">Für eine Klasse: Die Eigenschaft wird von der übergeordneten Klasse geerbt.</span><span class="sxs-lookup"><span data-stu-id="58960-124">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="58960-125">Für eine Instanz: Die Eigenschaft wurde zwar von der übergeordneten Klasse geerbt, aber von der Instanz nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="58960-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="58960-126">0</span><span class="sxs-lookup"><span data-stu-id="58960-126">0</span></span> | <span data-ttu-id="58960-127">Für eine Klasse: Die Eigenschaft gehört zur abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="58960-127">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="58960-128">Für eine Instanz: Die Eigenschaft wird von der Instanz geändert; D. h., es wurde ein Wert angegeben oder ein Qualifizierer hinzugefügt oder geändert.</span><span class="sxs-lookup"><span data-stu-id="58960-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="58960-129">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="58960-129">Return value</span></span>

<span data-ttu-id="58960-130">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="58960-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="58960-131">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="58960-131">Constant</span></span>  |<span data-ttu-id="58960-132">value</span><span class="sxs-lookup"><span data-stu-id="58960-132">Value</span></span>  |<span data-ttu-id="58960-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58960-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="58960-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="58960-134">0x80041001</span></span> | <span data-ttu-id="58960-135">Es ist ein allgemeines Versagen aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="58960-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="58960-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="58960-136">0x80041008</span></span> | <span data-ttu-id="58960-137">Mindestens ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="58960-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="58960-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="58960-138">0x80041002</span></span> | <span data-ttu-id="58960-139">Die angegebene Eigenschaft wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="58960-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="58960-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="58960-140">0x80041006</span></span> | <span data-ttu-id="58960-141">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="58960-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="58960-142">0</span><span class="sxs-lookup"><span data-stu-id="58960-142">0</span></span> | <span data-ttu-id="58960-143">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="58960-143">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="58960-144">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="58960-144">Remarks</span></span>

<span data-ttu-id="58960-145">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::Get-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get)</span><span class="sxs-lookup"><span data-stu-id="58960-145">This function wraps a call to the [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) method.</span></span>

<span data-ttu-id="58960-146">Die `Get` Funktion kann auch Systemeigenschaften zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="58960-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="58960-147">Dem `pVal` Argument wird der richtige Typ und Wert für den Qualifizierer und die COM [VariantInit-Funktion](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="58960-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) function</span></span>

## <a name="requirements"></a><span data-ttu-id="58960-148">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="58960-148">Requirements</span></span>

 <span data-ttu-id="58960-149">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58960-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="58960-150">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="58960-150">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="58960-151">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="58960-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="58960-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="58960-152">See also</span></span>

- [<span data-ttu-id="58960-153">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="58960-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
