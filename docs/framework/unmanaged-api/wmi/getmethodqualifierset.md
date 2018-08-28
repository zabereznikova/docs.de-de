---
title: GetMethodQualifierSet-Funktion (Referenz zur nicht verwalteten API)
description: GetMethodQualifierSet-Funktion ruft die Qualifizierer Satz einer Methode ab.
ms.date: 11/06/2017
api_name:
- GetMethodQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodQualifierSet
helpviewer_keywords:
- GetMethodQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a363591f5db7a2dbcba1147df35d8c023c9b0707
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2018
ms.locfileid: "43001408"
---
# <a name="getmethodqualifierset-function"></a><span data-ttu-id="f11b3-103">GetMethodQualifierSet-Funktion</span><span class="sxs-lookup"><span data-stu-id="f11b3-103">GetMethodQualifierSet function</span></span>
<span data-ttu-id="f11b3-104">Ruft den Qualifizierer aus, legen Sie für eine bestimmte Methode ab.</span><span class="sxs-lookup"><span data-stu-id="f11b3-104">Retrieves the qualifier set for a particular method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="f11b3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f11b3-105">Syntax</span></span>  
  
```  
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="f11b3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f11b3-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f11b3-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="f11b3-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f11b3-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="f11b3-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`  
<span data-ttu-id="f11b3-109">[in] Name der Methode.</span><span class="sxs-lookup"><span data-stu-id="f11b3-109">[in] The method  name.</span></span> <span data-ttu-id="f11b3-110">`wszMethod` muss auf einen gültigen zeigen `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="f11b3-110">`wszMethod` must point to a valid `LPCWSTR`.</span></span> 

`ppQualSet`  
<span data-ttu-id="f11b3-111">[out] Empfängt den Schnittstellenzeiger, der Zugriff auf die Qualifizierer, der die Methode ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="f11b3-111">[out] Receives the interface pointer that allows access to the qualifiers of the method.</span></span> <span data-ttu-id="f11b3-112">`ppQualSet` darf nicht `null` sein.</span><span class="sxs-lookup"><span data-stu-id="f11b3-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="f11b3-113">Wenn ein Fehler auftritt, ein neues Objekt nicht zurückgegeben wird und der Zeiger zum zeigen auf festgelegt ist `null`.</span><span class="sxs-lookup"><span data-stu-id="f11b3-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="f11b3-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f11b3-114">Return value</span></span>

<span data-ttu-id="f11b3-115">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="f11b3-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f11b3-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="f11b3-116">Constant</span></span>  |<span data-ttu-id="f11b3-117">Wert</span><span class="sxs-lookup"><span data-stu-id="f11b3-117">Value</span></span>  |<span data-ttu-id="f11b3-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f11b3-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="f11b3-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="f11b3-119">0x80041002</span></span> | <span data-ttu-id="f11b3-120">Die angegebene Methode ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f11b3-120">The specified method does not exist.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f11b3-121">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="f11b3-121">0x80041008</span></span> | <span data-ttu-id="f11b3-122">Ein Parameter ist `null`.</span><span class="sxs-lookup"><span data-stu-id="f11b3-122">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="f11b3-123">0</span><span class="sxs-lookup"><span data-stu-id="f11b3-123">0</span></span> | <span data-ttu-id="f11b3-124">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="f11b3-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="f11b3-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f11b3-125">Remarks</span></span>

<span data-ttu-id="f11b3-126">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) Methode.</span><span class="sxs-lookup"><span data-stu-id="f11b3-126">This function wraps a call to the [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) method.</span></span> 

<span data-ttu-id="f11b3-127">Ein Aufruf dieser Funktion werden nur dann, wenn das aktuelle Objekt mit der Definition einer CIM-Klasse ist.</span><span class="sxs-lookup"><span data-stu-id="f11b3-127">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="f11b3-128">Bearbeitung der Methode ist nicht verfügbar für [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Ponters, die auf das CIM-Instanzen verweisen.</span><span class="sxs-lookup"><span data-stu-id="f11b3-128">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) ponters that point to CIM instances.</span></span>

<span data-ttu-id="f11b3-129">Da jede Methode eine eigene Qualifizierer, möglicherweise die [IWbemQualifierSet Zeiger](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lässt den Aufrufer hinzufügen, bearbeiten oder löschen diese Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="f11b3-129">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

## <a name="requirements"></a><span data-ttu-id="f11b3-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f11b3-130">Requirements</span></span>  
<span data-ttu-id="f11b3-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f11b3-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f11b3-132">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f11b3-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f11b3-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f11b3-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f11b3-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f11b3-134">See also</span></span>  
[<span data-ttu-id="f11b3-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="f11b3-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
