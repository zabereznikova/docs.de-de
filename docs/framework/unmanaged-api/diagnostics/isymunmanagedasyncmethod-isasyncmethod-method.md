---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: af02aba1a0d390c103e8c6108f90b93fe2a98ff3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707151"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="2fbb0-102">ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="2fbb0-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>

<span data-ttu-id="2fbb0-103">Überprüft, ob die Methode über asynchrone Informationen verfügt oder nicht.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="2fbb0-104">Wenn diese Methode zurückgibt `FALSE` , ist es ungültig, andere Methoden in dieser Schnittstelle aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="2fbb0-105">In diesem Fall werden alle zurückgegeben `E_UNEXPECTED` .</span><span class="sxs-lookup"><span data-stu-id="2fbb0-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fbb0-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2fbb0-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fbb0-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="2fbb0-107">Parameters</span></span>  
  
|<span data-ttu-id="2fbb0-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="2fbb0-108">Parameter</span></span>|<span data-ttu-id="2fbb0-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2fbb0-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="2fbb0-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2fbb0-110">Return Value</span></span>  

 <span data-ttu-id="2fbb0-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="2fbb0-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fbb0-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2fbb0-112">Requirements</span></span>  

 <span data-ttu-id="2fbb0-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="2fbb0-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fbb0-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2fbb0-114">See also</span></span>

- [<span data-ttu-id="2fbb0-115">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2fbb0-115">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
