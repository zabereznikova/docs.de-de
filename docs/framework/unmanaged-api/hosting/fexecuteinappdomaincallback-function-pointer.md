---
title: FExecuteInAppDomainCallback-Funktionszeiger
ms.date: 03/30/2017
api_name:
- FExecuteInAppDomainCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FExecuteInAppDomainCallback
helpviewer_keywords:
- FExecuteInAppDomainCallback function pointer [.NET Framework hosting]
ms.assetid: 2709f18f-3eee-497f-bc33-3ab7a485599b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8edd2a42ed1b826e1b6ea09e92165bc9fa967a8b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760252"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="e0492-102">FExecuteInAppDomainCallback-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="e0492-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="e0492-103">Verweist auf eine Funktion, die von der common Language Runtime (CLR) zum Ausführen von verwalteten Codes aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e0492-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="e0492-104">Dieser Funktionszeiger wurde in .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="e0492-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0492-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0492-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0492-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e0492-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="e0492-107">[in] Ein Zeiger auf nicht transparente, vom Aufrufer reservierte Arbeitsspeicher mit dem verwalteten Code ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e0492-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="e0492-108">Die Zuordnung und die Lebensdauer dieses Arbeitsspeichers werden vom Aufrufer (d. h. die CLR) gesteuert.</span><span class="sxs-lookup"><span data-stu-id="e0492-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="e0492-109">Dies ist kein CLR verwaltete Heap-Speicher.</span><span class="sxs-lookup"><span data-stu-id="e0492-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0492-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e0492-110">Requirements</span></span>  
 <span data-ttu-id="e0492-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0492-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0492-112">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e0492-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0492-113">**Bibliothek:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="e0492-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="e0492-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0492-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0492-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0492-115">See also</span></span>

- [<span data-ttu-id="e0492-116">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="e0492-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
