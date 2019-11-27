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
ms.openlocfilehash: 9e91d990a8f23335248043c59eb210e8c4155e3a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445629"
---
# <a name="linkresource-method"></a><span data-ttu-id="6d2c0-102">LinkResource-Methode</span><span class="sxs-lookup"><span data-stu-id="6d2c0-102">LinkResource Method</span></span>
<span data-ttu-id="6d2c0-103">Verknüpfungen in einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="6d2c0-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d2c0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d2c0-104">Syntax</span></span>  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d2c0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6d2c0-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="6d2c0-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="6d2c0-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="6d2c0-107">Der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="6d2c0-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="6d2c0-108">Optionaler neuer Dateiname.</span><span class="sxs-lookup"><span data-stu-id="6d2c0-108">Optional new file name.</span></span> <span data-ttu-id="6d2c0-109">Wenn der Wert nicht NULL ist, werden `pszFileName` in pszNewLocation kopiert.</span><span class="sxs-lookup"><span data-stu-id="6d2c0-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="6d2c0-110">Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="6d2c0-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="6d2c0-111">Barrierefreiheits Flags wie `mrPublic` und `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="6d2c0-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="6d2c0-112">Dieser Parameter kann an die [DefineManifestResource-Methode](../metadata/imetadataassemblyemit-definemanifestresource-method.md)übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="6d2c0-112">This parameter may be passed to [DefineManifestResource Method](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d2c0-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6d2c0-113">Return Value</span></span>  
 <span data-ttu-id="6d2c0-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="6d2c0-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d2c0-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6d2c0-115">Requirements</span></span>  
 <span data-ttu-id="6d2c0-116">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="6d2c0-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d2c0-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d2c0-117">See also</span></span>

- [<span data-ttu-id="6d2c0-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6d2c0-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="6d2c0-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6d2c0-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="6d2c0-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="6d2c0-120">ALink API</span></span>](index.md)
