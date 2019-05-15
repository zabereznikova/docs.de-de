---
title: GetPropertyQualifierSet-Funktion (Referenz zur nicht verwalteten API)
description: Die GetPropertyQualifierSet-Funktion ruft ab, der Qualifizierer, die für eine Eigenschaft festgelegt wird.
ms.date: 11/06/2017
api_name:
- GetPropertyQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyQualifierSet
helpviewer_keywords:
- GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 588c56c80cc55df3689178875a9a0500cd0ca7b8
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636404"
---
# <a name="getpropertyqualifierset-function"></a><span data-ttu-id="5d8ed-103">GetPropertyQualifierSet-Funktion</span><span class="sxs-lookup"><span data-stu-id="5d8ed-103">GetPropertyQualifierSet function</span></span>

<span data-ttu-id="5d8ed-104">Ruft den Qualifizierer ab, der für eine bestimmte Eigenschaft festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5d8ed-104">Retrieves the qualifier set for a particular property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="5d8ed-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d8ed-105">Syntax</span></span>

```cpp
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a><span data-ttu-id="5d8ed-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d8ed-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="5d8ed-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="5d8ed-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="5d8ed-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="5d8ed-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`\
<span data-ttu-id="5d8ed-109">[in] Der Eigenschaftenname.</span><span class="sxs-lookup"><span data-stu-id="5d8ed-109">[in] The property  name.</span></span> <span data-ttu-id="5d8ed-110">`wszProperty` muss auf einen gültigen zeigen `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="5d8ed-110">`wszProperty` must point to a valid `LPCWSTR`.</span></span>

`ppQualSet`\
<span data-ttu-id="5d8ed-111">[out] Empfängt den Schnittstellenzeiger, der Zugriff auf die Qualifizierer der Eigenschaft ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="5d8ed-111">[out] Receives the interface pointer that allows access to the qualifiers of the property.</span></span> <span data-ttu-id="5d8ed-112">`ppQualSet` darf nicht `null` sein.</span><span class="sxs-lookup"><span data-stu-id="5d8ed-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="5d8ed-113">Wenn ein Fehler auftritt, ein neues Objekt nicht zurückgegeben wird und der Zeiger zum zeigen auf festgelegt ist `null`.</span><span class="sxs-lookup"><span data-stu-id="5d8ed-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="5d8ed-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5d8ed-114">Return value</span></span>

<span data-ttu-id="5d8ed-115">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="5d8ed-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5d8ed-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="5d8ed-116">Constant</span></span>  |<span data-ttu-id="5d8ed-117">Wert</span><span class="sxs-lookup"><span data-stu-id="5d8ed-117">Value</span></span>  |<span data-ttu-id="5d8ed-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d8ed-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="5d8ed-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="5d8ed-119">0x80041001</span></span> | <span data-ttu-id="5d8ed-120">Es wurde ein allgemeiner Fehler.</span><span class="sxs-lookup"><span data-stu-id="5d8ed-120">There has been a general failure.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="5d8ed-121">0x80041002</span><span class="sxs-lookup"><span data-stu-id="5d8ed-121">0x80041002</span></span> | <span data-ttu-id="5d8ed-122">Die angegebene Methode ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="5d8ed-122">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="5d8ed-123">0x80041006</span><span class="sxs-lookup"><span data-stu-id="5d8ed-123">0x80041006</span></span> | <span data-ttu-id="5d8ed-124">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="5d8ed-124">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5d8ed-125">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5d8ed-125">0x80041008</span></span> | <span data-ttu-id="5d8ed-126">Ein Parameter ist `null`.</span><span class="sxs-lookup"><span data-stu-id="5d8ed-126">A parameter is `null`.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | <span data-ttu-id="5d8ed-127">0x80041030</span><span class="sxs-lookup"><span data-stu-id="5d8ed-127">0x80041030</span></span> | <span data-ttu-id="5d8ed-128">Die Funktion versucht, Qualifizierer, der eine Systemeigenschaft abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5d8ed-128">The function attempts to get qualifiers of a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="5d8ed-129">0</span><span class="sxs-lookup"><span data-stu-id="5d8ed-129">0</span></span> | <span data-ttu-id="5d8ed-130">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="5d8ed-130">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="5d8ed-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d8ed-131">Remarks</span></span>

<span data-ttu-id="5d8ed-132">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) Methode.</span><span class="sxs-lookup"><span data-stu-id="5d8ed-132">This function wraps a call to the [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) method.</span></span>

<span data-ttu-id="5d8ed-133">Ein Aufruf dieser Funktion werden nur dann, wenn das aktuelle Objekt mit der Definition einer CIM-Klasse ist.</span><span class="sxs-lookup"><span data-stu-id="5d8ed-133">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="5d8ed-134">Bearbeitung der Methode ist nicht verfügbar für [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Zeigern, die auf das CIM-Instanzen verweisen.</span><span class="sxs-lookup"><span data-stu-id="5d8ed-134">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="5d8ed-135">Da jede Methode eine eigene Qualifizierer, möglicherweise die [IWbemQualifierSet Zeiger](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lässt den Aufrufer hinzufügen, bearbeiten oder löschen diese Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="5d8ed-135">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

<span data-ttu-id="5d8ed-136">Da Systemeigenschaften keine Qualifizierer verfügen, die Funktion gibt `WBEM_E_SYSTEM_PROPERTY` Wenn Sie versuchen, Sie erhalten eine [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) Zeiger für eine Systemeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5d8ed-136">Because system properties have no qualifiers, the function returns `WBEM_E_SYSTEM_PROPERTY` if you attempt to obtain a [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) pointer for a system property.</span></span>

## <a name="requirements"></a><span data-ttu-id="5d8ed-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5d8ed-137">Requirements</span></span>

<span data-ttu-id="5d8ed-138">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d8ed-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="5d8ed-139">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5d8ed-139">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="5d8ed-140">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5d8ed-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5d8ed-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d8ed-141">See also</span></span>

- [<span data-ttu-id="5d8ed-142">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="5d8ed-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
