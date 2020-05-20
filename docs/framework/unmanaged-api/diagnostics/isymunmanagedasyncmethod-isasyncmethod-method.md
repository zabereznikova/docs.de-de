---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 91b4c2688dadf12fa4a835a662622267d7831cf8
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441798"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="5bd00-102">ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="5bd00-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="5bd00-103">Überprüft, ob die Methode über asynchrone Informationen verfügt oder nicht.</span><span class="sxs-lookup"><span data-stu-id="5bd00-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="5bd00-104">Wenn diese Methode zurückgibt `FALSE` , ist es ungültig, andere Methoden in dieser Schnittstelle aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="5bd00-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="5bd00-105">In diesem Fall werden alle zurückgegeben `E_UNEXPECTED` .</span><span class="sxs-lookup"><span data-stu-id="5bd00-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bd00-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5bd00-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bd00-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="5bd00-107">Parameters</span></span>  
  
|<span data-ttu-id="5bd00-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="5bd00-108">Parameter</span></span>|<span data-ttu-id="5bd00-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5bd00-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="5bd00-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5bd00-110">Return Value</span></span>  
 <span data-ttu-id="5bd00-111">Gibt `HRESULT` zurück.</span><span class="sxs-lookup"><span data-stu-id="5bd00-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bd00-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5bd00-112">Requirements</span></span>  
 <span data-ttu-id="5bd00-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="5bd00-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bd00-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5bd00-114">See also</span></span>

- [<span data-ttu-id="5bd00-115">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5bd00-115">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
