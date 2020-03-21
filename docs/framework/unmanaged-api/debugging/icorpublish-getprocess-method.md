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
ms.openlocfilehash: 46f047dbec7ff008873540806b76ffe7085086b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178419"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="102c9-102">ICorPublish::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="102c9-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="102c9-103">Ruft eine [ICorPublishProcess-Instanz](icorpublishprocess-interface.md) ab, die den Prozess mit dem angegebenen Bezeichner darstellt.</span><span class="sxs-lookup"><span data-stu-id="102c9-103">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="102c9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="102c9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="102c9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="102c9-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="102c9-106">[in] Der Bezeichner des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="102c9-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="102c9-107">[out] Ein Zeiger auf die `ICorPublishProcess` Adresse einer Instanz, die den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="102c9-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="102c9-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="102c9-108">Remarks</span></span>  
 <span data-ttu-id="102c9-109">`GetProcess`schlägt fehl, wenn der Prozess nicht vorhanden ist oder kein verwalteter Prozess ist, der vom aktuellen Benutzer gedebuggt werden kann.</span><span class="sxs-lookup"><span data-stu-id="102c9-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="102c9-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="102c9-110">Requirements</span></span>  
 <span data-ttu-id="102c9-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="102c9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="102c9-112">**Kopfzeile:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="102c9-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="102c9-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="102c9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="102c9-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="102c9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="102c9-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="102c9-115">See also</span></span>

- [<span data-ttu-id="102c9-116">ICorPublish-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="102c9-116">ICorPublish Interface</span></span>](icorpublish-interface.md)
