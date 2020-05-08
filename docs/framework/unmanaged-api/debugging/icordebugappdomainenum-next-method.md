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
ms.openlocfilehash: 17bf4c92b1e1347a8fe790c8df5937de0f95df4d
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895081"
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="46b4a-102">ICorDebugAppDomainEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="46b4a-102">ICorDebugAppDomainEnum::Next Method</span></span>
<span data-ttu-id="46b4a-103">Ruft die angegebene Anzahl von Anwendungs Domänen ab der aktuellen Cursorposition aus der Auflistung ab.</span><span class="sxs-lookup"><span data-stu-id="46b4a-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46b4a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="46b4a-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46b4a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="46b4a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="46b4a-106">in Die Anzahl der Anwendungs Domänen, die abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="46b4a-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="46b4a-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein ICorDebugAppDomain-Objekt verweist, das eine Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="46b4a-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="46b4a-108">vorgenommen Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Anwendungs Domänen.</span><span class="sxs-lookup"><span data-stu-id="46b4a-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="46b4a-109">Dieser Wert kann NULL sein, `celt` wenn ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="46b4a-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46b4a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="46b4a-110">Requirements</span></span>  
 <span data-ttu-id="46b4a-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46b4a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46b4a-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46b4a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46b4a-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46b4a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46b4a-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46b4a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
