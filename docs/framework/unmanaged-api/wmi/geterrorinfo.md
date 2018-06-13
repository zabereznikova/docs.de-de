---
title: GetErrorInfo-Funktion (Referenz zur nicht verwalteten API)
description: GetErrorInfo-Funktion ruft die Fehlerinformationen aus dem vorherigen Funktionsaufruf ab.
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
ms.openlocfilehash: ef52a4e503597e08eae407571f02bf63adafc4e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455955"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="5cf95-103">GetErrorInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="5cf95-103">GetErrorInfo function</span></span>
<span data-ttu-id="5cf95-104">Ruft die Fehlerinformationen aus dem vorherigen Funktionsaufruf ab.</span><span class="sxs-lookup"><span data-stu-id="5cf95-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="5cf95-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5cf95-105">Syntax</span></span>  
  
```  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="5cf95-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5cf95-106">Return value</span></span>

<span data-ttu-id="5cf95-107">Ein Zeiger auf ein [IErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms221233(v=vs.85).aspx) -Objekt, wenn der Funktionsaufruf folgt, oder `null` dabei ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5cf95-107">An pointer to an [IErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms221233(v=vs.85).aspx) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5cf95-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5cf95-108">Remarks</span></span>

<span data-ttu-id="5cf95-109">Diese Funktion dient als Wrapper für einen Aufruf der [IComThreadingInfo::GetErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="5cf95-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="5cf95-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5cf95-110">Requirements</span></span>  
 <span data-ttu-id="5cf95-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cf95-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cf95-112">**Header:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="5cf95-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="5cf95-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5cf95-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cf95-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5cf95-114">See also</span></span>  
[<span data-ttu-id="5cf95-115">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="5cf95-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
