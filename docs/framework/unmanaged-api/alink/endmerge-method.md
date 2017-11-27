---
title: EndMerge-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.EndMerge
- EndMerge
api_location: alink.dll
api_type: COM
f1_keywords: EndMerge
helpviewer_keywords: EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7f29abf03c636fc552fe550534ca1b1395b43aae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="endmerge-method"></a><span data-ttu-id="44948-102">EndMerge-Methode</span><span class="sxs-lookup"><span data-stu-id="44948-102">EndMerge Method</span></span>
<span data-ttu-id="44948-103">Gibt an, dass alle benutzerdefinierten Attribute in den Bereich Emit zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="44948-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44948-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="44948-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44948-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="44948-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="44948-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="44948-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44948-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="44948-107">Return Value</span></span>  
 <span data-ttu-id="44948-108">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="44948-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44948-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="44948-109">Requirements</span></span>  
 <span data-ttu-id="44948-110">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="44948-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44948-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44948-111">See Also</span></span>  
 [<span data-ttu-id="44948-112">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44948-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="44948-113">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44948-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="44948-114">ALink-API</span><span class="sxs-lookup"><span data-stu-id="44948-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
