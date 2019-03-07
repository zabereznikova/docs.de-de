---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 460d6781405b6042262d50e1aa79ee8c77f781a7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489721"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="89d95-102">ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="89d95-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="89d95-103">Überprüft, ob die Methode asynchron Informationen oder nicht verfügt.</span><span class="sxs-lookup"><span data-stu-id="89d95-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="89d95-104">Wenn diese Methode zurückgibt `FALSE` ist es ungültig. alle anderen Methoden in dieser Schnittstelle aufrufen.</span><span class="sxs-lookup"><span data-stu-id="89d95-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="89d95-105">Werden alle Rückgabe `E_UNEXPECTED` in diesem Fall.</span><span class="sxs-lookup"><span data-stu-id="89d95-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89d95-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="89d95-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89d95-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="89d95-107">Parameters</span></span>  
  
|<span data-ttu-id="89d95-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="89d95-108">Parameter</span></span>|<span data-ttu-id="89d95-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89d95-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="89d95-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="89d95-110">Return Value</span></span>  
 <span data-ttu-id="89d95-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="89d95-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89d95-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="89d95-112">Requirements</span></span>  
 <span data-ttu-id="89d95-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="89d95-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89d95-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89d95-114">See also</span></span>
- [<span data-ttu-id="89d95-115">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89d95-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
