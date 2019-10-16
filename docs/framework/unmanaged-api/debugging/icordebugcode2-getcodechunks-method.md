---
title: ICorDebugCode2::GetCodeChunks-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d64773aa0d35f2e97232576d145dfcba624812ec
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395529"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="30320-102">ICorDebugCode2::GetCodeChunks-Methode</span><span class="sxs-lookup"><span data-stu-id="30320-102">ICorDebugCode2::GetCodeChunks Method</span></span>

<span data-ttu-id="30320-103">Ruft die Codeabschnitte ab, aus denen dieses Codeobjekt besteht.</span><span class="sxs-lookup"><span data-stu-id="30320-103">Gets the chunks of code that this code object is composed of.</span></span>

## <a name="syntax"></a><span data-ttu-id="30320-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="30320-104">Syntax</span></span>

```cpp
HRESULT GetCodeChunks (
    [in]  ULONG32     cbufSize,
    [out] ULONG32     *pcnumChunks,
    [out, size_is(cbufSize), length_is(*pcnumChunks)]
        CodeChunkInfo chunks[]
);
```

## <a name="parameters"></a><span data-ttu-id="30320-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="30320-105">Parameters</span></span>

`cbufSize`  
<span data-ttu-id="30320-106">in Größe des Arrays "`chunks`".</span><span class="sxs-lookup"><span data-stu-id="30320-106">[in] Size of the `chunks` array.</span></span>

`pcnumChunks`  
<span data-ttu-id="30320-107">vorgenommen Die Anzahl der Blöcke, die im `chunks`-Array zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="30320-107">[out] The number of chunks returned in the `chunks` array.</span></span>

`chunks`  
<span data-ttu-id="30320-108">vorgenommen Ein Array von CodeChunkInfo-Strukturen, von denen jedes einen einzelnen Codeblock darstellt.</span><span class="sxs-lookup"><span data-stu-id="30320-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="30320-109">Wenn der Wert von `cbufSize` 0 (null) ist, kann dieser Parameter NULL sein.</span><span class="sxs-lookup"><span data-stu-id="30320-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>

## <a name="remarks"></a><span data-ttu-id="30320-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="30320-110">Remarks</span></span>

<span data-ttu-id="30320-111">Die Code Blöcke werden nie überlappen, und Sie folgen der Reihenfolge, in der Sie von [ICorDebugCode:: GetCode](icordebugcode-getcode-method.md)verkettet worden wären.</span><span class="sxs-lookup"><span data-stu-id="30320-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="30320-112">Ein MSIL-Code Objekt (Microsoft Intermediate Language) in der .NET Framework Version 2,0 besteht aus einem einzelnen Codeblock.</span><span class="sxs-lookup"><span data-stu-id="30320-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>

## <a name="requirements"></a><span data-ttu-id="30320-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="30320-113">Requirements</span></span>

<span data-ttu-id="30320-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30320-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="30320-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30320-115">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="30320-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30320-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="30320-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30320-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
