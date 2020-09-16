---
title: GetErrorInfo-Funktion (Referenz zur nicht verwalteten API)
description: Die GetErrorInfo-Funktion ruft Fehlerinformationen aus dem vorherigen Funktions aufgerufenen ab.
ms.date: 11/06/2017
api_name:
- GetErrorInfo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetErrorInfo
helpviewer_keywords:
- GetErrorInfo function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 9a80c0b5522113e704336cda29362a0406077931
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553674"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="5c376-103">GetErrorInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="5c376-103">GetErrorInfo function</span></span>
<span data-ttu-id="5c376-104">Ruft Fehlerinformationen aus dem vorherigen Funktionsaufruf ab.</span><span class="sxs-lookup"><span data-stu-id="5c376-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="5c376-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c376-105">Syntax</span></span>  
  
```cpp  
IErrorInfo* GetErrorInfo();
```  

## <a name="return-value"></a><span data-ttu-id="5c376-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5c376-106">Return value</span></span>

<span data-ttu-id="5c376-107">Ein Zeiger auf ein [IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) -Objekt, wenn der Funktions Aufrufvorgang erfolgreich ist, oder, `null` Wenn es fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="5c376-107">An pointer to an [IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5c376-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5c376-108">Remarks</span></span>

<span data-ttu-id="5c376-109">Diese Funktion umschließt einen Aufrufen der [icomthreadinginfo:: GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) -Methode.</span><span class="sxs-lookup"><span data-stu-id="5c376-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="5c376-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5c376-110">Requirements</span></span>  
 <span data-ttu-id="5c376-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c376-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c376-112">**Header:** WMINet_Utils. def</span><span class="sxs-lookup"><span data-stu-id="5c376-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="5c376-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5c376-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c376-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c376-114">See also</span></span>

- [<span data-ttu-id="5c376-115">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="5c376-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
