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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd899422287d34407778f67e5b4dfd2f33ffd00c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994824"
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="d70ef-102">ICorDebugModule2::ResolveAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="d70ef-102">ICorDebugModule2::ResolveAssembly Method</span></span>

<span data-ttu-id="d70ef-103">Löst die Assembly, die vom angegebenen Metadatentoken verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d70ef-103">Resolves the assembly referenced by the specified metadata token.</span></span>

## <a name="syntax"></a><span data-ttu-id="d70ef-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d70ef-104">Syntax</span></span>

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a><span data-ttu-id="d70ef-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d70ef-105">Parameters</span></span>

`tkAssemblyRef`\
<span data-ttu-id="d70ef-106">[in] Ein `mdToken` -Wert, der die Assembly verweist.</span><span class="sxs-lookup"><span data-stu-id="d70ef-106">[in] An `mdToken` value that references the assembly.</span></span>

`ppAssembly`\
<span data-ttu-id="d70ef-107">[out] Ein Zeiger auf die Adresse eines ICorDebugAssembly-Objekts, das die Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="d70ef-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="d70ef-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d70ef-108">Remarks</span></span>

<span data-ttu-id="d70ef-109">Wenn die Assembly bei noch nicht geladen ist `ResolveAssembly` aufgerufen wird, wird ein HRESULT CORDBG_E_CANNOT_RESOLVE_ASSEMBLY Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d70ef-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="d70ef-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d70ef-110">Requirements</span></span>

<span data-ttu-id="d70ef-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d70ef-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="d70ef-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d70ef-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="d70ef-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d70ef-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="d70ef-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d70ef-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
