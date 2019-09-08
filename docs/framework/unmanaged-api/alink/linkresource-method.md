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
ms.openlocfilehash: 763b7a776007c2ce8dac42c6a5f7f00f6eb58a10
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776947"
---
# <a name="linkresource-method"></a><span data-ttu-id="c9350-102">LinkResource-Methode</span><span class="sxs-lookup"><span data-stu-id="c9350-102">LinkResource Method</span></span>
<span data-ttu-id="c9350-103">Verknüpfungen in einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="c9350-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9350-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9350-104">Syntax</span></span>  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9350-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c9350-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c9350-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="c9350-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="c9350-107">Der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="c9350-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="c9350-108">Optionaler neuer Dateiname.</span><span class="sxs-lookup"><span data-stu-id="c9350-108">Optional new file name.</span></span> <span data-ttu-id="c9350-109">Wenn der Wert ungleich NULL `pszFileName` ist, wird in pszNewLocation kopiert.</span><span class="sxs-lookup"><span data-stu-id="c9350-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="c9350-110">Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="c9350-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c9350-111">Barrierefreiheits Flags wie `mrPublic` und `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="c9350-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="c9350-112">Dieser Parameter kann an die [DefineManifestResource-Methode](../metadata/imetadataassemblyemit-definemanifestresource-method.md)übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c9350-112">This parameter may be passed to [DefineManifestResource Method](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9350-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c9350-113">Return Value</span></span>  
 <span data-ttu-id="c9350-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="c9350-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9350-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c9350-115">Requirements</span></span>  
 <span data-ttu-id="c9350-116">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="c9350-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9350-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9350-117">See also</span></span>

- [<span data-ttu-id="c9350-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c9350-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c9350-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c9350-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c9350-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="c9350-120">ALink API</span></span>](index.md)
