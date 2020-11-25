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
ms.openlocfilehash: 4d66d09e02b907281f64400b0c605a7b5c44d476
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731045"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="a6027-102">Icordebugvariablehome:: getliverange-Methode</span><span class="sxs-lookup"><span data-stu-id="a6027-102">IcorDebugVariableHome::GetLiveRange Method</span></span>

<span data-ttu-id="a6027-103">Ruft den systemeigenen Bereich ab, in dem diese Variable Live ist.</span><span class="sxs-lookup"><span data-stu-id="a6027-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6027-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6027-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6027-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a6027-105">Parameters</span></span>  

 `pStartOffset`  
 <span data-ttu-id="a6027-106">vorgenommen Der logische Offset, bei dem die Variable zum ersten Mal Live ist.</span><span class="sxs-lookup"><span data-stu-id="a6027-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="a6027-107">vorgenommen Der logische Offset unmittelbar nach dem Punkt, an dem die Variable zuletzt aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="a6027-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6027-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a6027-108">Requirements</span></span>  

 <span data-ttu-id="a6027-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6027-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6027-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6027-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6027-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6027-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6027-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6027-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6027-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a6027-113">See also</span></span>

- [<span data-ttu-id="a6027-114">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a6027-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
