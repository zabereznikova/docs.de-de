---
title: ICorDebugInternalFrame::GetFrameType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame.GetFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame::GetFrameType
helpviewer_keywords:
- GetFrameType method [.NET Framework debugging]
- ICorDebugInternalFrame::GetFrameType method [.NET Framework debugging]
ms.assetid: da278a29-dc2e-4bf7-96ce-801bdc4d7025
topic_type:
- apiref
ms.openlocfilehash: b7a33fd6e2178e0e9188b81f516b231702fb6460
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122717"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="d30f5-102">ICorDebugInternalFrame::GetFrameType-Methode</span><span class="sxs-lookup"><span data-stu-id="d30f5-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="d30f5-103">Ruft den Typ dieses internen Frames ab.</span><span class="sxs-lookup"><span data-stu-id="d30f5-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d30f5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d30f5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d30f5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d30f5-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="d30f5-106">vorgenommen Ein Zeiger auf einen Wert der CorDebugInternalFrameType-Enumeration, der den Typ des internen Frames angibt, der von diesem `ICorDebugInternalFrame` Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d30f5-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d30f5-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d30f5-107">Remarks</span></span>  
 <span data-ttu-id="d30f5-108">Der interne Frame-Typ wird nie STUBFRAME_NONE sein.</span><span class="sxs-lookup"><span data-stu-id="d30f5-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="d30f5-109">-Buggers sollten nicht erkannte interne Frame Typen ordnungsgemäß ignorieren.</span><span class="sxs-lookup"><span data-stu-id="d30f5-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d30f5-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d30f5-110">Requirements</span></span>  
 <span data-ttu-id="d30f5-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d30f5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d30f5-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d30f5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d30f5-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d30f5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d30f5-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d30f5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
