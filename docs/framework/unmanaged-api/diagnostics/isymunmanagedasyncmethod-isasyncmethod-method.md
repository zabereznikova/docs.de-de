---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ce91552d7468579d9941c1da75c4d281999d66fd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="5139b-102">ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="5139b-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="5139b-103">Überprüft, ob die Methode über asynchrone Informationen verfügt.</span><span class="sxs-lookup"><span data-stu-id="5139b-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="5139b-104">Wenn diese Methode zurückgibt `FALSE` ist es unzulässig, alle anderen Methoden in dieser Schnittstelle aufrufen.</span><span class="sxs-lookup"><span data-stu-id="5139b-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="5139b-105">Sie werden alle Return `E_UNEXPECTED` in diesem Fall.</span><span class="sxs-lookup"><span data-stu-id="5139b-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5139b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5139b-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5139b-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="5139b-107">Parameters</span></span>  
  
|<span data-ttu-id="5139b-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="5139b-108">Parameter</span></span>|<span data-ttu-id="5139b-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5139b-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="5139b-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5139b-110">Return Value</span></span>  
 <span data-ttu-id="5139b-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="5139b-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5139b-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5139b-112">Requirements</span></span>  
 <span data-ttu-id="5139b-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5139b-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5139b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5139b-114">See Also</span></span>  
 [<span data-ttu-id="5139b-115">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5139b-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
