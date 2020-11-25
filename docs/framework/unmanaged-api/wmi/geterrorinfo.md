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
ms.openlocfilehash: 5da4eaa459c515689b822e4cb537380245e800e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722764"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="2a6ce-103">GetErrorInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="2a6ce-103">GetErrorInfo function</span></span>

<span data-ttu-id="2a6ce-104">Ruft Fehlerinformationen aus dem vorherigen Funktionsaufruf ab.</span><span class="sxs-lookup"><span data-stu-id="2a6ce-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="2a6ce-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a6ce-105">Syntax</span></span>  
  
```cpp  
IErrorInfo* GetErrorInfo();
```  

## <a name="return-value"></a><span data-ttu-id="2a6ce-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2a6ce-106">Return value</span></span>

<span data-ttu-id="2a6ce-107">Ein Zeiger auf ein [IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) -Objekt, wenn der Funktions Aufrufvorgang erfolgreich ist, oder, `null` Wenn es fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="2a6ce-107">An pointer to an [IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2a6ce-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2a6ce-108">Remarks</span></span>

<span data-ttu-id="2a6ce-109">Diese Funktion umschließt einen Aufrufen der [icomthreadinginfo:: GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) -Methode.</span><span class="sxs-lookup"><span data-stu-id="2a6ce-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="2a6ce-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2a6ce-110">Requirements</span></span>  

 <span data-ttu-id="2a6ce-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a6ce-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a6ce-112">**Header:** WMINet_Utils. def</span><span class="sxs-lookup"><span data-stu-id="2a6ce-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="2a6ce-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2a6ce-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a6ce-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2a6ce-114">See also</span></span>

- [<span data-ttu-id="2a6ce-115">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="2a6ce-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
