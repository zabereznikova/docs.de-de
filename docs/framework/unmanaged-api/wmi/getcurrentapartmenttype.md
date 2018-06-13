---
title: GetCurrentApartmentType-Funktion (Referenz zur nicht verwalteten API)
description: GetCurrentApartmentType-Funktion ruft den Typ des Apartment, in der der Aufrufer ausgeführt wird.
ms.date: 11/06/2017
api_name:
- GetCurrentApartmentType
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetCurrentApartmentType
helpviewer_keywords:
- GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca7b5fa5bf6d845d542d3e80c0571e59f3d4c1e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461723"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="5d7e5-103">GetCurrentApartmentType-Funktion</span><span class="sxs-lookup"><span data-stu-id="5d7e5-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="5d7e5-104">Ruft den Typ des Apartment, in der der Aufrufer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5d7e5-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="5d7e5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d7e5-105">Syntax</span></span>  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="5d7e5-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d7e5-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5d7e5-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="5d7e5-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="5d7e5-108">[in] Ein Zeiger auf ein [IComThreadingInfo](https://msdn.microsoft.com/library/windows/desktop/ms694502(v=vs.85).aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="5d7e5-108">[in] A pointer to an [IComThreadingInfo](https://msdn.microsoft.com/library/windows/desktop/ms694502(v=vs.85).aspx) instance.</span></span>

`aptType`  
<span data-ttu-id="5d7e5-109">[out] Ein Zeiger auf ein [APTTYPE](https://msdn.microsoft.com/library/windows/desktop/ms693793(v=vs.85).aspx) Enumerationswert, der Aufrufer Apartment angibt.</span><span class="sxs-lookup"><span data-stu-id="5d7e5-109">[out] A pointer to an [APTTYPE](https://msdn.microsoft.com/library/windows/desktop/ms693793(v=vs.85).aspx) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="5d7e5-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5d7e5-110">Return value</span></span>


|<span data-ttu-id="5d7e5-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="5d7e5-111">Constant</span></span>  |<span data-ttu-id="5d7e5-112">Wert</span><span class="sxs-lookup"><span data-stu-id="5d7e5-112">Value</span></span>  |<span data-ttu-id="5d7e5-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d7e5-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="5d7e5-114">0</span><span class="sxs-lookup"><span data-stu-id="5d7e5-114">0</span></span> | <span data-ttu-id="5d7e5-115">Die Funktion wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5d7e5-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="5d7e5-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="5d7e5-116">0x80000008</span></span> | <span data-ttu-id="5d7e5-117">Der Aufrufer ist nicht in einem Apartment ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5d7e5-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="5d7e5-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d7e5-118">Remarks</span></span>

<span data-ttu-id="5d7e5-119">Diese Funktion dient als Wrapper für einen Aufruf der [IComThreadingInfo::GetCurrentApartmentType](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="5d7e5-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="5d7e5-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5d7e5-120">Requirements</span></span>  
 <span data-ttu-id="5d7e5-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d7e5-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d7e5-122">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5d7e5-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5d7e5-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5d7e5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d7e5-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d7e5-124">See also</span></span>  
[<span data-ttu-id="5d7e5-125">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="5d7e5-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
