---
title: GetCurrentApartmentType-Funktion (Referenz zur nicht verwalteten API)
description: Die GetCurrentApartmentType-Funktion ruft ab, der Typ des Apartment, in dem der Aufrufer ausgeführt wird.
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
ms.openlocfilehash: 76c852ac81126895ea3a2e1b40473722c8445201
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746555"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="3d737-103">GetCurrentApartmentType-Funktion</span><span class="sxs-lookup"><span data-stu-id="3d737-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="3d737-104">Ruft den Typ des Apartments ab, in dem die aufrufende Funktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3d737-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="3d737-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d737-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="3d737-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="3d737-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3d737-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="3d737-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="3d737-108">[in] Ein Zeiger auf ein [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) Instanz.</span><span class="sxs-lookup"><span data-stu-id="3d737-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="3d737-109">[out] Ein Zeiger auf ein [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) Enumerationswert, der Aufrufer Apartment angibt.</span><span class="sxs-lookup"><span data-stu-id="3d737-109">[out] A pointer to an [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="3d737-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3d737-110">Return value</span></span>

|<span data-ttu-id="3d737-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="3d737-111">Constant</span></span>  |<span data-ttu-id="3d737-112">Wert</span><span class="sxs-lookup"><span data-stu-id="3d737-112">Value</span></span>  |<span data-ttu-id="3d737-113">Description</span><span class="sxs-lookup"><span data-stu-id="3d737-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="3d737-114">0</span><span class="sxs-lookup"><span data-stu-id="3d737-114">0</span></span> | <span data-ttu-id="3d737-115">Die Funktion wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="3d737-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="3d737-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="3d737-116">0x80000008</span></span> | <span data-ttu-id="3d737-117">Der Aufrufer eine Wohnung nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3d737-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="3d737-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3d737-118">Remarks</span></span>

<span data-ttu-id="3d737-119">Diese Funktion umschließt einen Aufruf der [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) Methode.</span><span class="sxs-lookup"><span data-stu-id="3d737-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3d737-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3d737-120">Requirements</span></span>  
 <span data-ttu-id="3d737-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d737-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d737-122">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3d737-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3d737-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3d737-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d737-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d737-124">See also</span></span>

- [<span data-ttu-id="3d737-125">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="3d737-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
