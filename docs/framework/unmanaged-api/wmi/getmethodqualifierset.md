---
title: GetMethodQualifierSet-Funktion (Referenz zur nicht verwalteten API)
description: Die GetMethodQualifierSet-Funktion ruft eine Methode Qualifizierer Satz ab.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetMethodQualifierSet
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetMethodQualifierSet
helpviewer_keywords: GetMethodQualifierSet function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 79a19d3bb40dd4d435bd7cf97eb0b4071020648e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="getmethodqualifierset-function"></a><span data-ttu-id="15248-103">GetMethodQualifierSet-Funktion</span><span class="sxs-lookup"><span data-stu-id="15248-103">GetMethodQualifierSet function</span></span>
<span data-ttu-id="15248-104">Ruft den Qualifizierer für eine bestimmte Methode festgelegt.</span><span class="sxs-lookup"><span data-stu-id="15248-104">Retrieves the qualifier set for a particular method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="15248-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="15248-105">Syntax</span></span>  
  
```  
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="15248-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="15248-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="15248-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="15248-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="15248-108">[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="15248-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethod`  
<span data-ttu-id="15248-109">[in] Der Methodenname.</span><span class="sxs-lookup"><span data-stu-id="15248-109">[in] The method  name.</span></span> <span data-ttu-id="15248-110">`wszMethod`muss eine gültige zeigen `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="15248-110">`wszMethod` must point to a valid `LPCWSTR`.</span></span> 

`ppQualSet`  
<span data-ttu-id="15248-111">[out] Empfängt den Schnittstellenzeiger, der Zugriff auf die Qualifizierer, der die Methode ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="15248-111">[out] Receives the interface pointer that allows access to the qualifiers of the method.</span></span> <span data-ttu-id="15248-112">`ppQualSet` darf nicht `null` sein.</span><span class="sxs-lookup"><span data-stu-id="15248-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="15248-113">Wenn ein Fehler auftritt, ein neues Objekt nicht zurückgegeben wird und der Zeiger festgelegt wird, auf `null`.</span><span class="sxs-lookup"><span data-stu-id="15248-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="15248-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="15248-114">Return value</span></span>

<span data-ttu-id="15248-115">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="15248-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="15248-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="15248-116">Constant</span></span>  |<span data-ttu-id="15248-117">Wert</span><span class="sxs-lookup"><span data-stu-id="15248-117">Value</span></span>  |<span data-ttu-id="15248-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15248-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="15248-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="15248-119">0x80041002</span></span> | <span data-ttu-id="15248-120">Die angegebene Methode ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="15248-120">The specified method does not exist.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="15248-121">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="15248-121">0x80041008</span></span> | <span data-ttu-id="15248-122">Ein Parameter ist `null`.</span><span class="sxs-lookup"><span data-stu-id="15248-122">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="15248-123">0</span><span class="sxs-lookup"><span data-stu-id="15248-123">0</span></span> | <span data-ttu-id="15248-124">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="15248-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="15248-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15248-125">Remarks</span></span>

<span data-ttu-id="15248-126">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::GetMethodQualifierSet](https://msdn.microsoft.com/library/aa391446(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="15248-126">This function wraps a call to the [IWbemClassObject::GetMethodQualifierSet](https://msdn.microsoft.com/library/aa391446(v=vs.85).aspx) method.</span></span> 

<span data-ttu-id="15248-127">Ein Aufruf dieser Funktion wird unterstützt, nur, wenn das aktuelle Objekt die Definition einer CIM-Klasse.</span><span class="sxs-lookup"><span data-stu-id="15248-127">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="15248-128">Methode Bearbeitung ist nicht verfügbar für [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Ponters, die auf das CIM-Instanzen verweisen.</span><span class="sxs-lookup"><span data-stu-id="15248-128">Method manipulation is not available for [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters that point to CIM instances.</span></span>

<span data-ttu-id="15248-129">Da jeder Methode seine eigenen Qualifizierer möglicherweise die [IWbemQualifierSet Zeiger](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) ermöglicht den Aufrufer hinzufügen, bearbeiten oder löschen diese Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="15248-129">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) lets the caller add, edit, or delete these qualifiers.</span></span>

## <a name="requirements"></a><span data-ttu-id="15248-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15248-130">Requirements</span></span>  
<span data-ttu-id="15248-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15248-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15248-132">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="15248-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="15248-133">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="15248-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15248-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15248-134">See also</span></span>  
[<span data-ttu-id="15248-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="15248-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
