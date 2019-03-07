---
title: EndMerge-Methode
ms.date: 03/30/2017
api_name:
- IALink.EndMerge
- EndMerge
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EndMerge
helpviewer_keywords:
- EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d4b102485db0199f748f6c5b6c4ab40d21429e9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494410"
---
# <a name="endmerge-method"></a><span data-ttu-id="4eba8-102">EndMerge-Methode</span><span class="sxs-lookup"><span data-stu-id="4eba8-102">EndMerge Method</span></span>
<span data-ttu-id="4eba8-103">Gibt an, dass alle benutzerdefinierten Attribute mit dem Ausgabebereich zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="4eba8-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4eba8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4eba8-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4eba8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4eba8-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="4eba8-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="4eba8-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4eba8-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4eba8-107">Return Value</span></span>  
 <span data-ttu-id="4eba8-108">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="4eba8-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4eba8-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4eba8-109">Requirements</span></span>  
 <span data-ttu-id="4eba8-110">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="4eba8-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eba8-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4eba8-111">See also</span></span>
- [<span data-ttu-id="4eba8-112">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4eba8-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="4eba8-113">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4eba8-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="4eba8-114">Alink-API</span><span class="sxs-lookup"><span data-stu-id="4eba8-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
