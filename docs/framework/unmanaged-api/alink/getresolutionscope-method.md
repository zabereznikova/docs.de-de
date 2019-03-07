---
title: GetResolutionScope-Methode
ms.date: 03/30/2017
api_name:
- IALink.GetResolutionScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetResolutionScope
helpviewer_keywords:
- GetResolutionScope method
ms.assetid: 5b48ca60-dacd-44b2-9979-4a5122f00812
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bfe06c1300a22757b363236454f4f494dab1978a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486796"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="3f11a-102">GetResolutionScope-Methode</span><span class="sxs-lookup"><span data-stu-id="3f11a-102">GetResolutionScope Method</span></span>
<span data-ttu-id="3f11a-103">Ruft den Bereich des angegebenen Typs ab.</span><span class="sxs-lookup"><span data-stu-id="3f11a-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f11a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f11a-104">Syntax</span></span>  
  
```  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f11a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3f11a-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3f11a-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="3f11a-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="3f11a-107">Datei, die ein Verweis erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="3f11a-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="3f11a-108">Token der Datei dieses Typs ist definiert in "," in der Regel mit abgerufen [ImportFile-Methode](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="3f11a-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="3f11a-109">Erhält die Assembly oder den Modulverweis.</span><span class="sxs-lookup"><span data-stu-id="3f11a-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f11a-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3f11a-110">Return Value</span></span>  
 <span data-ttu-id="3f11a-111">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="3f11a-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f11a-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3f11a-112">Requirements</span></span>  
 <span data-ttu-id="3f11a-113">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="3f11a-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f11a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f11a-114">See also</span></span>
- [<span data-ttu-id="3f11a-115">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3f11a-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="3f11a-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3f11a-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="3f11a-117">Alink-API</span><span class="sxs-lookup"><span data-stu-id="3f11a-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
