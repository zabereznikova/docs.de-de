---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 049f8e4d04498b70533134c01765af2d996d86dc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499105"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="28259-102">ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="28259-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="28259-103">Überprüft, ob die Methode asynchron Informationen oder nicht verfügt.</span><span class="sxs-lookup"><span data-stu-id="28259-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="28259-104">Wenn diese Methode zurückgibt `FALSE` ist es ungültig. alle anderen Methoden in dieser Schnittstelle aufrufen.</span><span class="sxs-lookup"><span data-stu-id="28259-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="28259-105">Werden alle Rückgabe `E_UNEXPECTED` in diesem Fall.</span><span class="sxs-lookup"><span data-stu-id="28259-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28259-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="28259-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="28259-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="28259-107">Parameters</span></span>  
  
|<span data-ttu-id="28259-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="28259-108">Parameter</span></span>|<span data-ttu-id="28259-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28259-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="28259-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="28259-110">Return Value</span></span>  
 <span data-ttu-id="28259-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="28259-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28259-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="28259-112">Requirements</span></span>  
 <span data-ttu-id="28259-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="28259-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28259-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28259-114">See also</span></span>
- [<span data-ttu-id="28259-115">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="28259-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
