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
ms.openlocfilehash: 8d940cbdeddc7030c679fae8c8694bb3542123b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="precloseassembly-method"></a><span data-ttu-id="a3f19-102">PreCloseAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="a3f19-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="a3f19-103">Schließt die Assemblydatei an.</span><span class="sxs-lookup"><span data-stu-id="a3f19-103">Closes the assembly file.</span></span> <span data-ttu-id="a3f19-104">Rufen Sie diese Methode aus, schließen Sie alle anderen Dateien, jedoch vor dem Schließen der Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="a3f19-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="a3f19-105">Rufen Sie diese Methode nicht für ungebundenen Modulen.</span><span class="sxs-lookup"><span data-stu-id="a3f19-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3f19-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3f19-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3f19-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="a3f19-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a3f19-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="a3f19-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3f19-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a3f19-109">Return Value</span></span>  
 <span data-ttu-id="a3f19-110">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a3f19-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3f19-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a3f19-111">Requirements</span></span>  
 <span data-ttu-id="a3f19-112">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="a3f19-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f19-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3f19-113">See Also</span></span>  
 [<span data-ttu-id="a3f19-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3f19-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="a3f19-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3f19-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="a3f19-116">ALink-API</span><span class="sxs-lookup"><span data-stu-id="a3f19-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
