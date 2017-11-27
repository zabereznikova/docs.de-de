---
title: ICorPublish::GetProcess-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublish.GetProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c5fd66fb3ba5eba1b01451b77472a94bc16dfef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="b5771-102">ICorPublish::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="b5771-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="b5771-103">Ruft eine [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) -Instanz, die den Prozess mit dem angegebenen Bezeichner darstellt.</span><span class="sxs-lookup"><span data-stu-id="b5771-103">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5771-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5771-104">Syntax</span></span>  
  
```  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5771-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b5771-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="b5771-106">[in] Der Bezeichner des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="b5771-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="b5771-107">[out] Ein Zeiger auf die Adresse einer `ICorPublishProcess` -Instanz, die den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="b5771-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5771-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b5771-108">Remarks</span></span>  
 <span data-ttu-id="b5771-109">`GetProcess`schlägt fehl, wenn der Prozess ist nicht vorhanden oder ist nicht verwalteten Prozesses, der vom aktuellen Benutzer gedebuggt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b5771-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5771-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b5771-110">Requirements</span></span>  
 <span data-ttu-id="b5771-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5771-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5771-112">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="b5771-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b5771-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5771-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5771-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5771-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5771-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5771-115">See Also</span></span>  
 [<span data-ttu-id="b5771-116">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b5771-116">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
