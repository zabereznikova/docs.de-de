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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4d7eca3c2825707c9190436377bba7e4bb0d5447
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757975"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="c9815-102">ICorDebugILFrame::GetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="c9815-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="c9815-103">Ruft den Wert des Anweisungszeigers und eine bitweise Kombination-Wert, der beschreibt, wie der Wert des Anweisungszeigers abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="c9815-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9815-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9815-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9815-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c9815-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="c9815-106">[out] Der Wert des Anweisungszeigers.</span><span class="sxs-lookup"><span data-stu-id="c9815-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="c9815-107">[out] Ein Zeiger auf eine bitweise Kombination der CorDebugMappingResult-Enumerationswerte, die beschreiben, wie der Wert des Anweisungszeigers abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="c9815-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9815-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c9815-108">Remarks</span></span>  
 <span data-ttu-id="c9815-109">Der Wert des Anweisungszeigers wird der Stapelrahmen-Offset in der Microsoft intermediate Language (MSIL) Funktionscode.</span><span class="sxs-lookup"><span data-stu-id="c9815-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="c9815-110">Wenn der Stapelrahmen aktiv ist, ist diese Adresse die nächste Anweisung ausführen.</span><span class="sxs-lookup"><span data-stu-id="c9815-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="c9815-111">Wenn der Stapelrahmen nicht aktiv ist, ist diese Adresse die nächste Anweisung ausgeführt werden, wenn der Stapelrahmen erneut aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="c9815-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="c9815-112">Wenn dieser Rahmen eine just-in-Time (JIT) kompilierten Rahmen ist, wird der Wert des Anweisungszeigers Zuordnung rückwärts von den tatsächlichen systemeigenen Anweisungszeiger, daher der Wert möglicherweise nur ungefähr ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="c9815-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9815-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c9815-113">Requirements</span></span>  
 <span data-ttu-id="c9815-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9815-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9815-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9815-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9815-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9815-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9815-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9815-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
