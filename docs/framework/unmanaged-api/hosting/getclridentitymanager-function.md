---
title: GetCLRIdentityManager-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCLRIdentityManager
api_location: mscoree.dll
api_type: COM
f1_keywords: GetCLRIdentityManager
helpviewer_keywords: GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 699361bd33a844733427c213c4ef0f3ca4192906
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="4c1f3-102">GetCLRIdentityManager-Funktion</span><span class="sxs-lookup"><span data-stu-id="4c1f3-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="4c1f3-103">Ruft einen Zeiger auf eine Schnittstelle, die common Language Runtime (CLR) zum Verwalten von Identitäten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="4c1f3-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="4c1f3-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="4c1f3-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c1f3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c1f3-105">Syntax</span></span>  
  
```  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4c1f3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4c1f3-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="4c1f3-107">[in] Ein `REFIID` (einen Schnittstellenbezeichner), die die abzurufenden Schnittstelle angibt.</span><span class="sxs-lookup"><span data-stu-id="4c1f3-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="4c1f3-108">Dieser Wert muss entweder IID_ICLRAssemblyIdentityManager oder IID_ICLRHostBindingPolicyManager sein.</span><span class="sxs-lookup"><span data-stu-id="4c1f3-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="4c1f3-109">[out] Ein Zeiger auf die Adresse des entweder ein [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) oder ein [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="4c1f3-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c1f3-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4c1f3-110">Remarks</span></span>  
 <span data-ttu-id="4c1f3-111">Rufen Sie die [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) Funktion, um einen Zeiger auf die `GetCLRIdentityManager` Funktion.</span><span class="sxs-lookup"><span data-stu-id="4c1f3-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c1f3-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4c1f3-112">Requirements</span></span>  
 <span data-ttu-id="4c1f3-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c1f3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c1f3-114">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4c1f3-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4c1f3-115">**Bibliothek:** "Mscorwks.dll"</span><span class="sxs-lookup"><span data-stu-id="4c1f3-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="4c1f3-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c1f3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c1f3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c1f3-117">See Also</span></span>  
 [<span data-ttu-id="4c1f3-118">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="4c1f3-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
