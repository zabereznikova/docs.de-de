---
title: Getcurrentapartmenttype-Funktion (Referenz zur nicht verwalteten API)
description: Die getcurrentapartmenttype-Funktion Ruft den Typ des Apartment ab, in dem der Aufrufer ausgeführt wird.
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
ms.openlocfilehash: 6ecd2b49d6850a8fae25ddca54f855fdda2ccabb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120351"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="b4511-103">Getcurrentapartmenttype-Funktion</span><span class="sxs-lookup"><span data-stu-id="b4511-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="b4511-104">Ruft den Typ des Apartments ab, in dem die aufrufende Funktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b4511-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="b4511-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4511-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="b4511-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b4511-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b4511-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="b4511-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b4511-108">in Ein Zeiger auf eine [icomthreadinginfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="b4511-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="b4511-109">vorgenommen Ein Zeiger auf einen [apttype](/windows/win32/api/objidlbase/ne-objidlbase-apttype) -Enumerationswert, der das Apartment des Aufrufers angibt.</span><span class="sxs-lookup"><span data-stu-id="b4511-109">[out] A pointer to an [APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="b4511-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b4511-110">Return value</span></span>

|<span data-ttu-id="b4511-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="b4511-111">Constant</span></span>  |<span data-ttu-id="b4511-112">Wert</span><span class="sxs-lookup"><span data-stu-id="b4511-112">Value</span></span>  |<span data-ttu-id="b4511-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4511-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="b4511-114">0</span><span class="sxs-lookup"><span data-stu-id="b4511-114">0</span></span> | <span data-ttu-id="b4511-115">Die Funktion wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b4511-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="b4511-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="b4511-116">0x80000008</span></span> | <span data-ttu-id="b4511-117">Der Aufrufer wird nicht in einem Apartment ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b4511-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="b4511-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4511-118">Remarks</span></span>

<span data-ttu-id="b4511-119">Diese Funktion umschließt einen Aufrufen der [icomthreadinginfo:: getcurrentapartmenttype](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) -Methode.</span><span class="sxs-lookup"><span data-stu-id="b4511-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b4511-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4511-120">Requirements</span></span>  
 <span data-ttu-id="b4511-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4511-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4511-122">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="b4511-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b4511-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b4511-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4511-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4511-124">See also</span></span>

- [<span data-ttu-id="b4511-125">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="b4511-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
