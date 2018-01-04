---
title: GetPropertyQualifierSet-Funktion (Referenz zur nicht verwalteten API)
description: "Die GetPropertyQualifierSet-Funktion ruft den Qualifizierer für eine Eigenschaft festgelegt."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyQualifierSet
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyQualifierSet
helpviewer_keywords: GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ca2981c8833abaafd5d206b66d6e91f34e2c91d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getpropertyqualifierset-function"></a><span data-ttu-id="9d2fe-103">GetPropertyQualifierSet-Funktion</span><span class="sxs-lookup"><span data-stu-id="9d2fe-103">GetPropertyQualifierSet function</span></span>
<span data-ttu-id="9d2fe-104">Ruft den Qualifizierer, legen Sie für eine bestimmte Eigenschaft ab.</span><span class="sxs-lookup"><span data-stu-id="9d2fe-104">Retrieves the qualifier set for a particular property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="9d2fe-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d2fe-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="9d2fe-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9d2fe-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="9d2fe-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="9d2fe-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="9d2fe-108">[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="9d2fe-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethod`  
<span data-ttu-id="9d2fe-109">[in] Der Eigenschaftenname.</span><span class="sxs-lookup"><span data-stu-id="9d2fe-109">[in] The property  name.</span></span> <span data-ttu-id="9d2fe-110">`wszProperty`muss eine gültige zeigen `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="9d2fe-110">`wszProperty` must point to a valid `LPCWSTR`.</span></span> 

`ppQualSet`  
<span data-ttu-id="9d2fe-111">[out] Empfängt den Schnittstellenzeiger, der Zugriff auf die Qualifizierer der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="9d2fe-111">[out] Receives the interface pointer that allows access to the qualifiers of the property.</span></span> <span data-ttu-id="9d2fe-112">`ppQualSet` darf nicht `null` sein.</span><span class="sxs-lookup"><span data-stu-id="9d2fe-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="9d2fe-113">Wenn ein Fehler auftritt, ein neues Objekt nicht zurückgegeben wird und der Zeiger festgelegt wird, auf `null`.</span><span class="sxs-lookup"><span data-stu-id="9d2fe-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="9d2fe-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9d2fe-114">Return value</span></span>

<span data-ttu-id="9d2fe-115">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="9d2fe-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9d2fe-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="9d2fe-116">Constant</span></span>  |<span data-ttu-id="9d2fe-117">Wert</span><span class="sxs-lookup"><span data-stu-id="9d2fe-117">Value</span></span>  |<span data-ttu-id="9d2fe-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d2fe-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="9d2fe-119">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="9d2fe-119">0x80041001</span></span> | <span data-ttu-id="9d2fe-120">Ein allgemeiner Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9d2fe-120">There has been a general failure.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="9d2fe-121">0x80041002</span><span class="sxs-lookup"><span data-stu-id="9d2fe-121">0x80041002</span></span> | <span data-ttu-id="9d2fe-122">Die angegebene Methode ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="9d2fe-122">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="9d2fe-123">0x80041006</span><span class="sxs-lookup"><span data-stu-id="9d2fe-123">0x80041006</span></span> | <span data-ttu-id="9d2fe-124">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="9d2fe-124">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="9d2fe-125">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="9d2fe-125">0x80041008</span></span> | <span data-ttu-id="9d2fe-126">Ein Parameter ist `null`.</span><span class="sxs-lookup"><span data-stu-id="9d2fe-126">A parameter is `null`.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | <span data-ttu-id="9d2fe-127">0x80041030</span><span class="sxs-lookup"><span data-stu-id="9d2fe-127">0x80041030</span></span> | <span data-ttu-id="9d2fe-128">Die Funktion versucht, Qualifizierer, der eine Systemeigenschaft abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9d2fe-128">The function attempts to get qualifiers of a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="9d2fe-129">0</span><span class="sxs-lookup"><span data-stu-id="9d2fe-129">0</span></span> | <span data-ttu-id="9d2fe-130">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="9d2fe-130">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="9d2fe-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9d2fe-131">Remarks</span></span>

<span data-ttu-id="9d2fe-132">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::GetPropertyQualifierSet](https://msdn.microsoft.com/library/aa391450(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="9d2fe-132">This function wraps a call to the [IWbemClassObject::GetPropertyQualifierSet](https://msdn.microsoft.com/library/aa391450(v=vs.85).aspx) method.</span></span> 

<span data-ttu-id="9d2fe-133">Ein Aufruf dieser Funktion wird unterstützt, nur, wenn das aktuelle Objekt die Definition einer CIM-Klasse.</span><span class="sxs-lookup"><span data-stu-id="9d2fe-133">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="9d2fe-134">Methode Bearbeitung ist nicht verfügbar für [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Ponters, die auf das CIM-Instanzen verweisen.</span><span class="sxs-lookup"><span data-stu-id="9d2fe-134">Method manipulation is not available for [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters that point to CIM instances.</span></span>

<span data-ttu-id="9d2fe-135">Da jeder Methode seine eigenen Qualifizierer möglicherweise die [IWbemQualifierSet Zeiger](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) ermöglicht den Aufrufer hinzufügen, bearbeiten oder löschen diese Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="9d2fe-135">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) lets the caller add, edit, or delete these qualifiers.</span></span>

<span data-ttu-id="9d2fe-136">Da Systemeigenschaften keine Qualifizierer haben, gibt die Funktion `WBEM_E_SYSTEM_PROPERTY` Wenn Sie versuchen, erhalten eine [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) Zeiger für ein Systemeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9d2fe-136">Because system properties have no qualifiers, the function returns `WBEM_E_SYSTEM_PROPERTY` if you attempt to obtain a [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) pointer for a system property.</span></span>

## <a name="requirements"></a><span data-ttu-id="9d2fe-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9d2fe-137">Requirements</span></span>  
<span data-ttu-id="9d2fe-138">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d2fe-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d2fe-139">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9d2fe-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="9d2fe-140">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9d2fe-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d2fe-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d2fe-141">See also</span></span>  
[<span data-ttu-id="9d2fe-142">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="9d2fe-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
