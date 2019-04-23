---
title: ICorDebugCode::GetCode-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f396881ef16f63eaf198aec168e5e94ed887698b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228535"
---
# <a name="icordebugcodegetcode-method"></a><span data-ttu-id="0ffcf-102">ICorDebugCode::GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="0ffcf-102">ICorDebugCode::GetCode Method</span></span>
<span data-ttu-id="0ffcf-103">Ruft den gesamten für die Disassembly formatierten Code für die angegebene Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="0ffcf-103">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="0ffcf-104">Diese Methode wurde in .NET Framework, Version 2.0 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="0ffcf-104">This method has been deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="0ffcf-105">Verwendung [ICorDebugCode2:: GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) stattdessen.</span><span class="sxs-lookup"><span data-stu-id="0ffcf-105">Use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ffcf-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ffcf-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="0ffcf-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ffcf-107">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="0ffcf-108">[in] Der Offset vom Beginn der Funktion.</span><span class="sxs-lookup"><span data-stu-id="0ffcf-108">[in] The offset of the beginning of the function.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="0ffcf-109">[in] Der Offset des Endes der Funktion.</span><span class="sxs-lookup"><span data-stu-id="0ffcf-109">[in] The offset of the end of the function.</span></span>  
  
 `cBufferAlloc`  
 <span data-ttu-id="0ffcf-110">[in] Die Größe der `buffer` Arrays, in dem der Code zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0ffcf-110">[in] The size of the `buffer` array into which the code will be returned.</span></span>  
  
 `buffer`  
 <span data-ttu-id="0ffcf-111">[out] Das Array, in dem der Code zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0ffcf-111">[out] The array into which the code will be returned.</span></span>  
  
 `pcBufferSize`  
 <span data-ttu-id="0ffcf-112">[out] Die Anzahl der Bytes, die zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="0ffcf-112">[out] The number of bytes returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ffcf-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ffcf-113">Remarks</span></span>  
 <span data-ttu-id="0ffcf-114">Wenn Sie den Code der Funktion in mehrere Blöcke aufgeteilt wurde, werden sie in der Reihenfolge zunehmender beim nativen Offset verkettet.</span><span class="sxs-lookup"><span data-stu-id="0ffcf-114">If the function's code has been divided into multiple chunks, they are concatenated in order of increasing native offset.</span></span> <span data-ttu-id="0ffcf-115">Anweisungsgrenzen werden nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="0ffcf-115">Instruction boundaries are not checked.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ffcf-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0ffcf-116">Requirements</span></span>  
 <span data-ttu-id="0ffcf-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ffcf-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ffcf-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ffcf-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ffcf-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ffcf-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ffcf-120">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="0ffcf-120">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ffcf-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ffcf-121">See also</span></span>

- [<span data-ttu-id="0ffcf-122">GetCodeChunks-Methode</span><span class="sxs-lookup"><span data-stu-id="0ffcf-122">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
