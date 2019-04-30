---
title: ISymUnmanagedAsyncMethod-Schnittstelle
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd524446cd9fd5cf9c067ab5778a654ed000ffb3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940178"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="5e24c-102">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e24c-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="5e24c-103">Diese Schnittstelle ist die Ergänzung lesen [ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5e24c-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e24c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e24c-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="5e24c-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="5e24c-105">Methods</span></span>  
 <span data-ttu-id="5e24c-106">Diese Schnittstelle enthält die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="5e24c-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="5e24c-107">Methode</span><span class="sxs-lookup"><span data-stu-id="5e24c-107">Method</span></span>|<span data-ttu-id="5e24c-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e24c-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5e24c-109">GetAsyncStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="5e24c-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="5e24c-110">Finden Sie unter [DefineAsyncStepInfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="5e24c-110">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="5e24c-111">GetAsyncStepInfoCount-Methode</span><span class="sxs-lookup"><span data-stu-id="5e24c-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="5e24c-112">Finden Sie unter [DefineAsyncStepInfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="5e24c-112">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="5e24c-113">GetCatchHandlerILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="5e24c-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="5e24c-114">Finden Sie unter [DefineCatchHandlerILOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="5e24c-114">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="5e24c-115">GetKickoffMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="5e24c-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="5e24c-116">Finden Sie unter [DefineKickoffMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="5e24c-116">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="5e24c-117">HasCatchHandlerILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="5e24c-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="5e24c-118">Finden Sie unter [DefineCatchHandlerILOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="5e24c-118">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="5e24c-119">IsAsyncMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="5e24c-119">IsAsyncMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="5e24c-120">Überprüft, ob die Methode asynchron Informationen oder nicht verfügt.</span><span class="sxs-lookup"><span data-stu-id="5e24c-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="5e24c-121">Wenn diese Methode zurückgibt `FALSE` ist es ungültig. alle anderen Methoden in dieser Schnittstelle aufrufen.</span><span class="sxs-lookup"><span data-stu-id="5e24c-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="5e24c-122">Werden alle Rückgabe `E_UNEXPECTED` in diesem Fall.</span><span class="sxs-lookup"><span data-stu-id="5e24c-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5e24c-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5e24c-123">Requirements</span></span>  
 <span data-ttu-id="5e24c-124">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5e24c-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e24c-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e24c-125">See also</span></span>

- [<span data-ttu-id="5e24c-126">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5e24c-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
