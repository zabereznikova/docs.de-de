---
title: ICorDebugILFrame::GetIP-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 79b18c6fe15e28b2cec07ef9dfaa06ee295ab42d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="0d3a4-102">ICorDebugILFrame::GetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="0d3a4-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="0d3a4-103">Ruft den Wert des Anweisungszeigers und eine bitweise Kombination-Wert, der beschreibt, wie der Wert des Anweisungszeigers abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="0d3a4-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d3a4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d3a4-104">Syntax</span></span>  
  
```  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d3a4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0d3a4-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="0d3a4-106">[out] Der Wert des Anweisungszeigers.</span><span class="sxs-lookup"><span data-stu-id="0d3a4-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="0d3a4-107">[out] Ein Zeiger auf eine bitweise Kombination der CorDebugMappingResult-Enumerationswerte, die beschreiben, wie der Wert des Anweisungszeigers abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="0d3a4-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d3a4-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0d3a4-108">Remarks</span></span>  
 <span data-ttu-id="0d3a4-109">Der Wert des Anweisungszeigers ist der Stapelrahmen Offset der Funktion Microsoft intermediate Language (MSIL)-Code.</span><span class="sxs-lookup"><span data-stu-id="0d3a4-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="0d3a4-110">Wenn der Stapelrahmen aktiv ist, ist diese Adresse die nächste Anweisung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0d3a4-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="0d3a4-111">Wenn der Stapelrahmen nicht aktiv ist, wird diese Adresse die nächste Anweisung ausführen, wenn der Stapelrahmen erneut aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="0d3a4-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="0d3a4-112">Wenn dieser Rahmen eine just-in-Time (JIT) kompilierten Rahmen ist, wird der Wert des Anweisungszeigers durch Zuordnen rückwärts von den tatsächlichen systemeigenen Anweisungszeiger, daher ist der Wert möglicherweise nur ungefähre bestimmt.</span><span class="sxs-lookup"><span data-stu-id="0d3a4-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d3a4-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0d3a4-113">Requirements</span></span>  
 <span data-ttu-id="0d3a4-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d3a4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d3a4-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d3a4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d3a4-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d3a4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d3a4-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d3a4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
