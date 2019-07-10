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
ms.openlocfilehash: 2a5461cc6a78347cdbe0d0b13f8111cb24c11006
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760049"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="a6ea3-102">ICorDebugInternalFrame::GetFrameType-Methode</span><span class="sxs-lookup"><span data-stu-id="a6ea3-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="a6ea3-103">Ruft den Typ des diesem internen Frames.</span><span class="sxs-lookup"><span data-stu-id="a6ea3-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6ea3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6ea3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6ea3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a6ea3-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="a6ea3-106">[out] Ein Zeiger auf einen Wert der CorDebugInternalFrameType-Enumeration, der den Typ der internen Frames dargestellt, die von diesem angibt `ICorDebugInternalFrame` Objekt.</span><span class="sxs-lookup"><span data-stu-id="a6ea3-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6ea3-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a6ea3-107">Remarks</span></span>  
 <span data-ttu-id="a6ea3-108">Der Typ der internen Frames wird nie STUBFRAME_NONE.</span><span class="sxs-lookup"><span data-stu-id="a6ea3-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="a6ea3-109">Nicht erkannte interne Rahmentypen ignorieren Debugger ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="a6ea3-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6ea3-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a6ea3-110">Requirements</span></span>  
 <span data-ttu-id="a6ea3-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6ea3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6ea3-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6ea3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6ea3-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6ea3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6ea3-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6ea3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
