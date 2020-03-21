---
title: ICorDebugILFrame::GetIP-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::GetIP method [.NET Framework debugging]
ms.assetid: 18217ba1-1776-4297-a3b9-f77e64b0fead
topic_type:
- apiref
ms.openlocfilehash: f30516a8f59b90de9b4c052d92a8c88575ace3c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178825"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="afa52-102">ICorDebugILFrame::GetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="afa52-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="afa52-103">Ruft den Wert des Anweisungszeigers und einen bitweisen Kombinationswert ab, der beschreibt, wie der Wert des Anweisungszeigers abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="afa52-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afa52-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="afa52-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="afa52-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="afa52-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="afa52-106">[out] Der Wert des Anweisungszeigers.</span><span class="sxs-lookup"><span data-stu-id="afa52-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="afa52-107">[out] Ein Zeiger auf eine bitweise Kombination der CorDebugMappingResult-Enumerationswerte, die beschreiben, wie der Wert des Anweisungszeigers abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="afa52-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="afa52-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="afa52-108">Remarks</span></span>  
 <span data-ttu-id="afa52-109">Der Wert des Anweisungszeigers ist der Offset des Stapelrahmens in den MSIL-Code (Microsoft Intermediate Language) der Funktion.</span><span class="sxs-lookup"><span data-stu-id="afa52-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="afa52-110">Wenn der Stapelrahmen aktiv ist, ist diese Adresse die nächste auszuführende Anweisung.</span><span class="sxs-lookup"><span data-stu-id="afa52-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="afa52-111">Wenn der Stapelrahmen nicht aktiv ist, ist diese Adresse die nächste Anweisung, die ausgeführt werden muss, wenn der Stapelrahmen erneut aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="afa52-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="afa52-112">Wenn es sich bei diesem Frame um einen Just-in-Time-Kompilierten Frame (JIT) handelt, wird der Wert des Anweisungszeigers durch Rückwärtszuordnung vom tatsächlichen systemeigenen Anweisungszeiger bestimmt, sodass der Wert nur annähernd sein kann.</span><span class="sxs-lookup"><span data-stu-id="afa52-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afa52-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="afa52-113">Requirements</span></span>  
 <span data-ttu-id="afa52-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afa52-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afa52-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="afa52-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="afa52-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="afa52-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afa52-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afa52-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
