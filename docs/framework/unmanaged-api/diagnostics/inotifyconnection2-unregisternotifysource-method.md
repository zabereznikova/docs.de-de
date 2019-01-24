---
title: INotifyConnection2::UnregisterNotifySource-Methode
ms.date: 03/30/2017
api_name:
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e5380ed63a362b73b0684ef07b638117751ca80
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712011"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="92c0e-102">INotifyConnection2::UnregisterNotifySource-Methode</span><span class="sxs-lookup"><span data-stu-id="92c0e-102">INotifyConnection2::UnregisterNotifySource Method</span></span>
<span data-ttu-id="92c0e-103">Entfernt eine angegebene Benachrichtigung-Quellobjekt aus der Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="92c0e-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92c0e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="92c0e-104">Syntax</span></span>  
  
```  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92c0e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="92c0e-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="92c0e-106">[in] Benachrichtigungsobjekt, das nicht aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="92c0e-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92c0e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="92c0e-107">Return Value</span></span>  
 <span data-ttu-id="92c0e-108">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="92c0e-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92c0e-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="92c0e-109">Requirements</span></span>  
 <span data-ttu-id="92c0e-110">**Header:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="92c0e-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92c0e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92c0e-111">See also</span></span>
- [<span data-ttu-id="92c0e-112">INotifyConnection2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92c0e-112">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="92c0e-113">INotifySource2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92c0e-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="92c0e-114">INotifySink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92c0e-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="92c0e-115">RegisterNotifySource-Methode</span><span class="sxs-lookup"><span data-stu-id="92c0e-115">RegisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
