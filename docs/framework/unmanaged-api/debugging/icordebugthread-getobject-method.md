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
ms.openlocfilehash: 2c13ead228296525b57245be8b3bdbcdf38ae173
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728003"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="1d3ff-102">ICorDebugThread::GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="1d3ff-102">ICorDebugThread::GetObject Method</span></span>

<span data-ttu-id="1d3ff-103">Ruft einen Schnittstellen Zeiger auf den Common Language Runtime (CLR)-Thread ab.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d3ff-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d3ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d3ff-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1d3ff-105">Parameters</span></span>  

 `ppObject`  
 <span data-ttu-id="1d3ff-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugValue-Schnittstellen Objekts, das den CLR-Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d3ff-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1d3ff-107">Requirements</span></span>  

 <span data-ttu-id="1d3ff-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d3ff-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d3ff-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d3ff-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d3ff-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d3ff-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d3ff-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d3ff-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d3ff-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1d3ff-112">See also</span></span>

- <xref:System.Threading.Thread>
