---
title: GetCurrentApartmentType-Funktion (Referenz zur nicht verwalteten API)
description: "GetCurrentApartmentType-Funktion ruft den Typ des Apartment, in der der Aufrufer ausgeführt wird."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetCurrentApartmentType
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetCurrentApartmentType
helpviewer_keywords: GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a42c6c3c778dbdefd4b83621e65b81741b940ebe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="d763f-103">GetCurrentApartmentType-Funktion</span><span class="sxs-lookup"><span data-stu-id="d763f-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="d763f-104">Ruft den Typ des Apartment, in der der Aufrufer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d763f-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="d763f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d763f-105">Syntax</span></span>  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="d763f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d763f-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="d763f-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="d763f-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="d763f-108">[in] Ein Zeiger auf ein [IComThreadingInfo](https://msdn.microsoft.com/library/windows/desktop/ms694502(v=vs.85).aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="d763f-108">[in] A pointer to an [IComThreadingInfo](https://msdn.microsoft.com/library/windows/desktop/ms694502(v=vs.85).aspx) instance.</span></span>

`aptType`  
<span data-ttu-id="d763f-109">[out] Ein Zeiger auf ein [APTTYPE](https://msdn.microsoft.com/library/windows/desktop/ms693793(v=vs.85).aspx) Enumerationswert, der Aufrufer Apartment angibt.</span><span class="sxs-lookup"><span data-stu-id="d763f-109">[out] A pointer to an [APTTYPE](https://msdn.microsoft.com/library/windows/desktop/ms693793(v=vs.85).aspx) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="d763f-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d763f-110">Return value</span></span>


|<span data-ttu-id="d763f-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="d763f-111">Constant</span></span>  |<span data-ttu-id="d763f-112">Wert</span><span class="sxs-lookup"><span data-stu-id="d763f-112">Value</span></span>  |<span data-ttu-id="d763f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d763f-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="d763f-114">0</span><span class="sxs-lookup"><span data-stu-id="d763f-114">0</span></span> | <span data-ttu-id="d763f-115">Die Funktion wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d763f-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="d763f-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="d763f-116">0x80000008</span></span> | <span data-ttu-id="d763f-117">Der Aufrufer ist nicht in einem Apartment ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d763f-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="d763f-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d763f-118">Remarks</span></span>

<span data-ttu-id="d763f-119">Diese Funktion dient als Wrapper für einen Aufruf der [IComThreadingInfo::GetCurrentApartmentType](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="d763f-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="d763f-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d763f-120">Requirements</span></span>  
 <span data-ttu-id="d763f-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d763f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d763f-122">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d763f-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d763f-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d763f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d763f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d763f-124">See also</span></span>  
[<span data-ttu-id="d763f-125">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="d763f-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
