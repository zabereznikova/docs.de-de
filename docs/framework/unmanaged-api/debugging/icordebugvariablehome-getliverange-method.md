---
title: 'Icordebugvariablehome:: getliverange-Methode'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
ms.openlocfilehash: 28e41106ffcaf1ed2ed87166e641bb5e5f447e47
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791019"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="2d87e-102">Icordebugvariablehome:: getliverange-Methode</span><span class="sxs-lookup"><span data-stu-id="2d87e-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="2d87e-103">Ruft den systemeigenen Bereich ab, in dem diese Variable Live ist.</span><span class="sxs-lookup"><span data-stu-id="2d87e-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d87e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d87e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d87e-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="2d87e-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="2d87e-106">vorgenommen Der logische Offset, bei dem die Variable zum ersten Mal Live ist.</span><span class="sxs-lookup"><span data-stu-id="2d87e-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="2d87e-107">vorgenommen Der logische Offset unmittelbar nach dem Punkt, an dem die Variable zuletzt aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="2d87e-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d87e-108">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2d87e-108">Requirements</span></span>  
 <span data-ttu-id="2d87e-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d87e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d87e-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d87e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d87e-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d87e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d87e-112">**.NET Framework Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d87e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d87e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d87e-113">See also</span></span>

- [<span data-ttu-id="2d87e-114">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d87e-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
