---
title: CloseAssembly-Methode
ms.date: 03/30/2017
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseAssembly
helpviewer_keywords:
- CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type:
- apiref
ms.openlocfilehash: 70dca19075d8c896408ec78f89549b0c539280de
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446582"
---
# <a name="closeassembly-method"></a><span data-ttu-id="c0f62-102">CloseAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="c0f62-102">CloseAssembly Method</span></span>
<span data-ttu-id="c0f62-103">Finalizes assembly operations.</span><span class="sxs-lookup"><span data-stu-id="c0f62-103">Finalizes assembly operations.</span></span> <span data-ttu-id="c0f62-104">Call this method before beginning a new assembly or unbound module.</span><span class="sxs-lookup"><span data-stu-id="c0f62-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0f62-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0f62-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0f62-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c0f62-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c0f62-107">ID of the assembly.</span><span class="sxs-lookup"><span data-stu-id="c0f62-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0f62-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c0f62-108">Return Value</span></span>  
 <span data-ttu-id="c0f62-109">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="c0f62-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0f62-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c0f62-110">Requirements</span></span>  
 <span data-ttu-id="c0f62-111">Requires alink.h.</span><span class="sxs-lookup"><span data-stu-id="c0f62-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f62-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0f62-112">See also</span></span>

- [<span data-ttu-id="c0f62-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0f62-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c0f62-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0f62-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c0f62-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="c0f62-115">ALink API</span></span>](index.md)
