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
ms.openlocfilehash: d18702a1bb15d2cc6c7b8577b91ed011e9bd0c05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733671"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="b84ff-102">FLockClrVersionCallback-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="b84ff-102">FLockClrVersionCallback Function Pointer</span></span>

<span data-ttu-id="b84ff-103">Verweist auf eine Funktion, die vom Common Language Runtime (CLR) aufgerufen wird, um anzugeben, dass die Initialisierung entweder gestartet oder abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="b84ff-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="b84ff-104">Dieser Funktionszeiger wurde in der .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="b84ff-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b84ff-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b84ff-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="b84ff-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b84ff-106">Remarks</span></span>  

 <span data-ttu-id="b84ff-107">Diese Funktion wird vom Host implementiert.</span><span class="sxs-lookup"><span data-stu-id="b84ff-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b84ff-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b84ff-108">Requirements</span></span>  

 <span data-ttu-id="b84ff-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b84ff-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b84ff-110">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="b84ff-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b84ff-111">**Bibliothek:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="b84ff-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="b84ff-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b84ff-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b84ff-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b84ff-113">See also</span></span>

- [<span data-ttu-id="b84ff-114">LockClrVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="b84ff-114">LockClrVersion Function</span></span>](lockclrversion-function.md)
- [<span data-ttu-id="b84ff-115">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="b84ff-115">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
