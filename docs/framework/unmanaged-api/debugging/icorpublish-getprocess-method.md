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
ms.openlocfilehash: 2cd2238ac67713564922be440ce64a2ebc4bbf44
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396334"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="1f78b-102">ICorPublish::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="1f78b-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="1f78b-103">Ruft eine [ICorPublishProcess](icorpublishprocess-interface.md) -Instanz ab, die den Prozess mit dem angegebenen Bezeichner darstellt.</span><span class="sxs-lookup"><span data-stu-id="1f78b-103">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f78b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1f78b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f78b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1f78b-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="1f78b-106">in Der Bezeichner des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="1f78b-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="1f78b-107">vorgenommen Ein Zeiger auf die Adresse einer- `ICorPublishProcess` Instanz, die den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="1f78b-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f78b-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1f78b-108">Remarks</span></span>  
 <span data-ttu-id="1f78b-109">`GetProcess`schlägt fehl, wenn der Prozess nicht vorhanden ist, oder es handelt sich nicht um einen verwalteten Prozess, der vom aktuellen Benutzer debuggt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1f78b-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f78b-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1f78b-110">Requirements</span></span>  
 <span data-ttu-id="1f78b-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f78b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f78b-112">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="1f78b-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1f78b-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f78b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f78b-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f78b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f78b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f78b-115">See also</span></span>

- [<span data-ttu-id="1f78b-116">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1f78b-116">ICorPublish Interface</span></span>](icorpublish-interface.md)
