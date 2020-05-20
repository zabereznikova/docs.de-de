---
title: EClrUnhandledException-Enumeration
ms.date: 03/30/2017
api_name:
- EClrUnhandledException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrUnhandledException
helpviewer_keywords:
- EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type:
- apiref
ms.openlocfilehash: 63b07dda2293d3e05bd3c8fcdc45f20a498ea54c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616306"
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="120af-102">EClrUnhandledException-Enumeration</span><span class="sxs-lookup"><span data-stu-id="120af-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="120af-103">Beschreibt die verfügbaren Optionen zum Verwalten von Ausnahmen, die im Benutzercode nicht behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="120af-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="120af-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="120af-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="120af-105">Member</span><span class="sxs-lookup"><span data-stu-id="120af-105">Members</span></span>  
  
|<span data-ttu-id="120af-106">Member</span><span class="sxs-lookup"><span data-stu-id="120af-106">Member</span></span>|<span data-ttu-id="120af-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="120af-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="120af-108">Gibt an, dass das Standardverhalten auftritt.</span><span class="sxs-lookup"><span data-stu-id="120af-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="120af-109">Der Prozess wird beendet.</span><span class="sxs-lookup"><span data-stu-id="120af-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="120af-110">Gibt an, dass die Common Language Runtime (CLR) nicht behandelte Ausnahmen ignoriert und der Host jede weitere Aktion bestimmen kann.</span><span class="sxs-lookup"><span data-stu-id="120af-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="120af-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="120af-111">Remarks</span></span>  
 <span data-ttu-id="120af-112">Um anzugeben, dass die CLR sich wie frühere Versionen verhält, verwenden Sie den- `eHostDeterminedPolicy` Member.</span><span class="sxs-lookup"><span data-stu-id="120af-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="120af-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="120af-113">Requirements</span></span>  
 <span data-ttu-id="120af-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="120af-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="120af-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="120af-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="120af-116">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="120af-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="120af-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="120af-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="120af-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="120af-118">See also</span></span>

- [<span data-ttu-id="120af-119">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="120af-119">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="120af-120">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="120af-120">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="120af-121">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="120af-121">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="120af-122">SetUnhandledExceptionPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="120af-122">SetUnhandledExceptionPolicy Method</span></span>](iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [<span data-ttu-id="120af-123">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="120af-123">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="120af-124">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="120af-124">Hosting Enumerations</span></span>](hosting-enumerations.md)
