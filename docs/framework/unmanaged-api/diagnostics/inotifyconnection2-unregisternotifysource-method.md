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
ms.openlocfilehash: c4b4f90f918c872f3227ac22f4cccadcbf3194a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425479"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="a60c6-102">INotifyConnection2::UnregisterNotifySource-Methode</span><span class="sxs-lookup"><span data-stu-id="a60c6-102">INotifyConnection2::UnregisterNotifySource Method</span></span>
<span data-ttu-id="a60c6-103">Entfernt eine angegebene Benachrichtigung Quellobjekt, das von der Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="a60c6-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a60c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a60c6-104">Syntax</span></span>  
  
```  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a60c6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a60c6-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="a60c6-106">[in] Benachrichtigungsobjekt, das nicht aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="a60c6-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a60c6-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a60c6-107">Return Value</span></span>  
 <span data-ttu-id="a60c6-108">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="a60c6-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a60c6-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a60c6-109">Requirements</span></span>  
 <span data-ttu-id="a60c6-110">**Header:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="a60c6-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a60c6-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a60c6-111">See Also</span></span>  
 [<span data-ttu-id="a60c6-112">INotifyConnection2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a60c6-112">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 [<span data-ttu-id="a60c6-113">INotifySource2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a60c6-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="a60c6-114">INotifySink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a60c6-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="a60c6-115">RegisterNotifySource-Methode</span><span class="sxs-lookup"><span data-stu-id="a60c6-115">RegisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
