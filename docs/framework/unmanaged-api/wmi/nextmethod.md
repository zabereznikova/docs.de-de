---
title: NextMethod-Funktion (Referenz zur nicht verwalteten API)
description: Die NextMethod-Funktion ruft die nächste Methode in einer Enumeration ab.
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a730947b0c962d801975917cdf752136e7221c4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746480"
---
# <a name="nextmethod-function"></a><span data-ttu-id="184a6-103">NextMethod-Funktion</span><span class="sxs-lookup"><span data-stu-id="184a6-103">NextMethod function</span></span>
<span data-ttu-id="184a6-104">Ruft die nächste Methode in einer Enumeration, die mit einem Aufruf von beginnt [BeginMethodEnumeration](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="184a6-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="184a6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="184a6-105">Syntax</span></span>  
  
```cpp  
HRESULT NextMethod (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature   
); 
```  

## <a name="parameters"></a><span data-ttu-id="184a6-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="184a6-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="184a6-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="184a6-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="184a6-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="184a6-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="184a6-109">[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="184a6-109">[in] Reserved.</span></span> <span data-ttu-id="184a6-110">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="184a6-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="184a6-111">[out] Ein Zeiger, der auf zeigt `null` vor dem Aufruf.</span><span class="sxs-lookup"><span data-stu-id="184a6-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="184a6-112">Wenn die Funktion zurückgibt, die Adresse eines neuen `BSTR` , enthält der Name der Methode.</span><span class="sxs-lookup"><span data-stu-id="184a6-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span> 

`ppSignatureIn`  
<span data-ttu-id="184a6-113">[out] Ein Zeiger, der einen Zeiger auf empfängt eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , enthält die `in` Parameter für die Methode.</span><span class="sxs-lookup"><span data-stu-id="184a6-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span> 

`ppSignatureOut`  
<span data-ttu-id="184a6-114">[out] Ein Zeiger, der einen Zeiger auf empfängt eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , enthält die `out` Parameter für die Methode.</span><span class="sxs-lookup"><span data-stu-id="184a6-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span> 

## <a name="return-value"></a><span data-ttu-id="184a6-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="184a6-115">Return value</span></span>

<span data-ttu-id="184a6-116">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="184a6-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="184a6-117">Konstante</span><span class="sxs-lookup"><span data-stu-id="184a6-117">Constant</span></span>  |<span data-ttu-id="184a6-118">Wert</span><span class="sxs-lookup"><span data-stu-id="184a6-118">Value</span></span>  |<span data-ttu-id="184a6-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="184a6-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="184a6-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="184a6-120">0x8004101d</span></span> | <span data-ttu-id="184a6-121">Es wurde kein Aufruf von der [ `BeginEnumeration` ](beginenumeration.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="184a6-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="184a6-122">0</span><span class="sxs-lookup"><span data-stu-id="184a6-122">0</span></span> | <span data-ttu-id="184a6-123">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="184a6-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="184a6-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="184a6-124">0x40005</span></span> | <span data-ttu-id="184a6-125">Es gibt keine weiteren Eigenschaften in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="184a6-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="184a6-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="184a6-126">Remarks</span></span>

<span data-ttu-id="184a6-127">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) Methode.</span><span class="sxs-lookup"><span data-stu-id="184a6-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="184a6-128">Der Aufrufer beginnt der Enumerationssequenz durch Aufrufen der [BeginMethodEnumeration](beginmethodenumeration.md) funktionieren, und klicken Sie dann die [NextMethod]-Funktion aufruft, bis die Funktion gibt `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="184a6-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="184a6-129">Der Aufrufer wird optional die Sequenz beendet, indem Aufrufen [EndMethodEnumeration](endmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="184a6-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="184a6-130">Der Aufrufer kann die Enumeration beenden, in der frühen durch Aufrufen von [EndMethodEnumeration](endmethodenumeration.md) zu einem beliebigen Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="184a6-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="184a6-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="184a6-131">Example</span></span>

<span data-ttu-id="184a6-132">Eine C++-Beispiel finden Sie unter den [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) Methode.</span><span class="sxs-lookup"><span data-stu-id="184a6-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="184a6-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="184a6-133">Requirements</span></span>  
 <span data-ttu-id="184a6-134">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="184a6-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="184a6-135">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="184a6-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="184a6-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="184a6-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="184a6-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="184a6-137">See also</span></span>

- [<span data-ttu-id="184a6-138">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="184a6-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
