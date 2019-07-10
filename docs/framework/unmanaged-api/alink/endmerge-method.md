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
ms.openlocfilehash: 8daf76e50b4c584115a55936aa9336c95a3669ec
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742079"
---
# <a name="endmerge-method"></a><span data-ttu-id="2ef65-102">EndMerge-Methode</span><span class="sxs-lookup"><span data-stu-id="2ef65-102">EndMerge Method</span></span>
<span data-ttu-id="2ef65-103">Gibt an, dass alle benutzerdefinierten Attribute mit dem Ausgabebereich zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="2ef65-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ef65-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ef65-104">Syntax</span></span>  
  
```cpp  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ef65-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ef65-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="2ef65-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="2ef65-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ef65-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2ef65-107">Return Value</span></span>  
 <span data-ttu-id="2ef65-108">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="2ef65-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ef65-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ef65-109">Requirements</span></span>  
 <span data-ttu-id="2ef65-110">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="2ef65-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ef65-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ef65-111">See also</span></span>

- [<span data-ttu-id="2ef65-112">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ef65-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="2ef65-113">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ef65-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="2ef65-114">Alink-API</span><span class="sxs-lookup"><span data-stu-id="2ef65-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
