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
ms.openlocfilehash: a9d28243e9907fcc6320b2e09a49312bf35a70b4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121775"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="e72f2-102">ICorPublish::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="e72f2-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="e72f2-103">Ruft eine [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) -Instanz ab, die den Prozess mit dem angegebenen Bezeichner darstellt.</span><span class="sxs-lookup"><span data-stu-id="e72f2-103">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e72f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e72f2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e72f2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e72f2-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="e72f2-106">in Der Bezeichner des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="e72f2-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="e72f2-107">vorgenommen Ein Zeiger auf die Adresse einer `ICorPublishProcess`-Instanz, die den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="e72f2-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e72f2-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e72f2-108">Remarks</span></span>  
 <span data-ttu-id="e72f2-109">`GetProcess` schlägt fehl, wenn der Prozess nicht vorhanden ist oder kein verwalteter Prozess ist, der vom aktuellen Benutzer debuggt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e72f2-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e72f2-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e72f2-110">Requirements</span></span>  
 <span data-ttu-id="e72f2-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e72f2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e72f2-112">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="e72f2-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="e72f2-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e72f2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e72f2-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e72f2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e72f2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e72f2-115">See also</span></span>

- [<span data-ttu-id="e72f2-116">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e72f2-116">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
