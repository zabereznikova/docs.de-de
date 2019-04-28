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
ms.openlocfilehash: 020cc56126249b27a52387e6efa3aa10c83d9126
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789986"
---
# <a name="endmerge-method"></a><span data-ttu-id="833a3-102">EndMerge-Methode</span><span class="sxs-lookup"><span data-stu-id="833a3-102">EndMerge Method</span></span>
<span data-ttu-id="833a3-103">Gibt an, dass alle benutzerdefinierten Attribute mit dem Ausgabebereich zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="833a3-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="833a3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="833a3-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="833a3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="833a3-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="833a3-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="833a3-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="833a3-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="833a3-107">Return Value</span></span>  
 <span data-ttu-id="833a3-108">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="833a3-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="833a3-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="833a3-109">Requirements</span></span>  
 <span data-ttu-id="833a3-110">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="833a3-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="833a3-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="833a3-111">See also</span></span>

- [<span data-ttu-id="833a3-112">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="833a3-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="833a3-113">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="833a3-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="833a3-114">Alink-API</span><span class="sxs-lookup"><span data-stu-id="833a3-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
