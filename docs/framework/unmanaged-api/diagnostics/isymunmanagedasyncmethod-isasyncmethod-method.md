---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f5bf8252986ffa90ea5380d5342595cb91e5419
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424940"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="31488-102">ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="31488-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="31488-103">Überprüft, ob die Methode über asynchrone Informationen verfügt.</span><span class="sxs-lookup"><span data-stu-id="31488-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="31488-104">Wenn diese Methode zurückgibt `FALSE` ist es unzulässig, alle anderen Methoden in dieser Schnittstelle aufrufen.</span><span class="sxs-lookup"><span data-stu-id="31488-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="31488-105">Sie werden alle Return `E_UNEXPECTED` in diesem Fall.</span><span class="sxs-lookup"><span data-stu-id="31488-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31488-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="31488-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="31488-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="31488-107">Parameters</span></span>  
  
|<span data-ttu-id="31488-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="31488-108">Parameter</span></span>|<span data-ttu-id="31488-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31488-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="31488-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="31488-110">Return Value</span></span>  
 <span data-ttu-id="31488-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="31488-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31488-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="31488-112">Requirements</span></span>  
 <span data-ttu-id="31488-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="31488-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31488-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31488-114">See Also</span></span>  
 [<span data-ttu-id="31488-115">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31488-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
