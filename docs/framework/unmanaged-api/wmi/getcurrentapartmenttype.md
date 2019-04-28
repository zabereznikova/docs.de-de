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
ms.openlocfilehash: 9ead1c1a91b910e7cfbb09f17ba823fc7a77ce0f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609008"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="61b0e-103">GetCurrentApartmentType-Funktion</span><span class="sxs-lookup"><span data-stu-id="61b0e-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="61b0e-104">Ruft den Typ des Apartments ab, in dem die aufrufende Funktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="61b0e-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="61b0e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="61b0e-105">Syntax</span></span>  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="61b0e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="61b0e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="61b0e-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="61b0e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="61b0e-108">[in] Ein Zeiger auf ein [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) Instanz.</span><span class="sxs-lookup"><span data-stu-id="61b0e-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="61b0e-109">[out] Ein Zeiger auf ein [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) Enumerationswert, der Aufrufer Apartment angibt.</span><span class="sxs-lookup"><span data-stu-id="61b0e-109">[out] A pointer to an [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="61b0e-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="61b0e-110">Return value</span></span>

|<span data-ttu-id="61b0e-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="61b0e-111">Constant</span></span>  |<span data-ttu-id="61b0e-112">Wert</span><span class="sxs-lookup"><span data-stu-id="61b0e-112">Value</span></span>  |<span data-ttu-id="61b0e-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61b0e-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="61b0e-114">0</span><span class="sxs-lookup"><span data-stu-id="61b0e-114">0</span></span> | <span data-ttu-id="61b0e-115">Die Funktion wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="61b0e-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="61b0e-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="61b0e-116">0x80000008</span></span> | <span data-ttu-id="61b0e-117">Der Aufrufer eine Wohnung nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="61b0e-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="61b0e-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="61b0e-118">Remarks</span></span>

<span data-ttu-id="61b0e-119">Diese Funktion umschließt einen Aufruf der [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) Methode.</span><span class="sxs-lookup"><span data-stu-id="61b0e-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="61b0e-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="61b0e-120">Requirements</span></span>  
 <span data-ttu-id="61b0e-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61b0e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61b0e-122">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="61b0e-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="61b0e-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="61b0e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61b0e-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61b0e-124">See also</span></span>

- [<span data-ttu-id="61b0e-125">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="61b0e-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
