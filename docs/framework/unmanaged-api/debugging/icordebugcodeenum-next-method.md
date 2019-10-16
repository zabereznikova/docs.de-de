---
title: ICorDebugCodeEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac3fc157543f2990c7c9f9917140b35f8948108e
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395477"
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="2c4f2-102">ICorDebugCodeEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="2c4f2-102">ICorDebugCodeEnum::Next Method</span></span>

<span data-ttu-id="2c4f2-103">Ruft die angegebene Anzahl von "ICorDebugCode"-Instanzen aus der-Enumeration ab, beginnend bei der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="2c4f2-103">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>

## <a name="syntax"></a><span data-ttu-id="2c4f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c4f2-104">Syntax</span></span>

```cpp
HRESULT Next (
    [in] ULONG  celt,
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorDebugCode *values[],
    [out] ULONG *pceltFetched
);
```

## <a name="parameters"></a><span data-ttu-id="2c4f2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2c4f2-105">Parameters</span></span>

`celt`  
<span data-ttu-id="2c4f2-106">in Die Anzahl der abzurufenden `ICorDebugCode`-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="2c4f2-106">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>

`values`  
<span data-ttu-id="2c4f2-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugCode`-Objekt zeigt.</span><span class="sxs-lookup"><span data-stu-id="2c4f2-107">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>

`pceltFetched`  
<span data-ttu-id="2c4f2-108">vorgenommen Ein Zeiger auf die Anzahl von `ICorDebugCode`-Instanzen, die tatsächlich zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="2c4f2-108">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="2c4f2-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="2c4f2-109">This value may be null if `celt` is one.</span></span>

## <a name="requirements"></a><span data-ttu-id="2c4f2-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c4f2-110">Requirements</span></span>

<span data-ttu-id="2c4f2-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c4f2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="2c4f2-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c4f2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="2c4f2-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c4f2-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="2c4f2-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c4f2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
