---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3e017097183243c84a2ce40cc473067e05c80c3c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="6f53f-102">ISymUnmanagedAsyncMethod::GetKickoffMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="6f53f-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="6f53f-103">Finden Sie unter [DefineKickoffMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="6f53f-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f53f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f53f-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6f53f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6f53f-105">Parameters</span></span>  
  
|<span data-ttu-id="6f53f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6f53f-106">Parameter</span></span>|<span data-ttu-id="6f53f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f53f-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="6f53f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6f53f-108">Return Value</span></span>  
 <span data-ttu-id="6f53f-109">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="6f53f-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f53f-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6f53f-110">Requirements</span></span>  
 <span data-ttu-id="6f53f-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6f53f-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f53f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f53f-112">See Also</span></span>  
 [<span data-ttu-id="6f53f-113">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f53f-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
