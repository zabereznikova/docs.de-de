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
ms.openlocfilehash: 39235c5c26cb168dfc995de97f72b80dccb6b818
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720294"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="279e5-102">ISymUnmanagedWriter3::OpenMethod2-Methode</span><span class="sxs-lookup"><span data-stu-id="279e5-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>

<span data-ttu-id="279e5-103">Öffnet eine-Methode und stellt den tatsächlichen Abschnitts Offset im Bild bereit.</span><span class="sxs-lookup"><span data-stu-id="279e5-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="279e5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="279e5-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="279e5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="279e5-105">Parameters</span></span>  

 `method`  
 <span data-ttu-id="279e5-106">in Das Metadatentoken für die Methode, die geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="279e5-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="279e5-107">in Der Abschnitts Offset im Bild.</span><span class="sxs-lookup"><span data-stu-id="279e5-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="279e5-108">in Der Offset im Bild.</span><span class="sxs-lookup"><span data-stu-id="279e5-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="279e5-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="279e5-109">Return Value</span></span>  

 <span data-ttu-id="279e5-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="279e5-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="279e5-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="279e5-111">Requirements</span></span>  

 <span data-ttu-id="279e5-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="279e5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="279e5-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="279e5-113">See also</span></span>

- [<span data-ttu-id="279e5-114">ISymUnmanagedWriter3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="279e5-114">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="279e5-115">OpenMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="279e5-115">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)
