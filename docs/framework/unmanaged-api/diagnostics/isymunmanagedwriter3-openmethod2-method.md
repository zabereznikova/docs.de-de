---
title: ISymUnmanagedWriter3::OpenMethod2-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.OpenMethod2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::OpenMethod2
helpviewer_keywords:
- ISymUnmanagedWriter3::OpenMethod2 method [.NET Framework debugging]
- OpenMethod2 method [.NET Framework debugging]
ms.assetid: 025e358c-448f-4423-a2f2-57acf437c8a5
topic_type:
- apiref
ms.openlocfilehash: 3a628aec0823c5db07d31d33813a020606906163
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438121"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="35540-102">ISymUnmanagedWriter3::OpenMethod2-Methode</span><span class="sxs-lookup"><span data-stu-id="35540-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="35540-103">Öffnet eine-Methode und stellt den tatsächlichen Abschnitts Offset im Bild bereit.</span><span class="sxs-lookup"><span data-stu-id="35540-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35540-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="35540-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35540-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="35540-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="35540-106">in Das Metadatentoken für die Methode, die geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="35540-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="35540-107">in Der Abschnitts Offset im Bild.</span><span class="sxs-lookup"><span data-stu-id="35540-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="35540-108">in Der Offset im Bild.</span><span class="sxs-lookup"><span data-stu-id="35540-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35540-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="35540-109">Return Value</span></span>  
 <span data-ttu-id="35540-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="35540-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35540-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="35540-111">Requirements</span></span>  
 <span data-ttu-id="35540-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="35540-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35540-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35540-113">See also</span></span>

- [<span data-ttu-id="35540-114">ISymUnmanagedWriter3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35540-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="35540-115">OpenMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="35540-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
