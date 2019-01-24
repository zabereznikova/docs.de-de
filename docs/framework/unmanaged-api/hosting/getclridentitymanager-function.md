---
title: GetCLRIdentityManager-Funktion
ms.date: 03/30/2017
api_name:
- GetCLRIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetCLRIdentityManager
helpviewer_keywords:
- GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f40100be3ab05c0c8e8a55d48494569424e88371
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637265"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="2ba46-102">GetCLRIdentityManager-Funktion</span><span class="sxs-lookup"><span data-stu-id="2ba46-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="2ba46-103">Ruft einen Zeiger auf eine Schnittstelle, die die common Language Runtime (CLR) zum Verwalten von Identitäten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="2ba46-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="2ba46-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="2ba46-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ba46-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ba46-105">Syntax</span></span>  
  
```  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ba46-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ba46-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="2ba46-107">[in] Ein `REFIID` (einen Schnittstellenbezeichner), die die Schnittstelle zum Abrufen von angibt.</span><span class="sxs-lookup"><span data-stu-id="2ba46-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="2ba46-108">Dieser Wert muss entweder IID_ICLRAssemblyIdentityManager oder IID_ICLRHostBindingPolicyManager sein.</span><span class="sxs-lookup"><span data-stu-id="2ba46-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="2ba46-109">[out] Ein Zeiger auf die Adresse ein [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) oder [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="2ba46-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ba46-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ba46-110">Remarks</span></span>  
 <span data-ttu-id="2ba46-111">Rufen Sie die [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) Funktion, um einen Zeiger auf die `GetCLRIdentityManager` Funktion.</span><span class="sxs-lookup"><span data-stu-id="2ba46-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ba46-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ba46-112">Requirements</span></span>  
 <span data-ttu-id="2ba46-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ba46-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ba46-114">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2ba46-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ba46-115">**Bibliothek:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="2ba46-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="2ba46-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ba46-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ba46-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ba46-117">See also</span></span>
- [<span data-ttu-id="2ba46-118">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="2ba46-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
