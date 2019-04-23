---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5cddf34f1a6277e966901c9692bff63e26a3b8e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136733"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="4cf83-102">ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="4cf83-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="4cf83-103">Überprüft, ob die Methode asynchron Informationen oder nicht verfügt.</span><span class="sxs-lookup"><span data-stu-id="4cf83-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="4cf83-104">Wenn diese Methode zurückgibt `FALSE` ist es ungültig. alle anderen Methoden in dieser Schnittstelle aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4cf83-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="4cf83-105">Werden alle Rückgabe `E_UNEXPECTED` in diesem Fall.</span><span class="sxs-lookup"><span data-stu-id="4cf83-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cf83-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4cf83-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cf83-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="4cf83-107">Parameters</span></span>  
  
|<span data-ttu-id="4cf83-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="4cf83-108">Parameter</span></span>|<span data-ttu-id="4cf83-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4cf83-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="4cf83-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4cf83-110">Return Value</span></span>  
 <span data-ttu-id="4cf83-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="4cf83-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cf83-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4cf83-112">Requirements</span></span>  
 <span data-ttu-id="4cf83-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4cf83-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cf83-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cf83-114">See also</span></span>

- [<span data-ttu-id="4cf83-115">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4cf83-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
