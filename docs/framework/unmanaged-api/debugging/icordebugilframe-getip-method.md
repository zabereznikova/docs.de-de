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
ms.openlocfilehash: 7e1605eede55360e72d65da6744bc1dcce4f107f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130989"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="3d115-102">ICorDebugILFrame::GetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="3d115-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="3d115-103">Ruft den Wert des Anweisungs Zeigers und einen bitweisen Kombinationswert ab, der beschreibt, wie der Wert des Anweisungs Zeigers abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="3d115-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d115-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d115-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d115-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3d115-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="3d115-106">vorgenommen Der Wert des Anweisungs Zeigers.</span><span class="sxs-lookup"><span data-stu-id="3d115-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="3d115-107">vorgenommen Ein Zeiger auf eine bitweise Kombination der cordbugmappingresult-Enumerationswerte, die beschreiben, wie der Wert des Anweisungs Zeigers abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="3d115-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d115-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3d115-108">Remarks</span></span>  
 <span data-ttu-id="3d115-109">Der Wert des Anweisungs Zeigers ist der Offset des Stapel Rahmens im MSIL-Code (Microsoft Intermediate Language) der Funktion.</span><span class="sxs-lookup"><span data-stu-id="3d115-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="3d115-110">Wenn der Stapel Rahmen aktiv ist, ist diese Adresse die nächste Anweisung, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3d115-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="3d115-111">Wenn der Stapel Rahmen nicht aktiv ist, handelt es sich bei dieser Adresse um die nächste Anweisung, die ausgeführt werden soll, wenn der Stapel Rahmen erneut aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="3d115-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="3d115-112">Handelt es sich bei diesem Frame um einen JIT-kompilierten Frame (Just-in-Time), wird der Wert des Anweisungs Zeigers durch die Zuordnung rückwärts aus dem eigentlichen systemeigenen Anweisungs Zeiger bestimmt, sodass der Wert nur ungefähre Werte aufweisen kann.</span><span class="sxs-lookup"><span data-stu-id="3d115-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d115-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3d115-113">Requirements</span></span>  
 <span data-ttu-id="3d115-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d115-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d115-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d115-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d115-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d115-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d115-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d115-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
