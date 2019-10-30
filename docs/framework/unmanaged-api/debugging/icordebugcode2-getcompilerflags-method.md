---
title: ICorDebugCode2::GetCompilerFlags-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCompilerFlags
helpviewer_keywords:
- GetCompilerFlags method [.NET Framework debugging]
- ICorDebugCode2::GetCompilerFlags method [.NET Framework debugging]
ms.assetid: 532e9dfd-d114-4c75-b952-1accce102643
topic_type:
- apiref
ms.openlocfilehash: d948fda048e724ad11c59bf7d4776ee2ca6c8d58
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125555"
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="82669-102">ICorDebugCode2::GetCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="82669-102">ICorDebugCode2::GetCompilerFlags Method</span></span>

<span data-ttu-id="82669-103">Ruft die Flags ab, die die Bedingungen angeben, unter denen dieses Codeobjekt JIT-kompiliert (Just-In-Time) oder unter Verwendung des Native Image Generator (Ngen.exe) generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="82669-103">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>

## <a name="syntax"></a><span data-ttu-id="82669-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="82669-104">Syntax</span></span>

```cpp
HRESULT GetCompilerFlags (
    [out] DWORD *pdwFlags
);
```

## <a name="parameters"></a><span data-ttu-id="82669-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="82669-105">Parameters</span></span>

`pdwFlags`  
<span data-ttu-id="82669-106">vorgenommen Ein Zeiger auf einen Wert der [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) -Enumeration, der das Verhalten des JIT-Compilers oder des Native Image-Generators angibt.</span><span class="sxs-lookup"><span data-stu-id="82669-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>

## <a name="requirements"></a><span data-ttu-id="82669-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="82669-107">Requirements</span></span>

<span data-ttu-id="82669-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82669-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="82669-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82669-109">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="82669-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82669-110">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="82669-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82669-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
