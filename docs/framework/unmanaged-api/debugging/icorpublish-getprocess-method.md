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
ms.openlocfilehash: 021068caa8f1ad2c64e5ca3d18ea25dc827563a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085002"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="674a4-102">ICorPublish::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="674a4-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="674a4-103">Ruft eine [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) -Instanz, die den Prozess mit dem angegebenen Bezeichner darstellt.</span><span class="sxs-lookup"><span data-stu-id="674a4-103">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="674a4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="674a4-104">Syntax</span></span>  
  
```  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="674a4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="674a4-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="674a4-106">[in] Der Bezeichner des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="674a4-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="674a4-107">[out] Ein Zeiger auf die Adresse einer `ICorPublishProcess` -Instanz, die den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="674a4-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="674a4-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="674a4-108">Remarks</span></span>  
 `GetProcess` <span data-ttu-id="674a4-109">schlägt fehl, wenn der Prozess ist nicht vorhanden oder wird nicht von einem verwalteten Prozess, der vom aktuellen Benutzer gedebuggt werden kann.</span><span class="sxs-lookup"><span data-stu-id="674a4-109">fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="674a4-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="674a4-110">Requirements</span></span>  
 <span data-ttu-id="674a4-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="674a4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="674a4-112">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="674a4-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="674a4-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="674a4-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="674a4-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="674a4-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="674a4-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="674a4-115">See also</span></span>

- [<span data-ttu-id="674a4-116">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="674a4-116">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
