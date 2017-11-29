---
title: GetObjectText-Funktion (Referenz zur nicht verwalteten API)
description: Die GetObjectText-Funktion gibt ein Text-Rendering eines Objekts in MOF-Syntax.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetObjectText
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetObjectText
helpviewer_keywords: GetObjectText function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 27e25a7ab7131f5b1c995c9367de6fe5a6fae592
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="getobjecttext-function"></a><span data-ttu-id="e6b84-103">GetObjectText-Funktion</span><span class="sxs-lookup"><span data-stu-id="e6b84-103">GetObjectText function</span></span>
<span data-ttu-id="e6b84-104">Gibt eine Textrendering des Objekts in der Managed Object Format (MOF)-Syntax zurück.</span><span class="sxs-lookup"><span data-stu-id="e6b84-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="e6b84-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6b84-105">Syntax</span></span>  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a><span data-ttu-id="e6b84-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e6b84-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e6b84-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e6b84-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e6b84-108">[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="e6b84-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="e6b84-109">[in] Normalerweise 0.</span><span class="sxs-lookup"><span data-stu-id="e6b84-109">[in] Normally 0.</span></span> <span data-ttu-id="e6b84-110">Wenn `WBEM_FLAG_NO_FLAVORS` (oder 0 x 1) angegeben wird, sind die Qualifizierer ohne Weitergabe oder Flavor-Informationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e6b84-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

`pstrObjectText`   
<span data-ttu-id="e6b84-111">[out] Ein Zeiger auf eine `null` auf Eintrag.</span><span class="sxs-lookup"><span data-stu-id="e6b84-111">[out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="e6b84-112">Bei der Rückgabe eine neu zugeordnete `BSTR` , der eine MOF-Syntax die Darstellung des Objekts enthält.</span><span class="sxs-lookup"><span data-stu-id="e6b84-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="e6b84-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e6b84-113">Return value</span></span>

<span data-ttu-id="e6b84-114">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="e6b84-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e6b84-115">Konstante</span><span class="sxs-lookup"><span data-stu-id="e6b84-115">Constant</span></span>  |<span data-ttu-id="e6b84-116">Wert</span><span class="sxs-lookup"><span data-stu-id="e6b84-116">Value</span></span>  |<span data-ttu-id="e6b84-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6b84-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="e6b84-118">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="e6b84-118">0x80041001</span></span> | <span data-ttu-id="e6b84-119">Ein allgemeiner Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e6b84-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e6b84-120">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="e6b84-120">0x80041008</span></span> | <span data-ttu-id="e6b84-121">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="e6b84-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e6b84-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e6b84-122">0x80041006</span></span> | <span data-ttu-id="e6b84-123">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e6b84-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e6b84-124">0</span><span class="sxs-lookup"><span data-stu-id="e6b84-124">0</span></span> | <span data-ttu-id="e6b84-125">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="e6b84-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e6b84-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e6b84-126">Remarks</span></span>

<span data-ttu-id="e6b84-127">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="e6b84-127">This function wraps a call to the [IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="e6b84-128">Der MOF-Text zurückgegeben, enthält nicht alle Informationen über das Objekt, aber nur genügend Informationen für die MOF-Compiler, um das ursprüngliche Objekt neu erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="e6b84-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="e6b84-129">Beispielsweise sind keine weitergegebene Qualifizierer oder die Eigenschaften der übergeordneten Klasse enthalten.</span><span class="sxs-lookup"><span data-stu-id="e6b84-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="e6b84-130">Der folgende Algorithmus wird verwendet, um den Text der Parameter einer Methode zu rekonstruieren:</span><span class="sxs-lookup"><span data-stu-id="e6b84-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="e6b84-131">Parameter werden in der Reihenfolge ihrer Bezeichnerwerte resequenced.</span><span class="sxs-lookup"><span data-stu-id="e6b84-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="e6b84-132">Parameter, die als angegeben sind `[in]` und `[out]` einen einzelnen Parameter zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="e6b84-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>
 
<span data-ttu-id="e6b84-133">`pstrObjectText`muss ein Zeiger auf eine `null` beim Aufruf der Funktion ist; es muss nicht zeigen Sie auf eine Zeichenfolge, die vor dem Methodenaufruf gültig ist, da der Zeiger wird nicht aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="e6b84-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="e6b84-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e6b84-134">Requirements</span></span>  
<span data-ttu-id="e6b84-135">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6b84-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6b84-136">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e6b84-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e6b84-137">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e6b84-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6b84-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6b84-138">See also</span></span>  
[<span data-ttu-id="e6b84-139">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="e6b84-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
