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
ms.openlocfilehash: e18172ecf2d4300ae42cc42ecdb1783744cac105
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490418"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="b2068-102">GetCLRIdentityManager-Funktion</span><span class="sxs-lookup"><span data-stu-id="b2068-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="b2068-103">Ruft einen Zeiger auf eine Schnittstelle, die die common Language Runtime (CLR) zum Verwalten von Identitäten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="b2068-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="b2068-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="b2068-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2068-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2068-105">Syntax</span></span>  
  
```  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2068-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b2068-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="b2068-107">[in] Ein `REFIID` (einen Schnittstellenbezeichner), die die Schnittstelle zum Abrufen von angibt.</span><span class="sxs-lookup"><span data-stu-id="b2068-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="b2068-108">Dieser Wert muss entweder IID_ICLRAssemblyIdentityManager oder IID_ICLRHostBindingPolicyManager sein.</span><span class="sxs-lookup"><span data-stu-id="b2068-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="b2068-109">[out] Ein Zeiger auf die Adresse ein [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) oder [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="b2068-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2068-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b2068-110">Remarks</span></span>  
 <span data-ttu-id="b2068-111">Rufen Sie die [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) Funktion, um einen Zeiger auf die `GetCLRIdentityManager` Funktion.</span><span class="sxs-lookup"><span data-stu-id="b2068-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2068-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b2068-112">Requirements</span></span>  
 <span data-ttu-id="b2068-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2068-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2068-114">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b2068-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2068-115">**Bibliothek:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="b2068-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="b2068-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2068-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2068-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2068-117">See also</span></span>

- [<span data-ttu-id="b2068-118">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="b2068-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
