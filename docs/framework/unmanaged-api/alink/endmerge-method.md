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
ms.openlocfilehash: e8f9eecd6d6d74717eb7c1e389bfa24e40afc950
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402573"
---
# <a name="endmerge-method"></a><span data-ttu-id="671c3-102">EndMerge-Methode</span><span class="sxs-lookup"><span data-stu-id="671c3-102">EndMerge Method</span></span>
<span data-ttu-id="671c3-103">Gibt an, dass alle benutzerdefinierten Attribute in den Bereich Emit zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="671c3-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="671c3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="671c3-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="671c3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="671c3-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="671c3-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="671c3-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="671c3-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="671c3-107">Return Value</span></span>  
 <span data-ttu-id="671c3-108">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="671c3-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="671c3-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="671c3-109">Requirements</span></span>  
 <span data-ttu-id="671c3-110">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="671c3-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="671c3-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="671c3-111">See Also</span></span>  
 [<span data-ttu-id="671c3-112">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="671c3-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="671c3-113">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="671c3-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="671c3-114">Alink-API</span><span class="sxs-lookup"><span data-stu-id="671c3-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
