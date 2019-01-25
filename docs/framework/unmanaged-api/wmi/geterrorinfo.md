---
title: GetErrorInfo-Funktion (Referenz zur nicht verwalteten API)
description: Die GetErrorInfo-Funktion ruft die Fehlerinformationen aus dem vorherigen Funktionsaufruf ab.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b27dae07697943c696dc3419f2414701feb1220
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577671"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="d6124-103">GetErrorInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="d6124-103">GetErrorInfo function</span></span>
<span data-ttu-id="d6124-104">Ruft Fehlerinformationen aus dem vorherigen Funktionsaufruf ab.</span><span class="sxs-lookup"><span data-stu-id="d6124-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="d6124-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6124-105">Syntax</span></span>  
  
```  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="d6124-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d6124-106">Return value</span></span>

<span data-ttu-id="d6124-107">Ein Zeiger auf ein [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) -Objekt, wenn der Aufruf der Funktion erfolgreich ist, oder `null` bei einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="d6124-107">An pointer to an [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d6124-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d6124-108">Remarks</span></span>

<span data-ttu-id="d6124-109">Diese Funktion umschließt einen Aufruf der [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) Methode.</span><span class="sxs-lookup"><span data-stu-id="d6124-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="d6124-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d6124-110">Requirements</span></span>  
 <span data-ttu-id="d6124-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6124-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6124-112">**Header:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="d6124-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="d6124-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d6124-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6124-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6124-114">See also</span></span>
- [<span data-ttu-id="d6124-115">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="d6124-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
