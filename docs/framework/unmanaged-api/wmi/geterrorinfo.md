---
title: GetErrorInfo-Funktion (Nicht verwaltete API-Referenz)
description: Die GetErrorInfo-Funktion ruft Fehlerinformationen aus dem vorherigen Funktionsaufruf ab.
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
ms.openlocfilehash: 802ee66a5be213ac7a599b193ec6de589773ea17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176811"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="bccb6-103">GetErrorInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="bccb6-103">GetErrorInfo function</span></span>
<span data-ttu-id="bccb6-104">Ruft Fehlerinformationen aus dem vorherigen Funktionsaufruf ab.</span><span class="sxs-lookup"><span data-stu-id="bccb6-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="bccb6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bccb6-105">Syntax</span></span>  
  
```cpp  
IErrorInfo* GetErrorInfo();
```  

## <a name="return-value"></a><span data-ttu-id="bccb6-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bccb6-106">Return value</span></span>

<span data-ttu-id="bccb6-107">Ein Zeiger auf ein [IErrorInfo-Objekt,](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) wenn `null` der Funktionsaufruf erfolgreich ist oder fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="bccb6-107">An pointer to an [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="bccb6-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bccb6-108">Remarks</span></span>

<span data-ttu-id="bccb6-109">Diese Funktion umschließt einen Aufruf der [IComThreadingInfo::GetErrorInfo-Methode.](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype)</span><span class="sxs-lookup"><span data-stu-id="bccb6-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="bccb6-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bccb6-110">Requirements</span></span>  
 <span data-ttu-id="bccb6-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bccb6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bccb6-112">**Kopfzeile:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="bccb6-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="bccb6-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bccb6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bccb6-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bccb6-114">See also</span></span>

- [<span data-ttu-id="bccb6-115">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="bccb6-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
