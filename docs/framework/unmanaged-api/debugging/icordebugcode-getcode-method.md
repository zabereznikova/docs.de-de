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
ms.openlocfilehash: 20eac75a1f1d13b6a30267d56ff66024725e6f33
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674774"
---
# <a name="icordebugcodegetcode-method"></a><span data-ttu-id="d4bb1-102">ICorDebugCode::GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="d4bb1-102">ICorDebugCode::GetCode Method</span></span>

<span data-ttu-id="d4bb1-103">Ruft den gesamten für die Disassembly formatierten Code für die angegebene Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="d4bb1-103">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="d4bb1-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="d4bb1-104">This method has been deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="d4bb1-105">Verwenden Sie stattdessen [ICorDebugCode2:: getcodechunert](icordebugcode2-getcodechunks-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d4bb1-105">Use [ICorDebugCode2::GetCodeChunks](icordebugcode2-getcodechunks-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4bb1-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4bb1-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCode (  
    [in] ULONG32     startOffset,
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4bb1-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="d4bb1-107">Parameters</span></span>  

 `startOffset`  
 <span data-ttu-id="d4bb1-108">in Der Offset des Anfangs der Funktion.</span><span class="sxs-lookup"><span data-stu-id="d4bb1-108">[in] The offset of the beginning of the function.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="d4bb1-109">in Der Offset des Endes der Funktion.</span><span class="sxs-lookup"><span data-stu-id="d4bb1-109">[in] The offset of the end of the function.</span></span>  
  
 `cBufferAlloc`  
 <span data-ttu-id="d4bb1-110">in Die Größe des `buffer` Arrays, in das der Code zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d4bb1-110">[in] The size of the `buffer` array into which the code will be returned.</span></span>  
  
 `buffer`  
 <span data-ttu-id="d4bb1-111">vorgenommen Das Array, in das der Code zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d4bb1-111">[out] The array into which the code will be returned.</span></span>  
  
 `pcBufferSize`  
 <span data-ttu-id="d4bb1-112">vorgenommen Die Anzahl der zurückgegebenen Bytes.</span><span class="sxs-lookup"><span data-stu-id="d4bb1-112">[out] The number of bytes returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4bb1-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d4bb1-113">Remarks</span></span>  

 <span data-ttu-id="d4bb1-114">Wenn der Code der Funktion in mehrere Blöcke aufgeteilt wurde, werden diese in der Reihenfolge der Vergrößerung des systemeigenen Offsets verkettet.</span><span class="sxs-lookup"><span data-stu-id="d4bb1-114">If the function's code has been divided into multiple chunks, they are concatenated in order of increasing native offset.</span></span> <span data-ttu-id="d4bb1-115">Anweisungs Grenzen werden nicht geprüft.</span><span class="sxs-lookup"><span data-stu-id="d4bb1-115">Instruction boundaries are not checked.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4bb1-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d4bb1-116">Requirements</span></span>  

 <span data-ttu-id="d4bb1-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4bb1-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4bb1-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4bb1-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4bb1-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4bb1-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4bb1-120">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="d4bb1-120">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4bb1-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d4bb1-121">See also</span></span>

- [<span data-ttu-id="d4bb1-122">GetCodeChunks-Methode</span><span class="sxs-lookup"><span data-stu-id="d4bb1-122">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
