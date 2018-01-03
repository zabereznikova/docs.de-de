---
title: ICorDebugCode::GetCode-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f906fddf8073a00d2a3741613aae537b8604af67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcodegetcode-method"></a><span data-ttu-id="19a9d-102">ICorDebugCode::GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="19a9d-102">ICorDebugCode::GetCode Method</span></span>
<span data-ttu-id="19a9d-103">Ruft den gesamten für die Disassembly formatierten Code für die angegebene Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="19a9d-103">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="19a9d-104">Diese Methode ist in .NET Framework, Version 2.0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="19a9d-104">This method has been deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="19a9d-105">Verwendung [ICorDebugCode2:: GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) stattdessen.</span><span class="sxs-lookup"><span data-stu-id="19a9d-105">Use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19a9d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="19a9d-106">Syntax</span></span>  
  
```  
HRESULT GetCode (  
    [in] ULONG32     startOffset,   
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19a9d-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="19a9d-107">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="19a9d-108">[in] Der Offset vom Beginn der Funktion.</span><span class="sxs-lookup"><span data-stu-id="19a9d-108">[in] The offset of the beginning of the function.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="19a9d-109">[in] Der Offset des Endes der Funktion.</span><span class="sxs-lookup"><span data-stu-id="19a9d-109">[in] The offset of the end of the function.</span></span>  
  
 `cBufferAlloc`  
 <span data-ttu-id="19a9d-110">[in] Die Größe der `buffer` Arrays, in dem der Code zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="19a9d-110">[in] The size of the `buffer` array into which the code will be returned.</span></span>  
  
 `buffer`  
 <span data-ttu-id="19a9d-111">[out] Das Array, in dem der Code zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="19a9d-111">[out] The array into which the code will be returned.</span></span>  
  
 `pcBufferSize`  
 <span data-ttu-id="19a9d-112">[out] Die Anzahl der Bytes, die zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="19a9d-112">[out] The number of bytes returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19a9d-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="19a9d-113">Remarks</span></span>  
 <span data-ttu-id="19a9d-114">Wenn der Code der Funktion in mehrere Blöcke aufgeteilt ist, werden sie in aufsteigender Reihenfolge des systemeigenen Offsets verkettet.</span><span class="sxs-lookup"><span data-stu-id="19a9d-114">If the function's code has been divided into multiple chunks, they are concatenated in order of increasing native offset.</span></span> <span data-ttu-id="19a9d-115">Anweisungsgrenzen werden nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="19a9d-115">Instruction boundaries are not checked.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19a9d-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="19a9d-116">Requirements</span></span>  
 <span data-ttu-id="19a9d-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19a9d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19a9d-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19a9d-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19a9d-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19a9d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19a9d-120">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="19a9d-120">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19a9d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19a9d-121">See Also</span></span>  
 [<span data-ttu-id="19a9d-122">GetCodeChunks-Methode</span><span class="sxs-lookup"><span data-stu-id="19a9d-122">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)  
 
