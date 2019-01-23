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
ms.openlocfilehash: 4a188963273555e8b93b68c168260fd619136c00
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544535"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="01442-102">ICorDebugThread::GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="01442-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="01442-103">Ruft einen Schnittstellenzeiger auf die common Language Runtime (CLR)-Thread ab.</span><span class="sxs-lookup"><span data-stu-id="01442-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01442-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="01442-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01442-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="01442-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="01442-106">[out] Ein Zeiger auf die Adresse eines Objekts der ICorDebugValue-Schnittstelle, die den CLR-Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="01442-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01442-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="01442-107">Requirements</span></span>  
 <span data-ttu-id="01442-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01442-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01442-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01442-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01442-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01442-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01442-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01442-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01442-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01442-112">See also</span></span>
- <xref:System.Threading.Thread>
