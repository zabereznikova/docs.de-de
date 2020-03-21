---
title: GetCurrentApartmentType-Funktion (Nicht verwaltete API-Referenz)
description: Die GetCurrentApartmentType-Funktion ruft den Apartmenttyp ab, in dem der Aufrufer ausgeführt wird.
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
ms.openlocfilehash: 3fc88f7997ee5a6c25359243e1ee97a041050eb7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176824"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="ba0ba-103">GetCurrentApartmentType-Funktion</span><span class="sxs-lookup"><span data-stu-id="ba0ba-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="ba0ba-104">Ruft den Typ des Apartments ab, in dem die aufrufende Funktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ba0ba-104">Retrieves the type of apartment in which the caller is executing.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ba0ba-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba0ba-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc,
   [in] IComThreadingInfo*    ptr,
   [out] APTTYPE*             aptType
);
```  

## <a name="parameters"></a><span data-ttu-id="ba0ba-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba0ba-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ba0ba-107">[in] Dieser Parameter ist nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="ba0ba-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ba0ba-108">[in] Ein Zeiger auf eine [IComThreadingInfo-Instanz.](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo)</span><span class="sxs-lookup"><span data-stu-id="ba0ba-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="ba0ba-109">[out] Ein Zeiger auf einen APTTYPE-Enumerationswert, der die Wohnung des Aufrufers angibt. [APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype)</span><span class="sxs-lookup"><span data-stu-id="ba0ba-109">[out] A pointer to an [APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="ba0ba-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ba0ba-110">Return value</span></span>

|<span data-ttu-id="ba0ba-111">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="ba0ba-111">Constant</span></span>  |<span data-ttu-id="ba0ba-112">value</span><span class="sxs-lookup"><span data-stu-id="ba0ba-112">Value</span></span>  |<span data-ttu-id="ba0ba-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba0ba-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="ba0ba-114">0</span><span class="sxs-lookup"><span data-stu-id="ba0ba-114">0</span></span> | <span data-ttu-id="ba0ba-115">Die Funktion wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ba0ba-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="ba0ba-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="ba0ba-116">0x80000008</span></span> | <span data-ttu-id="ba0ba-117">Der Anrufer wird nicht in einer Wohnung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ba0ba-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="ba0ba-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ba0ba-118">Remarks</span></span>

<span data-ttu-id="ba0ba-119">Diese Funktion umschließt einen Aufruf der [IComThreadingInfo::GetCurrentApartmentType-Methode.](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype)</span><span class="sxs-lookup"><span data-stu-id="ba0ba-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ba0ba-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ba0ba-120">Requirements</span></span>  
 <span data-ttu-id="ba0ba-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba0ba-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba0ba-122">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ba0ba-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ba0ba-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ba0ba-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba0ba-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba0ba-124">See also</span></span>

- [<span data-ttu-id="ba0ba-125">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="ba0ba-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
