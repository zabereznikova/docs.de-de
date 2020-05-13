---
title: ICorDebugModule2::ResolveAssembly-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ResolveAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ResolveAssembly
helpviewer_keywords:
- ICorDebugModule2::ResolveAssembly method [.NET Framework debugging]
- ResolveAssembly method [.NET Framework debugging]
ms.assetid: ddf9085c-7161-44bd-9609-cd2732b9009f
topic_type:
- apiref
ms.openlocfilehash: e64e39d10d20f63430ffe9d2c4df8643e286a677
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210032"
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="bfb92-102">ICorDebugModule2::ResolveAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="bfb92-102">ICorDebugModule2::ResolveAssembly Method</span></span>

<span data-ttu-id="bfb92-103">Löst die Assembly auf, auf die vom angegebenen Metadatentoken verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="bfb92-103">Resolves the assembly referenced by the specified metadata token.</span></span>

## <a name="syntax"></a><span data-ttu-id="bfb92-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bfb92-104">Syntax</span></span>

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a><span data-ttu-id="bfb92-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bfb92-105">Parameters</span></span>

`tkAssemblyRef`\
<span data-ttu-id="bfb92-106">in Ein- `mdToken` Wert, der auf die Assembly verweist.</span><span class="sxs-lookup"><span data-stu-id="bfb92-106">[in] An `mdToken` value that references the assembly.</span></span>

`ppAssembly`\
<span data-ttu-id="bfb92-107">vorgenommen Ein Zeiger auf die Adresse eines ICorDebug-Objekts, das die Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="bfb92-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="bfb92-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bfb92-108">Remarks</span></span>

<span data-ttu-id="bfb92-109">Wenn die Assembly nicht bereits geladen ist `ResolveAssembly` , wenn aufgerufen wird, wird ein HRESULT-Wert von CORDBG_E_CANNOT_RESOLVE_ASSEMBLY zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bfb92-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="bfb92-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bfb92-110">Requirements</span></span>

<span data-ttu-id="bfb92-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfb92-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="bfb92-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bfb92-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="bfb92-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfb92-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="bfb92-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfb92-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
