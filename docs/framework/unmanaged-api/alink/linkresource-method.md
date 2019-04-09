---
title: LinkResource-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e851c1bd56c0e9ece02fb06c0dcd9975a5b02ff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079434"
---
# <a name="linkresource-method"></a><span data-ttu-id="d649a-102">LinkResource-Methode</span><span class="sxs-lookup"><span data-stu-id="d649a-102">LinkResource Method</span></span>
<span data-ttu-id="d649a-103">Links in einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="d649a-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d649a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d649a-104">Syntax</span></span>  
  
```  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d649a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d649a-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d649a-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="d649a-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="d649a-107">Der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="d649a-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="d649a-108">Neuer Dateiname optional.</span><span class="sxs-lookup"><span data-stu-id="d649a-108">Optional new file name.</span></span> <span data-ttu-id="d649a-109">Wenn ungleich NULL, `pszFileName` PszNewLocation kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="d649a-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="d649a-110">Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="d649a-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d649a-111">Barrierefreiheit flags, z. B. `mrPublic` und `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="d649a-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="d649a-112">Dieser Parameter kann übergeben werden, um [DefineManifestResource-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="d649a-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d649a-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d649a-113">Return Value</span></span>  
 <span data-ttu-id="d649a-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="d649a-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d649a-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d649a-115">Requirements</span></span>  
 <span data-ttu-id="d649a-116">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="d649a-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d649a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d649a-117">See also</span></span>

- [<span data-ttu-id="d649a-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d649a-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="d649a-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d649a-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="d649a-120">ALink-API</span><span class="sxs-lookup"><span data-stu-id="d649a-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
