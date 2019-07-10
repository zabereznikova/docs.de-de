---
title: FLockClrVersionCallback-Funktionszeiger
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46e3356df6578f2adf2ceee00b1363b65fd014ea
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760228"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="d205f-102">FLockClrVersionCallback-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="d205f-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="d205f-103">Verweist auf eine Funktion, die die common Language Runtime (CLR) Ruft auf, um anzugeben, dass die Initialisierung gestartet oder abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="d205f-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="d205f-104">Dieser Funktionszeiger wurde in .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="d205f-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d205f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d205f-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="d205f-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d205f-106">Remarks</span></span>  
 <span data-ttu-id="d205f-107">Diese Funktion wird vom Host implementiert.</span><span class="sxs-lookup"><span data-stu-id="d205f-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d205f-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d205f-108">Requirements</span></span>  
 <span data-ttu-id="d205f-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d205f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d205f-110">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d205f-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d205f-111">**Bibliothek:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="d205f-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="d205f-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d205f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d205f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d205f-113">See also</span></span>

- [<span data-ttu-id="d205f-114">LockClrVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="d205f-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [<span data-ttu-id="d205f-115">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="d205f-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
