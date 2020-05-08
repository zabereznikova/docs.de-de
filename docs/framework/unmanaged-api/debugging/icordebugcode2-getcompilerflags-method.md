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
ms.openlocfilehash: 734a05d96aed309541708d4e6f80ed61cab85637
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893500"
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="08de1-102">ICorDebugCode2::GetCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="08de1-102">ICorDebugCode2::GetCompilerFlags Method</span></span>

<span data-ttu-id="08de1-103">Ruft die Flags ab, die die Bedingungen angeben, unter denen dieses Codeobjekt JIT-kompiliert (Just-In-Time) oder unter Verwendung des Native Image Generator (Ngen.exe) generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="08de1-103">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>

## <a name="syntax"></a><span data-ttu-id="08de1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08de1-104">Syntax</span></span>

```cpp
HRESULT GetCompilerFlags (
    [out] DWORD *pdwFlags
);
```

## <a name="parameters"></a><span data-ttu-id="08de1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="08de1-105">Parameters</span></span>

`pdwFlags`  
<span data-ttu-id="08de1-106">vorgenommen Ein Zeiger auf einen Wert der [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) -Enumeration, der das Verhalten des JIT-Compilers oder des Native Image-Generators angibt.</span><span class="sxs-lookup"><span data-stu-id="08de1-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>

## <a name="requirements"></a><span data-ttu-id="08de1-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="08de1-107">Requirements</span></span>

<span data-ttu-id="08de1-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08de1-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="08de1-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08de1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="08de1-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08de1-110">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="08de1-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08de1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
