---
title: ICorPublish::GetProcess-Methode
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 414bc1bbd3578d0707e35fa70fe196b504af9942
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418495"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="41c30-102">ICorPublish::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="41c30-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="41c30-103">Ruft eine [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) -Instanz, die den Prozess mit dem angegebenen Bezeichner darstellt.</span><span class="sxs-lookup"><span data-stu-id="41c30-103">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41c30-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41c30-104">Syntax</span></span>  
  
```  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41c30-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="41c30-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="41c30-106">[in] Der Bezeichner des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="41c30-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="41c30-107">[out] Ein Zeiger auf die Adresse einer `ICorPublishProcess` -Instanz, die den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="41c30-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41c30-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="41c30-108">Remarks</span></span>  
 <span data-ttu-id="41c30-109">`GetProcess` schlägt fehl, wenn der Prozess ist nicht vorhanden oder ist nicht verwalteten Prozesses, der vom aktuellen Benutzer gedebuggt werden kann.</span><span class="sxs-lookup"><span data-stu-id="41c30-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41c30-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="41c30-110">Requirements</span></span>  
 <span data-ttu-id="41c30-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41c30-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41c30-112">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="41c30-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="41c30-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41c30-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41c30-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41c30-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41c30-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41c30-115">See Also</span></span>  
 [<span data-ttu-id="41c30-116">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41c30-116">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
