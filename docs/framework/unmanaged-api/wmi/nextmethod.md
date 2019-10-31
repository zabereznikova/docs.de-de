---
title: Nextmethod-Funktion (Referenz zur nicht verwalteten API)
description: Die nextmethod-Funktion Ruft die nächste Methode in einer Enumeration ab.
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
ms.openlocfilehash: 1c20fe5b4a081bd41f51365a36ab5f8f8cfb71ed
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127359"
---
# <a name="nextmethod-function"></a><span data-ttu-id="87559-103">Nextmethod-Funktion</span><span class="sxs-lookup"><span data-stu-id="87559-103">NextMethod function</span></span>
<span data-ttu-id="87559-104">Ruft die nächste Methode in einer Enumeration ab, die mit einem Aufrufen von [beginmethodenumeration](beginmethodenumeration.md)beginnt.</span><span class="sxs-lookup"><span data-stu-id="87559-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="87559-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="87559-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="87559-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="87559-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="87559-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="87559-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="87559-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="87559-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="87559-109">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="87559-109">[in] Reserved.</span></span> <span data-ttu-id="87559-110">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="87559-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="87559-111">vorgenommen Ein Zeiger, der auf `null` vor dem-Aufrufpunkt zeigt.</span><span class="sxs-lookup"><span data-stu-id="87559-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="87559-112">Wenn die Funktion zurückgegeben wird, wird die Adresse eines neuen `BSTR`, der den Methodennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="87559-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span> 

`ppSignatureIn`  
<span data-ttu-id="87559-113">vorgenommen Ein Zeiger, der einen Zeiger auf ein [IWbemClassObject-Objekt](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) empfängt, das die `in` Parameter für die Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="87559-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span> 

`ppSignatureOut`  
<span data-ttu-id="87559-114">vorgenommen Ein Zeiger, der einen Zeiger auf ein [IWbemClassObject-Objekt](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) empfängt, das die `out` Parameter für die Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="87559-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span> 

## <a name="return-value"></a><span data-ttu-id="87559-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="87559-115">Return value</span></span>

<span data-ttu-id="87559-116">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="87559-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="87559-117">Konstante</span><span class="sxs-lookup"><span data-stu-id="87559-117">Constant</span></span>  |<span data-ttu-id="87559-118">Wert</span><span class="sxs-lookup"><span data-stu-id="87559-118">Value</span></span>  |<span data-ttu-id="87559-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87559-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="87559-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="87559-120">0x8004101d</span></span> | <span data-ttu-id="87559-121">Die [`BeginEnumeration`](beginenumeration.md) Funktion wurde nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="87559-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="87559-122">0</span><span class="sxs-lookup"><span data-stu-id="87559-122">0</span></span> | <span data-ttu-id="87559-123">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="87559-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="87559-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="87559-124">0x40005</span></span> | <span data-ttu-id="87559-125">In der-Enumeration sind keine weiteren Eigenschaften vorhanden.</span><span class="sxs-lookup"><span data-stu-id="87559-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="87559-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="87559-126">Remarks</span></span>

<span data-ttu-id="87559-127">Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: nextmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) -Methode.</span><span class="sxs-lookup"><span data-stu-id="87559-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="87559-128">Der Aufrufer beginnt die enumerationssequenz, indem er die [beginmethodenumeration](beginmethodenumeration.md) -Funktion aufruft, und ruft dann die Funktion [nextmethod] auf, bis die Funktion `WBEM_S_NO_MORE_DATA`zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="87559-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="87559-129">Optional schließt der Aufrufer die Sequenz durch Aufrufen von [endmethodenumeration](endmethodenumeration.md)ab.</span><span class="sxs-lookup"><span data-stu-id="87559-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="87559-130">Der Aufrufer kann die Enumeration frühzeitig beenden, indem [endmethodenumeration](endmethodenumeration.md) jederzeit aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="87559-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="87559-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="87559-131">Example</span></span>

<span data-ttu-id="87559-132">Ein C++ Beispiel finden Sie unter der [IWbemClassObject:: nextmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) -Methode.</span><span class="sxs-lookup"><span data-stu-id="87559-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="87559-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="87559-133">Requirements</span></span>  
 <span data-ttu-id="87559-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87559-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87559-135">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="87559-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="87559-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="87559-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87559-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87559-137">See also</span></span>

- [<span data-ttu-id="87559-138">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="87559-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
