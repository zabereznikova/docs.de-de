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
ms.openlocfilehash: fcddca2e435a3f5bf4b8d083784613254d9801a4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43723713"
---
# <a name="getpropertyqualifierset-function"></a><span data-ttu-id="82c9c-103">GetPropertyQualifierSet-Funktion</span><span class="sxs-lookup"><span data-stu-id="82c9c-103">GetPropertyQualifierSet function</span></span>
<span data-ttu-id="82c9c-104">Ruft den Qualifizierer ab, der für eine bestimmte Eigenschaft festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="82c9c-104">Retrieves the qualifier set for a particular property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="82c9c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="82c9c-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="82c9c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="82c9c-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="82c9c-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="82c9c-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="82c9c-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="82c9c-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`  
<span data-ttu-id="82c9c-109">[in] Der Eigenschaftenname.</span><span class="sxs-lookup"><span data-stu-id="82c9c-109">[in] The property  name.</span></span> <span data-ttu-id="82c9c-110">`wszProperty` muss auf einen gültigen zeigen `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="82c9c-110">`wszProperty` must point to a valid `LPCWSTR`.</span></span> 

`ppQualSet`  
<span data-ttu-id="82c9c-111">[out] Empfängt den Schnittstellenzeiger, der Zugriff auf die Qualifizierer der Eigenschaft ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="82c9c-111">[out] Receives the interface pointer that allows access to the qualifiers of the property.</span></span> <span data-ttu-id="82c9c-112">`ppQualSet` darf nicht `null` sein.</span><span class="sxs-lookup"><span data-stu-id="82c9c-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="82c9c-113">Wenn ein Fehler auftritt, ein neues Objekt nicht zurückgegeben wird und der Zeiger zum zeigen auf festgelegt ist `null`.</span><span class="sxs-lookup"><span data-stu-id="82c9c-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="82c9c-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="82c9c-114">Return value</span></span>

<span data-ttu-id="82c9c-115">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="82c9c-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="82c9c-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="82c9c-116">Constant</span></span>  |<span data-ttu-id="82c9c-117">Wert</span><span class="sxs-lookup"><span data-stu-id="82c9c-117">Value</span></span>  |<span data-ttu-id="82c9c-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82c9c-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="82c9c-119">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="82c9c-119">0x80041001</span></span> | <span data-ttu-id="82c9c-120">Es wurde ein allgemeiner Fehler.</span><span class="sxs-lookup"><span data-stu-id="82c9c-120">There has been a general failure.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="82c9c-121">0x80041002</span><span class="sxs-lookup"><span data-stu-id="82c9c-121">0x80041002</span></span> | <span data-ttu-id="82c9c-122">Die angegebene Methode ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="82c9c-122">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="82c9c-123">0x80041006</span><span class="sxs-lookup"><span data-stu-id="82c9c-123">0x80041006</span></span> | <span data-ttu-id="82c9c-124">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="82c9c-124">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="82c9c-125">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="82c9c-125">0x80041008</span></span> | <span data-ttu-id="82c9c-126">Ein Parameter ist `null`.</span><span class="sxs-lookup"><span data-stu-id="82c9c-126">A parameter is `null`.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | <span data-ttu-id="82c9c-127">0x80041030</span><span class="sxs-lookup"><span data-stu-id="82c9c-127">0x80041030</span></span> | <span data-ttu-id="82c9c-128">Die Funktion versucht, Qualifizierer, der eine Systemeigenschaft abzurufen.</span><span class="sxs-lookup"><span data-stu-id="82c9c-128">The function attempts to get qualifiers of a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="82c9c-129">0</span><span class="sxs-lookup"><span data-stu-id="82c9c-129">0</span></span> | <span data-ttu-id="82c9c-130">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="82c9c-130">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="82c9c-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="82c9c-131">Remarks</span></span>

<span data-ttu-id="82c9c-132">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) Methode.</span><span class="sxs-lookup"><span data-stu-id="82c9c-132">This function wraps a call to the [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) method.</span></span> 

<span data-ttu-id="82c9c-133">Ein Aufruf dieser Funktion werden nur dann, wenn das aktuelle Objekt mit der Definition einer CIM-Klasse ist.</span><span class="sxs-lookup"><span data-stu-id="82c9c-133">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="82c9c-134">Bearbeitung der Methode ist nicht verfügbar für [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Ponters, die auf das CIM-Instanzen verweisen.</span><span class="sxs-lookup"><span data-stu-id="82c9c-134">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) ponters that point to CIM instances.</span></span>

<span data-ttu-id="82c9c-135">Da jede Methode eine eigene Qualifizierer, möglicherweise die [IWbemQualifierSet Zeiger](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lässt den Aufrufer hinzufügen, bearbeiten oder löschen diese Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="82c9c-135">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

<span data-ttu-id="82c9c-136">Da Systemeigenschaften keine Qualifizierer verfügen, die Funktion gibt `WBEM_E_SYSTEM_PROPERTY` Wenn Sie versuchen, Sie erhalten eine [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) Zeiger für eine Systemeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="82c9c-136">Because system properties have no qualifiers, the function returns `WBEM_E_SYSTEM_PROPERTY` if you attempt to obtain a [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) pointer for a system property.</span></span>

## <a name="requirements"></a><span data-ttu-id="82c9c-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="82c9c-137">Requirements</span></span>  
<span data-ttu-id="82c9c-138">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82c9c-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82c9c-139">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="82c9c-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="82c9c-140">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="82c9c-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82c9c-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82c9c-141">See also</span></span>  
[<span data-ttu-id="82c9c-142">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="82c9c-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
