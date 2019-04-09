---
title: INotifyConnection2::RegisterNotifySource-Methode
ms.date: 03/30/2017
api_name:
- INotifyConnection2.RegisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::RegisterNotifySource
helpviewer_keywords:
- INotifyConnection2::RegisterNotifySource method [.NET Framework debugging]
- RegisterNotifySource method [.NET Framework debugging]
ms.assetid: 2632da80-6e4b-4429-8dee-b382745a5f81
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9dac5ae2f0f77c7b6d2dbd7f908f3552823735b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109602"
---
# <a name="inotifyconnection2registernotifysource-method"></a><span data-ttu-id="0ab8e-102">INotifyConnection2::RegisterNotifySource-Methode</span><span class="sxs-lookup"><span data-stu-id="0ab8e-102">INotifyConnection2::RegisterNotifySource Method</span></span>
<span data-ttu-id="0ab8e-103">Installiert eine Quelle für die angegebene Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="0ab8e-103">Installs a specified notification source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ab8e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ab8e-104">Syntax</span></span>  
  
```  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ab8e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ab8e-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="0ab8e-106">[in] Gibt das Objekt, das als Benachrichtigungsquelle für verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0ab8e-106">[in] Specifies the object to be used as the notification source.</span></span>  
  
 `out_ppNotifySink`  
 <span data-ttu-id="0ab8e-107">[out] Erhält das Objekt als den Benachrichtigungsempfänger verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0ab8e-107">[out] Receives the object to be used as the notification sink.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ab8e-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0ab8e-108">Return Value</span></span>  
 <span data-ttu-id="0ab8e-109">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="0ab8e-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ab8e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0ab8e-110">Requirements</span></span>  
 <span data-ttu-id="0ab8e-111">**Header:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="0ab8e-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ab8e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ab8e-112">See also</span></span>

- [<span data-ttu-id="0ab8e-113">INotifyConnection2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ab8e-113">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="0ab8e-114">INotifySource2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ab8e-114">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="0ab8e-115">INotifySink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ab8e-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="0ab8e-116">UnregisterNotifySource-Methode</span><span class="sxs-lookup"><span data-stu-id="0ab8e-116">UnregisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-unregisternotifysource-method.md)
