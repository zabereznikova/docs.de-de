---
title: NextMethod-Funktion (Nicht verwaltete API-Referenz)
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
ms.openlocfilehash: 36acd6135110a8865bd8efdda628c352c01b4f26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174926"
---
# <a name="nextmethod-function"></a><span data-ttu-id="c0245-103">NextMethod-Funktion</span><span class="sxs-lookup"><span data-stu-id="c0245-103">NextMethod function</span></span>
<span data-ttu-id="c0245-104">Ruft die nächste Methode in einer Enumeration ab, die mit einem Aufruf von [BeginMethodEnumeration](beginmethodenumeration.md)beginnt.</span><span class="sxs-lookup"><span data-stu-id="c0245-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c0245-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0245-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="c0245-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c0245-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="c0245-107">[in] Dieser Parameter ist nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0245-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="c0245-108">[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="c0245-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="c0245-109">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="c0245-109">[in] Reserved.</span></span> <span data-ttu-id="c0245-110">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="c0245-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="c0245-111">[out] Ein Zeiger, auf `null` den vor dem Aufruf zeigt.</span><span class="sxs-lookup"><span data-stu-id="c0245-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="c0245-112">Wenn die Funktion zurückkehrt, wird `BSTR` die Adresse eines Neuen, der den Methodennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="c0245-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span>

`ppSignatureIn`  
<span data-ttu-id="c0245-113">[out] Ein Zeiger, der einen Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) empfängt, das die `in` Parameter für die Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="c0245-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span>

`ppSignatureOut`  
<span data-ttu-id="c0245-114">[out] Ein Zeiger, der einen Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) empfängt, das die `out` Parameter für die Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="c0245-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="c0245-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c0245-115">Return value</span></span>

<span data-ttu-id="c0245-116">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="c0245-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c0245-117">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="c0245-117">Constant</span></span>  |<span data-ttu-id="c0245-118">value</span><span class="sxs-lookup"><span data-stu-id="c0245-118">Value</span></span>  |<span data-ttu-id="c0245-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0245-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="c0245-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="c0245-120">0x8004101d</span></span> | <span data-ttu-id="c0245-121">Es gab keinen [`BeginEnumeration`](beginenumeration.md) Aufruf der Funktion.</span><span class="sxs-lookup"><span data-stu-id="c0245-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="c0245-122">0</span><span class="sxs-lookup"><span data-stu-id="c0245-122">0</span></span> | <span data-ttu-id="c0245-123">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="c0245-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="c0245-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="c0245-124">0x40005</span></span> | <span data-ttu-id="c0245-125">Es sind keine Eigenschaften mehr in der Enumeration vorhanden.</span><span class="sxs-lookup"><span data-stu-id="c0245-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="c0245-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c0245-126">Remarks</span></span>

<span data-ttu-id="c0245-127">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::NextMethod-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)</span><span class="sxs-lookup"><span data-stu-id="c0245-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="c0245-128">Der Aufrufer beginnt die Enumerationssequenz, indem er die [BeginMethodEnumeration-Funktion](beginmethodenumeration.md) aufruft, `WBEM_S_NO_MORE_DATA`und ruft dann die [NextMethod]-Funktion auf, bis die Funktion zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c0245-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="c0245-129">Optional beendet der Aufrufer die Sequenz, indem er [EndMethodEnumeration aufruft.](endmethodenumeration.md)</span><span class="sxs-lookup"><span data-stu-id="c0245-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="c0245-130">Der Aufrufer kann die Enumeration jederzeit vorzeitig beenden, indem er [EndMethodEnumeration](endmethodenumeration.md) aufruft.</span><span class="sxs-lookup"><span data-stu-id="c0245-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="c0245-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c0245-131">Example</span></span>

<span data-ttu-id="c0245-132">Ein C++-Beispiel finden Sie in der [IWbemClassObject::NextMethod-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)</span><span class="sxs-lookup"><span data-stu-id="c0245-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c0245-133">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c0245-133">Requirements</span></span>  
 <span data-ttu-id="c0245-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0245-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0245-135">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c0245-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c0245-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c0245-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0245-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c0245-137">See also</span></span>

- [<span data-ttu-id="c0245-138">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="c0245-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
