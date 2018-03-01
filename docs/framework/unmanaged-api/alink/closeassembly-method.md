---
title: CloseAssembly-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseAssembly
helpviewer_keywords:
- CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 160ec53440f4ecdb924537c732a367881e75acf9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="closeassembly-method"></a><span data-ttu-id="bd66f-102">CloseAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="bd66f-102">CloseAssembly Method</span></span>
<span data-ttu-id="bd66f-103">Schließt die Vorgänge der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="bd66f-103">Finalizes assembly operations.</span></span> <span data-ttu-id="bd66f-104">Rufen Sie diese Methode, bevor Sie beginnen, eine neue Assembly oder ein ungebundener Modul.</span><span class="sxs-lookup"><span data-stu-id="bd66f-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd66f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd66f-105">Syntax</span></span>  
  
```  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd66f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="bd66f-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="bd66f-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="bd66f-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd66f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bd66f-108">Return Value</span></span>  
 <span data-ttu-id="bd66f-109">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bd66f-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd66f-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bd66f-110">Requirements</span></span>  
 <span data-ttu-id="bd66f-111">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="bd66f-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd66f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd66f-112">See Also</span></span>  
 [<span data-ttu-id="bd66f-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd66f-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="bd66f-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd66f-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="bd66f-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="bd66f-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
