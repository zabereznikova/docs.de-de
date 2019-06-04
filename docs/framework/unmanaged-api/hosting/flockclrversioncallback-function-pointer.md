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
ms.openlocfilehash: ef308b624525c3a139c892e6118a24d6adb6e14a
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490465"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="b3418-102">FLockClrVersionCallback-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="b3418-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="b3418-103">Verweist auf eine Funktion, die die common Language Runtime (CLR) Ruft auf, um anzugeben, dass die Initialisierung gestartet oder abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="b3418-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="b3418-104">Dieser Funktionszeiger wurde in .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="b3418-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3418-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3418-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="b3418-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b3418-106">Remarks</span></span>  
 <span data-ttu-id="b3418-107">Diese Funktion wird vom Host implementiert.</span><span class="sxs-lookup"><span data-stu-id="b3418-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3418-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b3418-108">Requirements</span></span>  
 <span data-ttu-id="b3418-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3418-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3418-110">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b3418-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b3418-111">**Bibliothek:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="b3418-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="b3418-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3418-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3418-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3418-113">See also</span></span>

- [<span data-ttu-id="b3418-114">LockClrVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="b3418-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [<span data-ttu-id="b3418-115">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="b3418-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
