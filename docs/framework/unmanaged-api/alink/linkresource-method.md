---
title: LinkResource-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.LinkResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- LinkResource
helpviewer_keywords:
- LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b1ff38bf0017cf400d8f35f0ddf265f8628c82d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="linkresource-method"></a><span data-ttu-id="af18c-102">LinkResource-Methode</span><span class="sxs-lookup"><span data-stu-id="af18c-102">LinkResource Method</span></span>
<span data-ttu-id="af18c-103">Links in einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="af18c-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af18c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="af18c-104">Syntax</span></span>  
  
```  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af18c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="af18c-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="af18c-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="af18c-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="af18c-107">Der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="af18c-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="af18c-108">Neuen Dateinamen optional.</span><span class="sxs-lookup"><span data-stu-id="af18c-108">Optional new file name.</span></span> <span data-ttu-id="af18c-109">Wenn ungleich NULL, `pszFileName` in PszNewLocation kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="af18c-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="af18c-110">Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="af18c-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="af18c-111">Eingabehilfen kennzeichnet, wie z. B. `mrPublic` und `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="af18c-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="af18c-112">Dieser Parameter kann übergeben werden, um [DefineManifestResource-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="af18c-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af18c-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="af18c-113">Return Value</span></span>  
 <span data-ttu-id="af18c-114">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="af18c-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af18c-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af18c-115">Requirements</span></span>  
 <span data-ttu-id="af18c-116">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="af18c-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af18c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af18c-117">See Also</span></span>  
 [<span data-ttu-id="af18c-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af18c-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="af18c-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af18c-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="af18c-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="af18c-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
