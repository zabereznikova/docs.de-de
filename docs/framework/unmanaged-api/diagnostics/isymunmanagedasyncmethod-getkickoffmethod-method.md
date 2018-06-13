---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod-Methode
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2f055dc19bf7f40036283102d8cc4549555b992
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424767"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="4892c-102">ISymUnmanagedAsyncMethod::GetKickoffMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="4892c-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="4892c-103">Finden Sie unter [DefineKickoffMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="4892c-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4892c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4892c-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4892c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4892c-105">Parameters</span></span>  
  
|<span data-ttu-id="4892c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4892c-106">Parameter</span></span>|<span data-ttu-id="4892c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4892c-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="4892c-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4892c-108">Return Value</span></span>  
 <span data-ttu-id="4892c-109">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="4892c-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4892c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4892c-110">Requirements</span></span>  
 <span data-ttu-id="4892c-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4892c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4892c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4892c-112">See Also</span></span>  
 [<span data-ttu-id="4892c-113">ISymUnmanagedAsyncMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4892c-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
