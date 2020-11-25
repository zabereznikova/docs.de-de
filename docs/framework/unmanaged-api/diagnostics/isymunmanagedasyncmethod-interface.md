---
title: ISymUnmanagedAsyncMethod-Schnittstelle
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: 02b1866f2b9e89cdc8c8795f399ecc0c733c7202
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707164"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="95e90-102">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95e90-102">ISymUnmanagedAsyncMethod Interface</span></span>

<span data-ttu-id="95e90-103">Diese Schnittstelle ist die Lese Ergänzung zur [isymunmanagedasyncmethodpropertieswriter-Schnittstelle](isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="95e90-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95e90-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="95e90-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="95e90-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="95e90-105">Methods</span></span>  

 <span data-ttu-id="95e90-106">Diese Schnittstelle enthält die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="95e90-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="95e90-107">Methode</span><span class="sxs-lookup"><span data-stu-id="95e90-107">Method</span></span>|<span data-ttu-id="95e90-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="95e90-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95e90-109">GetAsyncStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="95e90-109">GetAsyncStepInfo Method</span></span>](isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="95e90-110">Siehe [defineasyncstepinfo-Methode](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="95e90-110">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="95e90-111">GetAsyncStepInfoCount-Methode</span><span class="sxs-lookup"><span data-stu-id="95e90-111">GetAsyncStepInfoCount Method</span></span>](isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="95e90-112">Siehe [defineasyncstepinfo-Methode](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="95e90-112">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="95e90-113">GetCatchHandlerILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="95e90-113">GetCatchHandlerILOffset Method</span></span>](isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="95e90-114">Siehe [definecatchhandleriloffset-Methode](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="95e90-114">See [DefineCatchHandlerILOffset Method](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="95e90-115">GetKickoffMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="95e90-115">GetKickoffMethod Method</span></span>](isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="95e90-116">Siehe [definekickoffmethod-Methode](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="95e90-116">See [DefineKickoffMethod Method](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="95e90-117">HasCatchHandlerILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="95e90-117">HasCatchHandlerILOffset Method</span></span>](isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="95e90-118">Siehe [definecatchhandleriloffset-Methode](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="95e90-118">See [DefineCatchHandlerILOffset Method](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="95e90-119">IsAsyncMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="95e90-119">IsAsyncMethod Method</span></span>](isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="95e90-120">Überprüft, ob die Methode über asynchrone Informationen verfügt oder nicht.</span><span class="sxs-lookup"><span data-stu-id="95e90-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="95e90-121">Wenn diese Methode zurückgibt `FALSE` , ist es ungültig, andere Methoden in dieser Schnittstelle aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="95e90-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="95e90-122">In diesem Fall werden alle zurückgegeben `E_UNEXPECTED` .</span><span class="sxs-lookup"><span data-stu-id="95e90-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="95e90-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="95e90-123">Requirements</span></span>  

 <span data-ttu-id="95e90-124">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="95e90-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95e90-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95e90-125">See also</span></span>

- [<span data-ttu-id="95e90-126">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="95e90-126">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
