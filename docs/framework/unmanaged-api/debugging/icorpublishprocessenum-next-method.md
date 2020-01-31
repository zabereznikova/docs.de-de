---
title: ICorPublishProcessEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum::Next
helpviewer_keywords:
- ICorPublishProcessEnum::Next method [.NET Framework debugging]
- Next method, ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: 6c399f37-1e38-4ca1-b70d-8ae41f7228b7
topic_type:
- apiref
ms.openlocfilehash: 084af87acd73ef65739ba69ef2bd66d10d7c27c2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790516"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="90f19-102">ICorPublishProcessEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="90f19-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="90f19-103">Ruft die angegebene Anzahl von Prozessen ab der aktuellen Cursorposition aus der Auflistung ab.</span><span class="sxs-lookup"><span data-stu-id="90f19-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90f19-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90f19-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90f19-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="90f19-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="90f19-106">in Die Anzahl der abzurufenden Prozesse.</span><span class="sxs-lookup"><span data-stu-id="90f19-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="90f19-107">vorgenommen Ein Zeiger auf das Array von abgerufenen [ICorPublishProcess](icorpublishprocess-interface.md) -Objekten, von denen jedes einen Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="90f19-107">[out] A pointer to the array of retrieved [ICorPublishProcess](icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="90f19-108">vorgenommen Zeiger auf die Anzahl der tatsächlich zurückgegebenen Prozesse.</span><span class="sxs-lookup"><span data-stu-id="90f19-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="90f19-109">Dieser Wert kann NULL sein, wenn `celt` 1 ist.</span><span class="sxs-lookup"><span data-stu-id="90f19-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90f19-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="90f19-110">Requirements</span></span>  
 <span data-ttu-id="90f19-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90f19-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90f19-112">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="90f19-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="90f19-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90f19-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90f19-114">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90f19-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90f19-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90f19-115">See also</span></span>

- [<span data-ttu-id="90f19-116">ICorPublishProcessEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90f19-116">ICorPublishProcessEnum Interface</span></span>](icorpublishprocessenum-interface.md)
