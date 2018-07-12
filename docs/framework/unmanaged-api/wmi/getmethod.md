---
title: GetMethod-Funktion (Referenz zur nicht verwalteten API)
description: GetMethod-Funktion ruft Informationen zu einer Methode ab.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65b8cb74a028892a3494e818f2b523f75e8766a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460446"
---
# <a name="getmethod-function"></a><span data-ttu-id="ee93f-103">GetMethod-Funktion</span><span class="sxs-lookup"><span data-stu-id="ee93f-103">GetMethod function</span></span>
<span data-ttu-id="ee93f-104">Ruft Informationen über die angegebene Methode ab.</span><span class="sxs-lookup"><span data-stu-id="ee93f-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="ee93f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee93f-105">Syntax</span></span>  
  
```  
HRESULT GetMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
); 
```  

## <a name="parameters"></a><span data-ttu-id="ee93f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ee93f-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ee93f-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="ee93f-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ee93f-108">[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="ee93f-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="ee93f-109">[in] Der Methodenname.</span><span class="sxs-lookup"><span data-stu-id="ee93f-109">[in] The method name.</span></span> <span data-ttu-id="ee93f-110">Dieser Parameter darf nicht sein `null` muss einem gültigen zeigen `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="ee93f-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`  
<span data-ttu-id="ee93f-111">[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="ee93f-111">[in] Reserved.</span></span> <span data-ttu-id="ee93f-112">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="ee93f-112">This parameter must be 0.</span></span>

`ppInSignature`   
<span data-ttu-id="ee93f-113">[out] Ein Zeiger auf die Adresse des ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) -Instanz, die in Paramteers an die Methode beschreibt.</span><span class="sxs-lookup"><span data-stu-id="ee93f-113">[out] A pointer to the address of an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance that describes the in paramteers to the method.</span></span> <span data-ttu-id="ee93f-114">Dieser Parameter wird ignoriert, wenn er, um festgelegt ist `null`.</span><span class="sxs-lookup"><span data-stu-id="ee93f-114">This parameter is ignored if it is set to `null`.</span></span> 

`ppOutSignature`  
<span data-ttu-id="ee93f-115">[out] Ein Zeiger auf die Adresse des ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz, die die Out-Parameter an die Methode beschreibt.</span><span class="sxs-lookup"><span data-stu-id="ee93f-115">[out] A pointer to the address of an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="ee93f-116">Dieser Parameter wird ignoriert, wenn er, um festgelegt ist `null`.</span><span class="sxs-lookup"><span data-stu-id="ee93f-116">This parameter is ignored if it is set to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="ee93f-117">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ee93f-117">Return value</span></span>

<span data-ttu-id="ee93f-118">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="ee93f-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ee93f-119">Konstante</span><span class="sxs-lookup"><span data-stu-id="ee93f-119">Constant</span></span>  |<span data-ttu-id="ee93f-120">Wert</span><span class="sxs-lookup"><span data-stu-id="ee93f-120">Value</span></span>  |<span data-ttu-id="ee93f-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee93f-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="ee93f-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="ee93f-122">0x80041002</span></span> | <span data-ttu-id="ee93f-123">Die angegebene Eigenschaft wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="ee93f-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ee93f-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ee93f-124">0x80041006</span></span> | <span data-ttu-id="ee93f-125">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="ee93f-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ee93f-126">0</span><span class="sxs-lookup"><span data-stu-id="ee93f-126">0</span></span> | <span data-ttu-id="ee93f-127">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="ee93f-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ee93f-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ee93f-128">Remarks</span></span>

<span data-ttu-id="ee93f-129">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::GetMethod](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="ee93f-129">This function wraps a call to the [IWbemClassObject::GetMethod](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="ee93f-130">Verwaltung von Windows können festlegen, die [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Zeiger auf `null` Wenn die Methode keine in-Parameter hat.</span><span class="sxs-lookup"><span data-stu-id="ee93f-130">Windows Management can set the [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="ee93f-131">In `ppInSignature` und `ppOutSignature` beschreiben "" in und out-Parameter, jeweils als Eigenschaften in einem `IWbemClassObject` Instanz der Systemklasse [_Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="ee93f-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx).</span></span> <span data-ttu-id="ee93f-132">Die Eigenschaften im `ppInsignature` heißen **Param *** n*, wobei *n* ist die Position des Parameters in der Methodensignatur (z. B. `Param1`, `Param2`usw..).</span><span class="sxs-lookup"><span data-stu-id="ee93f-132">The properties in `ppInsignature` are named **Param***n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="ee93f-133">Die Eigenschaften im `ppOutSignature` sind auch mit dem Namen **Param *** n*, und der Rückgabewert lautet **ReturnValue**.</span><span class="sxs-lookup"><span data-stu-id="ee93f-133">The properties in `ppOutSignature` are also named **Param***n*, and the return value is named **ReturnValue**.</span></span> <span data-ttu-id="ee93f-134">Weitere Informationen und ein Beispiel finden Sie unter [IWbemClassObject::GetMethod Methode](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="ee93f-134">For more information and an example, see [IWbemClassObject::GetMethod method](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx).</span></span>

## <a name="requirements"></a><span data-ttu-id="ee93f-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ee93f-135">Requirements</span></span>  
<span data-ttu-id="ee93f-136">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee93f-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee93f-137">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ee93f-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ee93f-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ee93f-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee93f-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee93f-139">See also</span></span>  
[<span data-ttu-id="ee93f-140">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="ee93f-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
