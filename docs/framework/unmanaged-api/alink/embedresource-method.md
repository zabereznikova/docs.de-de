---
title: EmbedResource-Methode
ms.date: 03/30/2017
api_name:
- IALink.EmbedResource
- EmbedResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmbedResource
helpviewer_keywords:
- EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: af5a200578c34464b5f8d86e568d08d814b46a29
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742149"
---
# <a name="embedresource-method"></a><span data-ttu-id="6e047-102">EmbedResource-Methode</span><span class="sxs-lookup"><span data-stu-id="6e047-102">EmbedResource Method</span></span>
<span data-ttu-id="6e047-103">Deklariert eine eingebettete Ressource.</span><span class="sxs-lookup"><span data-stu-id="6e047-103">Declares an embedded resource.</span></span> <span data-ttu-id="6e047-104">Diese Methode können Sie die Ressource nicht tatsächlich einbetten.</span><span class="sxs-lookup"><span data-stu-id="6e047-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e047-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e047-105">Syntax</span></span>  
  
```cpp  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e047-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6e047-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="6e047-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="6e047-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="6e047-108">Datei-Token "oder" Assembly-ID der Datei, die die Ressource enthält.</span><span class="sxs-lookup"><span data-stu-id="6e047-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="6e047-109">Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="6e047-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="6e047-110">Der Offset der Ressource von RVA.</span><span class="sxs-lookup"><span data-stu-id="6e047-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="6e047-111">Barrierefreiheit flags, z. B. `mrPublic` und `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="6e047-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="6e047-112">Diese Flags können übergeben werden, um [DefineExportedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="6e047-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e047-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6e047-113">Return Value</span></span>  
 <span data-ttu-id="6e047-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="6e047-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e047-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6e047-115">Requirements</span></span>  
 <span data-ttu-id="6e047-116">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="6e047-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e047-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e047-117">See also</span></span>

- [<span data-ttu-id="6e047-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e047-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="6e047-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e047-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="6e047-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="6e047-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
