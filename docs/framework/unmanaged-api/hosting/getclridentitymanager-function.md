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
ms.openlocfilehash: 8b1e918edf641d38dd6b91d790bcaff8020293a0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493265"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="e70d0-102">GetCLRIdentityManager-Funktion</span><span class="sxs-lookup"><span data-stu-id="e70d0-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="e70d0-103">Ruft einen Zeiger auf eine-Schnittstelle ab, die dem Common Language Runtime (CLR) das Verwalten von Identitäten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="e70d0-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="e70d0-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="e70d0-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e70d0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e70d0-105">Syntax</span></span>  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e70d0-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e70d0-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="e70d0-107">in Ein `REFIID` (ein Schnittstellen Bezeichner), der angibt, welche Schnittstelle Sie erhalten.</span><span class="sxs-lookup"><span data-stu-id="e70d0-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="e70d0-108">Dieser Wert muss entweder IID_ICLRAssemblyIdentityManager oder IID_ICLRHostBindingPolicyManager sein.</span><span class="sxs-lookup"><span data-stu-id="e70d0-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="e70d0-109">vorgenommen Ein Zeiger auf die Adresse eines [ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md) -Objekts oder eines [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) -Objekts.</span><span class="sxs-lookup"><span data-stu-id="e70d0-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e70d0-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e70d0-110">Remarks</span></span>  
 <span data-ttu-id="e70d0-111">Aufrufen der [GetRealProcAddress](getrealprocaddress-function.md) -Funktion, um einen Zeiger auf die Funktion zu erhalten `GetCLRIdentityManager` .</span><span class="sxs-lookup"><span data-stu-id="e70d0-111">Call the [GetRealProcAddress](getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e70d0-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e70d0-112">Requirements</span></span>  
 <span data-ttu-id="e70d0-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e70d0-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e70d0-114">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e70d0-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e70d0-115">**Bibliothek:** Mscorwert. dll</span><span class="sxs-lookup"><span data-stu-id="e70d0-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="e70d0-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e70d0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e70d0-117">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="e70d0-117">See also</span></span>

- [<span data-ttu-id="e70d0-118">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="e70d0-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
