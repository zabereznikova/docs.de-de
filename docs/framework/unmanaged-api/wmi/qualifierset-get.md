---
title: QualifierSet_Get-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion QualifierSet_Get Ruft einen benannten Qualifizierer ab.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 93ba4e59dda4806931ba085f8c63b63a1d8bd797
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetget-function"></a><span data-ttu-id="a8c77-103">QualifierSet_Get-Funktion</span><span class="sxs-lookup"><span data-stu-id="a8c77-103">QualifierSet_Get function</span></span>
<span data-ttu-id="a8c77-104">Ruft den angegebenen benannten Qualifizierer ab.</span><span class="sxs-lookup"><span data-stu-id="a8c77-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="a8c77-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a8c77-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Get (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a><span data-ttu-id="a8c77-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a8c77-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="a8c77-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="a8c77-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="a8c77-108">[in] Ein Zeiger auf ein [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="a8c77-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`wszName`   
<span data-ttu-id="a8c77-109">[in] Der Name des Qualifizierers der, deren Wert angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="a8c77-109">[in] The name of the qualifier whose value is requested.</span></span>

`lFlags`   
<span data-ttu-id="a8c77-110">[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="a8c77-110">[in] Reserved.</span></span> <span data-ttu-id="a8c77-111">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="a8c77-111">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="a8c77-112">[out] Bei erfolgreicher Ausführung, den richtigen Typ und Wert für den Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="a8c77-112">[out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="a8c77-113">Wenn die Funktion fehlschlägt, die `VARIANT` verweist `pVal` wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="a8c77-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="a8c77-114">Wenn dieser Parameter ist `null`, der Parameter wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a8c77-114">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="a8c77-115">[out] Ein Zeiger auf einen Long-Wert, der die Qualifizierer Flavor Bits für den Qualifizierer des angeforderten empfängt.</span><span class="sxs-lookup"><span data-stu-id="a8c77-115">[out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="a8c77-116">Dieser Parameter kann sein, wenn Flavor-Informationen nicht erwünscht ist, `null`.</span><span class="sxs-lookup"><span data-stu-id="a8c77-116">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="a8c77-117">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a8c77-117">Return value</span></span>

<span data-ttu-id="a8c77-118">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="a8c77-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a8c77-119">Konstante</span><span class="sxs-lookup"><span data-stu-id="a8c77-119">Constant</span></span>  |<span data-ttu-id="a8c77-120">Wert</span><span class="sxs-lookup"><span data-stu-id="a8c77-120">Value</span></span>  |<span data-ttu-id="a8c77-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8c77-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="a8c77-122">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="a8c77-122">0x80041008</span></span> | <span data-ttu-id="a8c77-123">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="a8c77-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="a8c77-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="a8c77-124">0x80041002</span></span> | <span data-ttu-id="a8c77-125">Der angegebene Qualifizierer ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a8c77-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="a8c77-126">0</span><span class="sxs-lookup"><span data-stu-id="a8c77-126">0</span></span> | <span data-ttu-id="a8c77-127">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="a8c77-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="a8c77-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a8c77-128">Remarks</span></span>

<span data-ttu-id="a8c77-129">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemQualifierSet::Get](https://msdn.microsoft.com/library/aa391867(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="a8c77-129">This function wraps a call to the [IWbemQualifierSet::Get](https://msdn.microsoft.com/library/aa391867(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="a8c77-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a8c77-130">Requirements</span></span>  
 <span data-ttu-id="a8c77-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8c77-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8c77-132">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a8c77-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a8c77-133">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a8c77-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8c77-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8c77-134">See also</span></span>  
[<span data-ttu-id="a8c77-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="a8c77-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
