---
title: ICorDebugAppDomainEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum::Next method
helpviewer_keywords:
- ICorDebugAppDomainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: b8d1def7-0ebc-4314-a3a2-fd36a75973e7
topic_type:
- apiref
ms.openlocfilehash: 55e331ff4e6ada73dc92bb2e880f555887639714
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088793"
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="41656-102">ICorDebugAppDomainEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="41656-102">ICorDebugAppDomainEnum::Next Method</span></span>
<span data-ttu-id="41656-103">Ruft die angegebene Anzahl von Anwendungs Domänen ab der aktuellen Cursorposition aus der Auflistung ab.</span><span class="sxs-lookup"><span data-stu-id="41656-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41656-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41656-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41656-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="41656-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="41656-106">in Die Anzahl der Anwendungs Domänen, die abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="41656-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="41656-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein ICorDebugAppDomain-Objekt verweist, das eine Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="41656-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="41656-108">vorgenommen Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Anwendungs Domänen.</span><span class="sxs-lookup"><span data-stu-id="41656-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="41656-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="41656-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41656-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="41656-110">Requirements</span></span>  
 <span data-ttu-id="41656-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41656-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41656-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41656-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41656-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41656-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41656-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41656-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
