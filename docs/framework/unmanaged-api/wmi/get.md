---
title: Get-Funktion (Referenz zur nicht verwalteten API)
description: Die Get-Funktion Ruft den angegebenen Eigenschafts Wert ab.
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
ms.openlocfilehash: 7cc0c285f79b2791863fce251e4683aa7b55341b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553687"
---
# <a name="get-function"></a><span data-ttu-id="8fe73-103">Get-Funktion</span><span class="sxs-lookup"><span data-stu-id="8fe73-103">Get function</span></span>

<span data-ttu-id="8fe73-104">Ruft den angegebenen Eigenschafts Wert ab, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="8fe73-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="8fe73-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8fe73-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="8fe73-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8fe73-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="8fe73-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="8fe73-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="8fe73-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="8fe73-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="8fe73-109">[in] Der Name der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8fe73-109">[in] The name of the property.</span></span>

`lFlags`\
<span data-ttu-id="8fe73-110">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="8fe73-110">[in] Reserved.</span></span> <span data-ttu-id="8fe73-111">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="8fe73-111">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="8fe73-112">vorgenommen Wenn die Funktion erfolgreich zurückgegeben wird, enthält Sie den Wert der- `wszName` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8fe73-112">[out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="8fe73-113">Dem `pval` -Argument werden der richtige Typ und der richtige Wert für den Qualifizierer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="8fe73-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

`pvtType`\
<span data-ttu-id="8fe73-114">vorgenommen Wenn die Funktion erfolgreich zurückgegeben wird, enthält eine [CIM-Type-Konstante](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) , die den Eigenschaftentyp angibt.</span><span class="sxs-lookup"><span data-stu-id="8fe73-114">[out] If the function returns successfully, contains a [CIM-type constant](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) that indicates the property type.</span></span> <span data-ttu-id="8fe73-115">Der Wert kann auch sein `null` .</span><span class="sxs-lookup"><span data-stu-id="8fe73-115">Its value can also be `null`.</span></span>

`plFlavor`\
<span data-ttu-id="8fe73-116">vorgenommen Wenn die Funktion erfolgreich zurückgegeben wird, empfängt Informationen über den Ursprung der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8fe73-116">[out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="8fe73-117">Der Wert kann `null` oder einer der folgenden WBEM_FLAVOR_TYPE Konstanten sein, die in der Header Datei " *wbemcli. h* " definiert sind:</span><span class="sxs-lookup"><span data-stu-id="8fe73-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span>

|<span data-ttu-id="8fe73-118">Konstant</span><span class="sxs-lookup"><span data-stu-id="8fe73-118">Constant</span></span>  |<span data-ttu-id="8fe73-119">Wert</span><span class="sxs-lookup"><span data-stu-id="8fe73-119">Value</span></span>  |<span data-ttu-id="8fe73-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8fe73-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="8fe73-121">0x40</span><span class="sxs-lookup"><span data-stu-id="8fe73-121">0x40</span></span> | <span data-ttu-id="8fe73-122">Die-Eigenschaft ist eine Standardsystem Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8fe73-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="8fe73-123">0x20</span><span class="sxs-lookup"><span data-stu-id="8fe73-123">0x20</span></span> | <span data-ttu-id="8fe73-124">Für eine Klasse: die Eigenschaft wird von der übergeordneten Klasse geerbt.</span><span class="sxs-lookup"><span data-stu-id="8fe73-124">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="8fe73-125">Für eine-Instanz: die-Eigenschaft wurde von der-Instanz nicht geändert, während Sie von der übergeordneten Klasse geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="8fe73-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="8fe73-126">0</span><span class="sxs-lookup"><span data-stu-id="8fe73-126">0</span></span> | <span data-ttu-id="8fe73-127">Für eine Klasse: die Eigenschaft gehört zur abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="8fe73-127">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="8fe73-128">Für eine-Instanz: die-Eigenschaft wird von der-Instanz geändert. Das heißt, es wurde ein Wert angegeben, oder es wurde ein Qualifizierer hinzugefügt oder geändert.</span><span class="sxs-lookup"><span data-stu-id="8fe73-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="8fe73-129">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8fe73-129">Return value</span></span>

<span data-ttu-id="8fe73-130">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="8fe73-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8fe73-131">Konstant</span><span class="sxs-lookup"><span data-stu-id="8fe73-131">Constant</span></span>  |<span data-ttu-id="8fe73-132">Wert</span><span class="sxs-lookup"><span data-stu-id="8fe73-132">Value</span></span>  |<span data-ttu-id="8fe73-133">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8fe73-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="8fe73-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="8fe73-134">0x80041001</span></span> | <span data-ttu-id="8fe73-135">Es ist ein allgemeiner Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8fe73-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8fe73-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8fe73-136">0x80041008</span></span> | <span data-ttu-id="8fe73-137">Mindestens ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="8fe73-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="8fe73-138">0x80041002 angezeigt</span><span class="sxs-lookup"><span data-stu-id="8fe73-138">0x80041002</span></span> | <span data-ttu-id="8fe73-139">Die angegebene Eigenschaft wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="8fe73-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="8fe73-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="8fe73-140">0x80041006</span></span> | <span data-ttu-id="8fe73-141">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="8fe73-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="8fe73-142">0</span><span class="sxs-lookup"><span data-stu-id="8fe73-142">0</span></span> | <span data-ttu-id="8fe73-143">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="8fe73-143">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="8fe73-144">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8fe73-144">Remarks</span></span>

<span data-ttu-id="8fe73-145">Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject:: Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) -Methode.</span><span class="sxs-lookup"><span data-stu-id="8fe73-145">This function wraps a call to the [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) method.</span></span>

<span data-ttu-id="8fe73-146">Die- `Get` Funktion kann auch Systemeigenschaften zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="8fe73-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="8fe73-147">Dem `pVal` -Argument werden der richtige Typ und Wert für den Qualifizierer und die com- [variantit](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) -Funktion zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="8fe73-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) function</span></span>

## <a name="requirements"></a><span data-ttu-id="8fe73-148">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8fe73-148">Requirements</span></span>

 <span data-ttu-id="8fe73-149">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fe73-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="8fe73-150">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="8fe73-150">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="8fe73-151">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8fe73-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8fe73-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fe73-152">See also</span></span>

- [<span data-ttu-id="8fe73-153">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="8fe73-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
