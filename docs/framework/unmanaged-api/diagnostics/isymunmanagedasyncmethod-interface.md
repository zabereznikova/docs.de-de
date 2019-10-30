---
title: ISymUnmanagedAsyncMethod-Schnittstelle
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: 0b8adba9dbffbdc47bb526cef9aad3ffa4b48065
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129223"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="5fb1c-102">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5fb1c-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="5fb1c-103">Diese Schnittstelle ist die Lese Ergänzung zur [isymunmanagedasyncmethodpropertieswriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5fb1c-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fb1c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5fb1c-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="5fb1c-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="5fb1c-105">Methods</span></span>  
 <span data-ttu-id="5fb1c-106">Diese Schnittstelle enthält die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="5fb1c-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="5fb1c-107">Methode</span><span class="sxs-lookup"><span data-stu-id="5fb1c-107">Method</span></span>|<span data-ttu-id="5fb1c-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5fb1c-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5fb1c-109">GetAsyncStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="5fb1c-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="5fb1c-110">Siehe [defineasyncstepinfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="5fb1c-110">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="5fb1c-111">GetAsyncStepInfoCount-Methode</span><span class="sxs-lookup"><span data-stu-id="5fb1c-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="5fb1c-112">Siehe [defineasyncstepinfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="5fb1c-112">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="5fb1c-113">GetCatchHandlerILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="5fb1c-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="5fb1c-114">Siehe [definecatchhandleriloffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="5fb1c-114">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="5fb1c-115">GetKickoffMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="5fb1c-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="5fb1c-116">Siehe [definekickoffmethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="5fb1c-116">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="5fb1c-117">HasCatchHandlerILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="5fb1c-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="5fb1c-118">Siehe [definecatchhandleriloffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="5fb1c-118">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="5fb1c-119">IsAsyncMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="5fb1c-119">IsAsyncMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="5fb1c-120">Überprüft, ob die Methode über asynchrone Informationen verfügt oder nicht.</span><span class="sxs-lookup"><span data-stu-id="5fb1c-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="5fb1c-121">Wenn diese Methode `FALSE` zurückgibt, ist es ungültig, andere Methoden in dieser Schnittstelle aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="5fb1c-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="5fb1c-122">Alle werden in diesem Fall `E_UNEXPECTED` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5fb1c-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5fb1c-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5fb1c-123">Requirements</span></span>  
 <span data-ttu-id="5fb1c-124">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="5fb1c-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fb1c-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5fb1c-125">See also</span></span>

- [<span data-ttu-id="5fb1c-126">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5fb1c-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
