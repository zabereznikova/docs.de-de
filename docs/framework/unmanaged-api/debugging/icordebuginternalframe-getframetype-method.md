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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a0b6f0550bad534379b562c3df9da9ab917f5270
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493036"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="85723-102">ICorDebugInternalFrame::GetFrameType-Methode</span><span class="sxs-lookup"><span data-stu-id="85723-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="85723-103">Ruft den Typ des diesem internen Frames.</span><span class="sxs-lookup"><span data-stu-id="85723-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85723-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="85723-104">Syntax</span></span>  
  
```  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85723-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="85723-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="85723-106">[out] Ein Zeiger auf einen Wert der CorDebugInternalFrameType-Enumeration, der den Typ der internen Frames dargestellt, die von diesem angibt `ICorDebugInternalFrame` Objekt.</span><span class="sxs-lookup"><span data-stu-id="85723-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85723-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="85723-107">Remarks</span></span>  
 <span data-ttu-id="85723-108">Der Typ der internen Frames wird nie STUBFRAME_NONE.</span><span class="sxs-lookup"><span data-stu-id="85723-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="85723-109">Nicht erkannte interne Rahmentypen ignorieren Debugger ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="85723-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85723-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="85723-110">Requirements</span></span>  
 <span data-ttu-id="85723-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85723-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85723-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85723-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85723-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85723-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85723-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85723-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
