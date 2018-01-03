---
title: ISymUnmanagedAsyncMethod-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9f83723b59f525c06f04b7edeeae953dbf94556
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="92515-102">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92515-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="92515-103">Diese Schnittstelle ist die lesen-Ergänzung zur [ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="92515-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92515-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="92515-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="92515-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="92515-105">Methods</span></span>  
 <span data-ttu-id="92515-106">Diese Schnittstelle enthält die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="92515-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="92515-107">Methode</span><span class="sxs-lookup"><span data-stu-id="92515-107">Method</span></span>|<span data-ttu-id="92515-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92515-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="92515-109">GetAsyncStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="92515-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="92515-110">Finden Sie unter [DefineAsyncStepInfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="92515-110">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="92515-111">GetAsyncStepInfoCount-Methode</span><span class="sxs-lookup"><span data-stu-id="92515-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="92515-112">Finden Sie unter [DefineAsyncStepInfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="92515-112">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="92515-113">GetCatchHandlerILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="92515-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="92515-114">Finden Sie unter [DefineCatchHandlerILOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="92515-114">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="92515-115">GetKickoffMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="92515-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="92515-116">Finden Sie unter [DefineKickoffMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="92515-116">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="92515-117">HasCatchHandlerILOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="92515-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="92515-118">Finden Sie unter [DefineCatchHandlerILOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="92515-118">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="92515-119">IsAsyncMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="92515-119">IsAsyncMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="92515-120">Überprüft, ob die Methode über asynchrone Informationen verfügt.</span><span class="sxs-lookup"><span data-stu-id="92515-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="92515-121">Wenn diese Methode zurückgibt `FALSE` ist es unzulässig, alle anderen Methoden in dieser Schnittstelle aufrufen.</span><span class="sxs-lookup"><span data-stu-id="92515-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="92515-122">Sie werden alle Return `E_UNEXPECTED` in diesem Fall.</span><span class="sxs-lookup"><span data-stu-id="92515-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="92515-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="92515-123">Requirements</span></span>  
 <span data-ttu-id="92515-124">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="92515-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92515-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92515-125">See Also</span></span>  
 [<span data-ttu-id="92515-126">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="92515-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
