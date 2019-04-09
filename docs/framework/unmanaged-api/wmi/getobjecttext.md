---
title: GetObjectText-Funktion (Referenz zur nicht verwalteten API)
description: Die GetObjectText-Funktion gibt ein Text-Rendering eines Objekts in MOF-Syntax.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d34cb399ac0e8780c442eeb2e95cebfd0a22ca02
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208318"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="77383-103">GetObjectText-Funktion</span><span class="sxs-lookup"><span data-stu-id="77383-103">GetObjectText function</span></span>
<span data-ttu-id="77383-104">Gibt eine Textrendering des Objekts in der Managed Object Format (MOF)-Syntax zurück.</span><span class="sxs-lookup"><span data-stu-id="77383-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="77383-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="77383-105">Syntax</span></span>  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a><span data-ttu-id="77383-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="77383-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="77383-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="77383-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="77383-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="77383-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="77383-109">[in] Normalerweise 0.</span><span class="sxs-lookup"><span data-stu-id="77383-109">[in] Normally 0.</span></span> <span data-ttu-id="77383-110">Wenn `WBEM_FLAG_NO_FLAVORS` (oder 0 x 1) angegeben wird, Qualifizierer werden ohne Weitergabe oder Art Informationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="77383-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

`pstrObjectText`   
<span data-ttu-id="77383-111">[out] Ein Zeiger auf eine `null` auf Eintrag.</span><span class="sxs-lookup"><span data-stu-id="77383-111">[out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="77383-112">Bei der Rückgabe eine neu zugeordnete `BSTR` , der eine MOF-Syntax die Darstellung des Objekts enthält.</span><span class="sxs-lookup"><span data-stu-id="77383-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="77383-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="77383-113">Return value</span></span>

<span data-ttu-id="77383-114">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="77383-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="77383-115">Konstante</span><span class="sxs-lookup"><span data-stu-id="77383-115">Constant</span></span>  |<span data-ttu-id="77383-116">Wert</span><span class="sxs-lookup"><span data-stu-id="77383-116">Value</span></span>  |<span data-ttu-id="77383-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77383-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="77383-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="77383-118">0x80041001</span></span> | <span data-ttu-id="77383-119">Es wurde ein allgemeiner Fehler.</span><span class="sxs-lookup"><span data-stu-id="77383-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="77383-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="77383-120">0x80041008</span></span> | <span data-ttu-id="77383-121">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="77383-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="77383-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="77383-122">0x80041006</span></span> | <span data-ttu-id="77383-123">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="77383-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="77383-124">0</span><span class="sxs-lookup"><span data-stu-id="77383-124">0</span></span> | <span data-ttu-id="77383-125">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="77383-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="77383-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="77383-126">Remarks</span></span>

<span data-ttu-id="77383-127">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) Methode.</span><span class="sxs-lookup"><span data-stu-id="77383-127">This function wraps a call to the [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) method.</span></span>

<span data-ttu-id="77383-128">Der MOF-Text zurückgegeben, enthält nicht alle Informationen über das Objekt, aber nur genügend Informationen für die MOF-Compiler, um das ursprüngliche Objekt neu erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="77383-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="77383-129">Beispielsweise sind keine weitergegebenen Qualifizierer oder die Eigenschaften der übergeordneten Klasse enthalten.</span><span class="sxs-lookup"><span data-stu-id="77383-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="77383-130">Der folgende Algorithmus wird verwendet, um den Text der Parameter einer Methode zu rekonstruieren:</span><span class="sxs-lookup"><span data-stu-id="77383-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="77383-131">Parameter werden in der Reihenfolge ihrer Bezeichnerwerte resequenced.</span><span class="sxs-lookup"><span data-stu-id="77383-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="77383-132">Parameter, die als angegeben sind `[in]` und `[out]` werden in einem einzigen Parameter kombiniert.</span><span class="sxs-lookup"><span data-stu-id="77383-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>
 
`pstrObjectText` <span data-ttu-id="77383-133">muss ein Zeiger auf eine `null` , wenn die Funktion aufgerufen wird; es muss auf eine Zeichenfolge, die vor dem Methodenaufruf gültig ist, da der Zeiger nicht freigegeben wird, nicht zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="77383-133">must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="77383-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="77383-134">Requirements</span></span>  
<span data-ttu-id="77383-135">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77383-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77383-136">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="77383-136">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="77383-137">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="77383-137">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="77383-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77383-138">See also</span></span>

- [<span data-ttu-id="77383-139">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="77383-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
