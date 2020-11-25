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
ms.openlocfilehash: a0466aee47b0a6142870640c78b43f49e221ac2b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726768"
---
# <a name="nextmethod-function"></a><span data-ttu-id="0cd25-103">NextMethod-Funktion</span><span class="sxs-lookup"><span data-stu-id="0cd25-103">NextMethod function</span></span>

<span data-ttu-id="0cd25-104">Ruft die nächste Methode in einer Enumeration ab, die mit einem Aufrufen von [beginmethodenumeration](beginmethodenumeration.md)beginnt.</span><span class="sxs-lookup"><span data-stu-id="0cd25-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="0cd25-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0cd25-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="0cd25-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0cd25-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="0cd25-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="0cd25-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="0cd25-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="0cd25-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="0cd25-109">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="0cd25-109">[in] Reserved.</span></span> <span data-ttu-id="0cd25-110">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="0cd25-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="0cd25-111">vorgenommen Ein Zeiger, der vor dem-Befehl auf verweist `null` .</span><span class="sxs-lookup"><span data-stu-id="0cd25-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="0cd25-112">Wenn die Funktion zurückgegeben wird, die Adresse eines neuen `BSTR` , der den Methodennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="0cd25-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span>

`ppSignatureIn`  
<span data-ttu-id="0cd25-113">vorgenommen Ein Zeiger, der einen Zeiger auf ein [IWbemClassObject-Objekt](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) empfängt, das die `in` Parameter für die Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="0cd25-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span>

`ppSignatureOut`  
<span data-ttu-id="0cd25-114">vorgenommen Ein Zeiger, der einen Zeiger auf ein [IWbemClassObject-Objekt](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) empfängt, das die `out` Parameter für die Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="0cd25-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="0cd25-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0cd25-115">Return value</span></span>

<span data-ttu-id="0cd25-116">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="0cd25-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0cd25-117">Konstante</span><span class="sxs-lookup"><span data-stu-id="0cd25-117">Constant</span></span>  |<span data-ttu-id="0cd25-118">Wert</span><span class="sxs-lookup"><span data-stu-id="0cd25-118">Value</span></span>  |<span data-ttu-id="0cd25-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0cd25-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="0cd25-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="0cd25-120">0x8004101d</span></span> | <span data-ttu-id="0cd25-121">Die Funktion wurde nicht aufgerufen [`BeginEnumeration`](beginenumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="0cd25-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="0cd25-122">0</span><span class="sxs-lookup"><span data-stu-id="0cd25-122">0</span></span> | <span data-ttu-id="0cd25-123">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="0cd25-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="0cd25-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="0cd25-124">0x40005</span></span> | <span data-ttu-id="0cd25-125">In der-Enumeration sind keine weiteren Eigenschaften vorhanden.</span><span class="sxs-lookup"><span data-stu-id="0cd25-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="0cd25-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0cd25-126">Remarks</span></span>

<span data-ttu-id="0cd25-127">Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: nextmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) -Methode.</span><span class="sxs-lookup"><span data-stu-id="0cd25-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="0cd25-128">Der Aufrufer beginnt die enumerationssequenz, indem er die [beginmethodenumeration](beginmethodenumeration.md) -Funktion aufruft, und ruft dann die Funktion [nextmethod] auf, bis die Funktion zurückgibt `WBEM_S_NO_MORE_DATA` .</span><span class="sxs-lookup"><span data-stu-id="0cd25-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="0cd25-129">Optional schließt der Aufrufer die Sequenz durch Aufrufen von [endmethodenumeration](endmethodenumeration.md)ab.</span><span class="sxs-lookup"><span data-stu-id="0cd25-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="0cd25-130">Der Aufrufer kann die Enumeration frühzeitig beenden, indem [endmethodenumeration](endmethodenumeration.md) jederzeit aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0cd25-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="0cd25-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0cd25-131">Example</span></span>

<span data-ttu-id="0cd25-132">Ein C++-Beispiel finden Sie unter der [IWbemClassObject:: nextmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) -Methode.</span><span class="sxs-lookup"><span data-stu-id="0cd25-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="0cd25-133">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0cd25-133">Requirements</span></span>  

 <span data-ttu-id="0cd25-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cd25-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cd25-135">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="0cd25-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0cd25-136">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0cd25-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cd25-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0cd25-137">See also</span></span>

- [<span data-ttu-id="0cd25-138">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="0cd25-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
