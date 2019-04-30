---
title: NOTIFY_FILTER-Enumeration
ms.date: 03/30/2017
api_name:
- NOTIFY_FILTER
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- NOTIFY_FILTER
helpviewer_keywords:
- NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 63c3ecd0ae0d9e1df62d73eb05b759093583f652
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61915316"
---
# <a name="notifyfilter-enumeration"></a><span data-ttu-id="ac5df-102">NOTIFY_FILTER-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ac5df-102">NOTIFY_FILTER Enumeration</span></span>
<span data-ttu-id="ac5df-103">Identifiziert die Rückrufe für Debugger-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="ac5df-103">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="ac5df-104">Weitere Informationen finden Sie unter den [INotifySource2:: SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="ac5df-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac5df-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac5df-105">Syntax</span></span>  
  
```  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a><span data-ttu-id="ac5df-106">Member</span><span class="sxs-lookup"><span data-stu-id="ac5df-106">Members</span></span>  
  
|<span data-ttu-id="ac5df-107">Member</span><span class="sxs-lookup"><span data-stu-id="ac5df-107">Member</span></span>|<span data-ttu-id="ac5df-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac5df-108">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="ac5df-109">Gibt an, dass die [INotifySink2:: OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) Methode aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ac5df-109">Indicates that the [INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="ac5df-110">Gibt an, dass die [INotifySink2:: OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) Methode aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ac5df-110">Indicates that the [INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="ac5df-111">Gibt an, dass die [INotifySink2:: OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) Methode aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ac5df-111">Indicates that the [INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="ac5df-112">Gibt an, dass die [INotifySink2:: OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) Methode aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ac5df-112">Indicates that the [INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="ac5df-113">Gibt an, dass alle der [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) Methoden aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ac5df-113">Indicates that all of the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="ac5df-114">Aktiviert alle vorhandene und künftige Benachrichtigungen an.</span><span class="sxs-lookup"><span data-stu-id="ac5df-114">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="ac5df-115">Gibt an, dass keine Benachrichtigungsmethoden aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ac5df-115">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ac5df-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ac5df-116">Requirements</span></span>  
 <span data-ttu-id="ac5df-117">**Header:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="ac5df-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac5df-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac5df-118">See also</span></span>

- [<span data-ttu-id="ac5df-119">Diagnosesymbolspeicher-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="ac5df-119">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
