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
ms.openlocfilehash: fb198782bb91a8301507fd6cadcffb0378230f0e
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396582"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="d2a12-102">Icordebugvariablehome:: getliverange-Methode</span><span class="sxs-lookup"><span data-stu-id="d2a12-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="d2a12-103">Ruft den systemeigenen Bereich ab, in dem diese Variable Live ist.</span><span class="sxs-lookup"><span data-stu-id="d2a12-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2a12-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2a12-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2a12-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d2a12-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="d2a12-106">vorgenommen Der logische Offset, bei dem die Variable zum ersten Mal Live ist.</span><span class="sxs-lookup"><span data-stu-id="d2a12-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="d2a12-107">vorgenommen Der logische Offset unmittelbar nach dem Punkt, an dem die Variable zuletzt aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="d2a12-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2a12-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d2a12-108">Requirements</span></span>  
 <span data-ttu-id="d2a12-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2a12-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2a12-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2a12-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2a12-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2a12-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2a12-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2a12-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2a12-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2a12-113">See also</span></span>

- [<span data-ttu-id="d2a12-114">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2a12-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
