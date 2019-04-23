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
ms.openlocfilehash: 6c6d298c84b801b87832c56026b05f647cb5a9dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135174"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="cfaf3-102">GetResolutionScope-Methode</span><span class="sxs-lookup"><span data-stu-id="cfaf3-102">GetResolutionScope Method</span></span>
<span data-ttu-id="cfaf3-103">Ruft den Bereich des angegebenen Typs ab.</span><span class="sxs-lookup"><span data-stu-id="cfaf3-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfaf3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cfaf3-104">Syntax</span></span>  
  
```  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfaf3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cfaf3-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="cfaf3-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="cfaf3-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="cfaf3-107">Datei, die ein Verweis erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="cfaf3-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="cfaf3-108">Token der Datei dieses Typs ist definiert in "," in der Regel mit abgerufen [ImportFile-Methode](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="cfaf3-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="cfaf3-109">Erhält die Assembly oder den Modulverweis.</span><span class="sxs-lookup"><span data-stu-id="cfaf3-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cfaf3-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cfaf3-110">Return Value</span></span>  
 <span data-ttu-id="cfaf3-111">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="cfaf3-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfaf3-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cfaf3-112">Requirements</span></span>  
 <span data-ttu-id="cfaf3-113">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="cfaf3-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfaf3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfaf3-114">See also</span></span>

- [<span data-ttu-id="cfaf3-115">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cfaf3-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="cfaf3-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cfaf3-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="cfaf3-117">Alink-API</span><span class="sxs-lookup"><span data-stu-id="cfaf3-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
