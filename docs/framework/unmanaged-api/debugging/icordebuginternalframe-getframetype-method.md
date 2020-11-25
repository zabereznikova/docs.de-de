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
ms.openlocfilehash: c675ba4b56cecd1990184cd2f0e805250c3dfeb7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724883"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="77fc0-102">ICorDebugInternalFrame::GetFrameType-Methode</span><span class="sxs-lookup"><span data-stu-id="77fc0-102">ICorDebugInternalFrame::GetFrameType Method</span></span>

<span data-ttu-id="77fc0-103">Ruft den Typ dieses internen Frames ab.</span><span class="sxs-lookup"><span data-stu-id="77fc0-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77fc0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="77fc0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77fc0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="77fc0-105">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="77fc0-106">vorgenommen Ein Zeiger auf einen Wert der CorDebugInternalFrameType-Enumeration, der den Typ des internen Frames angibt, der durch dieses-Objekt dargestellt wird `ICorDebugInternalFrame` .</span><span class="sxs-lookup"><span data-stu-id="77fc0-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77fc0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="77fc0-107">Remarks</span></span>  

 <span data-ttu-id="77fc0-108">Der interne Rahmentyp wird nie STUBFRAME_NONE.</span><span class="sxs-lookup"><span data-stu-id="77fc0-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="77fc0-109">-Buggers sollten nicht erkannte interne Frame Typen ordnungsgemäß ignorieren.</span><span class="sxs-lookup"><span data-stu-id="77fc0-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77fc0-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="77fc0-110">Requirements</span></span>  

 <span data-ttu-id="77fc0-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77fc0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77fc0-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77fc0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77fc0-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77fc0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77fc0-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77fc0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
