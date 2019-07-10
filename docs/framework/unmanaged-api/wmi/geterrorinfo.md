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
ms.openlocfilehash: e33a18487da420eb3b317bb70e0ac9e68b4b8ad6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746540"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="f79f1-103">GetErrorInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="f79f1-103">GetErrorInfo function</span></span>
<span data-ttu-id="f79f1-104">Ruft Fehlerinformationen aus dem vorherigen Funktionsaufruf ab.</span><span class="sxs-lookup"><span data-stu-id="f79f1-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f79f1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f79f1-105">Syntax</span></span>  
  
```cpp  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="f79f1-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f79f1-106">Return value</span></span>

<span data-ttu-id="f79f1-107">Ein Zeiger auf ein [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) -Objekt, wenn der Aufruf der Funktion erfolgreich ist, oder `null` bei einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="f79f1-107">An pointer to an [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f79f1-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f79f1-108">Remarks</span></span>

<span data-ttu-id="f79f1-109">Diese Funktion umschließt einen Aufruf der [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) Methode.</span><span class="sxs-lookup"><span data-stu-id="f79f1-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f79f1-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f79f1-110">Requirements</span></span>  
 <span data-ttu-id="f79f1-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f79f1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f79f1-112">**Header:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="f79f1-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="f79f1-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f79f1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f79f1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f79f1-114">See also</span></span>

- [<span data-ttu-id="f79f1-115">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="f79f1-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
