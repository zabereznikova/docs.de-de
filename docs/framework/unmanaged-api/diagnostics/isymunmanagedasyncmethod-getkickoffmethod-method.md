---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod-Methode
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f20039318d6e1230ccc0fbd203fc44686806bb2e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604469"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="329af-102">ISymUnmanagedAsyncMethod::GetKickoffMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="329af-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="329af-103">Finden Sie unter [DefineKickoffMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="329af-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="329af-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="329af-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="329af-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="329af-105">Parameters</span></span>  
  
|<span data-ttu-id="329af-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="329af-106">Parameter</span></span>|<span data-ttu-id="329af-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="329af-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="329af-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="329af-108">Return Value</span></span>  
 <span data-ttu-id="329af-109">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="329af-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="329af-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="329af-110">Requirements</span></span>  
 <span data-ttu-id="329af-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="329af-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="329af-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="329af-112">See also</span></span>
- [<span data-ttu-id="329af-113">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="329af-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
