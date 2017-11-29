---
title: CloseAssembly-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location: alink.dll
api_type: COM
f1_keywords: CloseAssembly
helpviewer_keywords: CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be68348b619f342eca4841a6052088bf7152f453
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="closeassembly-method"></a><span data-ttu-id="d85fc-102">CloseAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="d85fc-102">CloseAssembly Method</span></span>
<span data-ttu-id="d85fc-103">Schließt die Vorgänge der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="d85fc-103">Finalizes assembly operations.</span></span> <span data-ttu-id="d85fc-104">Rufen Sie diese Methode, bevor Sie beginnen, eine neue Assembly oder ein ungebundener Modul.</span><span class="sxs-lookup"><span data-stu-id="d85fc-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d85fc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d85fc-105">Syntax</span></span>  
  
```  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d85fc-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d85fc-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d85fc-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="d85fc-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d85fc-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d85fc-108">Return Value</span></span>  
 <span data-ttu-id="d85fc-109">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d85fc-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d85fc-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d85fc-110">Requirements</span></span>  
 <span data-ttu-id="d85fc-111">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="d85fc-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d85fc-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d85fc-112">See Also</span></span>  
 [<span data-ttu-id="d85fc-113">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d85fc-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="d85fc-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d85fc-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="d85fc-115">ALink-API</span><span class="sxs-lookup"><span data-stu-id="d85fc-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
