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
ms.openlocfilehash: e67a71c25c0ae8ee7c54fae2e38d1116a5d92eff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402586"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="22380-102">GetResolutionScope-Methode</span><span class="sxs-lookup"><span data-stu-id="22380-102">GetResolutionScope Method</span></span>
<span data-ttu-id="22380-103">Ruft den Bereich eines bestimmten Typs ab.</span><span class="sxs-lookup"><span data-stu-id="22380-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22380-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="22380-104">Syntax</span></span>  
  
```  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="22380-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="22380-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="22380-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="22380-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="22380-107">Datei, die ein Verweis erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="22380-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="22380-108">Token der Datei dieses Typs definiert ist, in der Regel mit abgerufen [ImportFile-Methode](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="22380-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="22380-109">Erhält die Assembly oder Modulverweis.</span><span class="sxs-lookup"><span data-stu-id="22380-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22380-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="22380-110">Return Value</span></span>  
 <span data-ttu-id="22380-111">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="22380-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22380-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="22380-112">Requirements</span></span>  
 <span data-ttu-id="22380-113">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="22380-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22380-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22380-114">See Also</span></span>  
 [<span data-ttu-id="22380-115">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22380-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="22380-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22380-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="22380-117">Alink-API</span><span class="sxs-lookup"><span data-stu-id="22380-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
