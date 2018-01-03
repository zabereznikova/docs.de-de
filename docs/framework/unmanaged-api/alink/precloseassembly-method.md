---
title: PreCloseAssembly-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.PreCloseAssembly
api_location: alink.dll
api_type: COM
f1_keywords: PreCloseAssembly
helpviewer_keywords: PreCloseAssembly method
ms.assetid: 6d23ac54-15ea-4027-a172-9ebef43e8f56
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5a4d1f2eed036552ab17b6768b7b2d84f4a52c9c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="precloseassembly-method"></a><span data-ttu-id="d0c68-102">PreCloseAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="d0c68-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="d0c68-103">Schließt die Assemblydatei an.</span><span class="sxs-lookup"><span data-stu-id="d0c68-103">Closes the assembly file.</span></span> <span data-ttu-id="d0c68-104">Rufen Sie diese Methode aus, schließen Sie alle anderen Dateien, jedoch vor dem Schließen der Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="d0c68-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="d0c68-105">Rufen Sie diese Methode nicht für ungebundenen Modulen.</span><span class="sxs-lookup"><span data-stu-id="d0c68-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0c68-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0c68-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0c68-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="d0c68-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d0c68-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="d0c68-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0c68-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d0c68-109">Return Value</span></span>  
 <span data-ttu-id="d0c68-110">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d0c68-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0c68-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d0c68-111">Requirements</span></span>  
 <span data-ttu-id="d0c68-112">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="d0c68-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0c68-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0c68-113">See Also</span></span>  
 [<span data-ttu-id="d0c68-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d0c68-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="d0c68-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d0c68-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="d0c68-116">Alink-API</span><span class="sxs-lookup"><span data-stu-id="d0c68-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
