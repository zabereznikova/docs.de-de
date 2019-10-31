---
title: GetMethod-Funktion (Referenz zur nicht verwalteten API)
description: Die GetMethod-Funktion Ruft Informationen zu einer Methode ab.
ms.date: 11/06/2017
api_name:
- GetMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethod
helpviewer_keywords:
- GetMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 48986f5ff1cbbb45840ec1a059aa86711848d717
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102588"
---
# <a name="getmethod-function"></a><span data-ttu-id="74c97-103">GetMethod-Funktion</span><span class="sxs-lookup"><span data-stu-id="74c97-103">GetMethod function</span></span>

<span data-ttu-id="74c97-104">Ruft Informationen zur angegebenen Methode ab.</span><span class="sxs-lookup"><span data-stu-id="74c97-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="74c97-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="74c97-105">Syntax</span></span>

```cpp
HRESULT GetMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```

## <a name="parameters"></a><span data-ttu-id="74c97-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="74c97-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="74c97-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="74c97-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="74c97-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="74c97-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="74c97-109">in Der Methodenname.</span><span class="sxs-lookup"><span data-stu-id="74c97-109">[in] The method name.</span></span> <span data-ttu-id="74c97-110">Dieser Parameter kann nicht `null` werden und muss auf einen gültigen `LPCWSTR`zeigen.</span><span class="sxs-lookup"><span data-stu-id="74c97-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`\
<span data-ttu-id="74c97-111">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="74c97-111">[in] Reserved.</span></span> <span data-ttu-id="74c97-112">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="74c97-112">This parameter must be 0.</span></span>

`ppInSignature`\
<span data-ttu-id="74c97-113">vorgenommen Ein Zeiger auf die Adresse einer [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz, die die in den Parametern der Methode beschreibt.</span><span class="sxs-lookup"><span data-stu-id="74c97-113">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the in parameters to the method.</span></span> <span data-ttu-id="74c97-114">Dieser Parameter wird ignoriert, wenn er auf `null`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="74c97-114">This parameter is ignored if it is set to `null`.</span></span>

`ppOutSignature`\
<span data-ttu-id="74c97-115">vorgenommen Ein Zeiger auf die Adresse einer [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz, die die Out-Parameter für die Methode beschreibt.</span><span class="sxs-lookup"><span data-stu-id="74c97-115">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="74c97-116">Dieser Parameter wird ignoriert, wenn er auf `null`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="74c97-116">This parameter is ignored if it is set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="74c97-117">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="74c97-117">Return value</span></span>

<span data-ttu-id="74c97-118">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="74c97-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="74c97-119">Konstante</span><span class="sxs-lookup"><span data-stu-id="74c97-119">Constant</span></span>  |<span data-ttu-id="74c97-120">Wert</span><span class="sxs-lookup"><span data-stu-id="74c97-120">Value</span></span>  |<span data-ttu-id="74c97-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74c97-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="74c97-122">0x80041002 angezeigt</span><span class="sxs-lookup"><span data-stu-id="74c97-122">0x80041002</span></span> | <span data-ttu-id="74c97-123">Die angegebene Eigenschaft wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="74c97-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="74c97-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="74c97-124">0x80041006</span></span> | <span data-ttu-id="74c97-125">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="74c97-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="74c97-126">0</span><span class="sxs-lookup"><span data-stu-id="74c97-126">0</span></span> | <span data-ttu-id="74c97-127">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="74c97-127">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="74c97-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74c97-128">Remarks</span></span>

<span data-ttu-id="74c97-129">Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject:: GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) -Methode.</span><span class="sxs-lookup"><span data-stu-id="74c97-129">This function wraps a call to the [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="74c97-130">Die Windows-Verwaltung kann den [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Zeiger auf `null` festlegen, wenn die Methode über keine in-Parameter verfügt.</span><span class="sxs-lookup"><span data-stu-id="74c97-130">Windows Management can set the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="74c97-131">In `ppInSignature` und `ppOutSignature` die in-bzw. out-Parameter als Eigenschaften in einer `IWbemClassObject` Instanz der System Klasse [_Parameters](/windows/desktop/WmiSdk/--parameters)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74c97-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](/windows/desktop/WmiSdk/--parameters).</span></span> <span data-ttu-id="74c97-132">Die Eigenschaften in `ppInSignature` werden `Param`*n*benannt, wobei *n* die Position des Parameters in der Methoden Signatur (z. b. `Param1`, `Param2`usw.) ist.</span><span class="sxs-lookup"><span data-stu-id="74c97-132">The properties in `ppInSignature` are named `Param`*n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="74c97-133">Die Eigenschaften in `ppOutSignature` werden ebenfalls `Param`*n*benannt, und der Rückgabewert hat den Namen `ReturnValue`.</span><span class="sxs-lookup"><span data-stu-id="74c97-133">The properties in `ppOutSignature` are also named `Param`*n*, and the return value is named `ReturnValue`.</span></span> <span data-ttu-id="74c97-134">Weitere Informationen und ein Beispiel finden Sie unter [IWbemClassObject:: GetMethod-Methode](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span><span class="sxs-lookup"><span data-stu-id="74c97-134">For more information and an example, see [IWbemClassObject::GetMethod method](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span></span>

## <a name="requirements"></a><span data-ttu-id="74c97-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="74c97-135">Requirements</span></span>

<span data-ttu-id="74c97-136">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74c97-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="74c97-137">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="74c97-137">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="74c97-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="74c97-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="74c97-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74c97-139">See also</span></span>

- [<span data-ttu-id="74c97-140">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="74c97-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
