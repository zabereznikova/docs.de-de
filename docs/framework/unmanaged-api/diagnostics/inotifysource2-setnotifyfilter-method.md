---
title: INotifySource2::SetNotifyFilter-Methode
ms.date: 03/30/2017
api_name:
- INotifySource2.SetNotifyFilter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySource2::SetNotifyFilter
helpviewer_keywords:
- INotifySource2::SetNotifyFilter method [.NET Framework debugging]
- SetNotifyFilter method [.NET Framework debugging]
ms.assetid: 6351fc92-b126-4af6-9bf3-0a8ce92845fc
topic_type:
- apiref
ms.openlocfilehash: 554756bdda6e7167b013e7114e647f952cd1069d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435952"
---
# <a name="inotifysource2setnotifyfilter-method"></a><span data-ttu-id="680d5-102">INotifySource2::SetNotifyFilter-Methode</span><span class="sxs-lookup"><span data-stu-id="680d5-102">INotifySource2::SetNotifyFilter Method</span></span>
<span data-ttu-id="680d5-103">Weist einen Benachrichtigungs Filter zur Verwendung mit dieser Quelle zu.</span><span class="sxs-lookup"><span data-stu-id="680d5-103">Assigns a notification filter for use with this source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="680d5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="680d5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="680d5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="680d5-105">Parameters</span></span>  
 `in_NotifyFilter`  
 <span data-ttu-id="680d5-106">in Eine bitweise Kombination der [NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md) Enumerationswerte, die Rückrufe für die Debugger-API identifizieren.</span><span class="sxs-lookup"><span data-stu-id="680d5-106">[in] A bitwise combination of the [NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md) enumeration values that identify callbacks for the debugger API.</span></span>  
  
 `in_pUserThreadFilter`  
 <span data-ttu-id="680d5-107">in Ein Zeiger auf eine [USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md) -Struktur, die Threads für die Debugger-API identifiziert.</span><span class="sxs-lookup"><span data-stu-id="680d5-107">[in] A pointer to a [USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md) structure that identifies threads for the debugger API.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="680d5-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="680d5-108">Return Value</span></span>  
 <span data-ttu-id="680d5-109">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="680d5-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="680d5-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="680d5-110">Requirements</span></span>  
 <span data-ttu-id="680d5-111">**Header:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="680d5-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="680d5-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="680d5-112">See also</span></span>

- [<span data-ttu-id="680d5-113">INotifySource2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="680d5-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="680d5-114">INotifyConnection2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="680d5-114">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="680d5-115">INotifySink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="680d5-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
