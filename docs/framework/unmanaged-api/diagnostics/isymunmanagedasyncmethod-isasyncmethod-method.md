---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 0ea4c21e9e6a49d7bbbad5e1853598c440cd6410
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129212"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="d40b1-102">ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="d40b1-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="d40b1-103">Überprüft, ob die Methode über asynchrone Informationen verfügt oder nicht.</span><span class="sxs-lookup"><span data-stu-id="d40b1-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="d40b1-104">Wenn diese Methode `FALSE` zurückgibt, ist es ungültig, andere Methoden in dieser Schnittstelle aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="d40b1-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="d40b1-105">Alle werden in diesem Fall `E_UNEXPECTED` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d40b1-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d40b1-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d40b1-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d40b1-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="d40b1-107">Parameters</span></span>  
  
|<span data-ttu-id="d40b1-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="d40b1-108">Parameter</span></span>|<span data-ttu-id="d40b1-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d40b1-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="d40b1-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d40b1-110">Return Value</span></span>  
 <span data-ttu-id="d40b1-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="d40b1-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d40b1-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d40b1-112">Requirements</span></span>  
 <span data-ttu-id="d40b1-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="d40b1-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d40b1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d40b1-114">See also</span></span>

- [<span data-ttu-id="d40b1-115">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d40b1-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
