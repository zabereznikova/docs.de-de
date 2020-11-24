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
ms.openlocfilehash: b315f38dc306727e33b52b84d17951a91ccdc39f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684472"
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="53843-102">ICorDebugAppDomainEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="53843-102">ICorDebugAppDomainEnum::Next Method</span></span>

<span data-ttu-id="53843-103">Ruft die angegebene Anzahl von Anwendungs Domänen ab der aktuellen Cursorposition aus der Auflistung ab.</span><span class="sxs-lookup"><span data-stu-id="53843-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53843-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="53843-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53843-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="53843-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="53843-106">in Die Anzahl der Anwendungs Domänen, die abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="53843-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="53843-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein ICorDebugAppDomain-Objekt verweist, das eine Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="53843-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="53843-108">vorgenommen Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Anwendungs Domänen.</span><span class="sxs-lookup"><span data-stu-id="53843-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="53843-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="53843-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53843-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="53843-110">Requirements</span></span>  

 <span data-ttu-id="53843-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53843-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53843-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53843-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53843-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53843-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53843-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53843-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
