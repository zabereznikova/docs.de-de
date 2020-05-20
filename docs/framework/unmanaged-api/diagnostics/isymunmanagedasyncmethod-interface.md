---
title: ISymUnmanagedAsyncMethod-Schnittstelle
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: fef1af75587b889afad9cb5b93d0cd722294006b
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441811"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="986f3-102">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="986f3-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="986f3-103">Diese Schnittstelle ist die Lese Ergänzung zur [isymunmanagedasyncmethodpropertieswriter-Schnittstelle](isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="986f3-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="986f3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="986f3-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="986f3-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="986f3-105">Methods</span></span>  
 <span data-ttu-id="986f3-106">Diese Schnittstelle enthält die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="986f3-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="986f3-107">Methode</span><span class="sxs-lookup"><span data-stu-id="986f3-107">Method</span></span>|<span data-ttu-id="986f3-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="986f3-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="986f3-109">GetAsyncStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="986f3-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="986f3-110">Siehe [defineasyncstepinfo-Methode](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="986f3-110">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="986f3-111">GetAsyncStepInfoCount-Methode</span><span class="sxs-lookup"><span data-stu-id="986f3-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="986f3-112">Siehe [defineasyncstepinfo-Methode](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="986f3-112">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="986f3-113">GetCatchHandlerILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="986f3-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="986f3-114">Siehe [definecatchhandleriloffset-Methode](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="986f3-114">See [DefineCatchHandlerILOffset Method](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="986f3-115">GetKickoffMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="986f3-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="986f3-116">Siehe [definekickoffmethod-Methode](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="986f3-116">See [DefineKickoffMethod Method](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="986f3-117">HasCatchHandlerILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="986f3-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="986f3-118">Siehe [definecatchhandleriloffset-Methode](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="986f3-118">See [DefineCatchHandlerILOffset Method](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="986f3-119">IsAsyncMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="986f3-119">IsAsyncMethod Method</span></span>](isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="986f3-120">Überprüft, ob die Methode über asynchrone Informationen verfügt oder nicht.</span><span class="sxs-lookup"><span data-stu-id="986f3-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="986f3-121">Wenn diese Methode zurückgibt `FALSE` , ist es ungültig, andere Methoden in dieser Schnittstelle aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="986f3-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="986f3-122">In diesem Fall werden alle zurückgegeben `E_UNEXPECTED` .</span><span class="sxs-lookup"><span data-stu-id="986f3-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="986f3-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="986f3-123">Requirements</span></span>  
 <span data-ttu-id="986f3-124">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="986f3-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="986f3-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="986f3-125">See also</span></span>

- [<span data-ttu-id="986f3-126">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="986f3-126">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
