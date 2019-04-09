---
title: ICorDebugThread::GetObject-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetObject method [.NET Framework debugging]
ms.assetid: 1590febe-96c2-4046-97db-d81d81d67e01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fa90aff73d94baf2cbf7d01f41710cb2aa10213
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178736"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="fd79f-102">ICorDebugThread::GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="fd79f-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="fd79f-103">Ruft einen Schnittstellenzeiger auf die common Language Runtime (CLR)-Thread ab.</span><span class="sxs-lookup"><span data-stu-id="fd79f-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd79f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd79f-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd79f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fd79f-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="fd79f-106">[out] Ein Zeiger auf die Adresse eines Objekts der ICorDebugValue-Schnittstelle, die den CLR-Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="fd79f-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd79f-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd79f-107">Requirements</span></span>  
 <span data-ttu-id="fd79f-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd79f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd79f-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd79f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd79f-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd79f-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fd79f-111">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="fd79f-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fd79f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd79f-112">See also</span></span>

- <xref:System.Threading.Thread>
