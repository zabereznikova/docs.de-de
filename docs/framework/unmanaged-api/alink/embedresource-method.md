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
ms.openlocfilehash: eb1fc266c8451953c8b6a9c686f4a1c1951966e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405397"
---
# <a name="embedresource-method"></a><span data-ttu-id="4785e-102">EmbedResource-Methode</span><span class="sxs-lookup"><span data-stu-id="4785e-102">EmbedResource Method</span></span>
<span data-ttu-id="4785e-103">Deklariert eine eingebettete Ressource.</span><span class="sxs-lookup"><span data-stu-id="4785e-103">Declares an embedded resource.</span></span> <span data-ttu-id="4785e-104">Diese Methode können Sie die Ressource nicht tatsächlich einbetten.</span><span class="sxs-lookup"><span data-stu-id="4785e-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4785e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4785e-105">Syntax</span></span>  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4785e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4785e-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="4785e-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="4785e-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="4785e-108">Datei-Token oder Assembly-ID der Datei, die die Ressource enthält.</span><span class="sxs-lookup"><span data-stu-id="4785e-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="4785e-109">Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="4785e-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="4785e-110">Offset der Ressource RVA.</span><span class="sxs-lookup"><span data-stu-id="4785e-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="4785e-111">Eingabehilfen kennzeichnet, wie z. B. `mrPublic` und `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="4785e-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="4785e-112">Diese Flags übergeben werden können, um [DefineExportedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="4785e-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4785e-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4785e-113">Return Value</span></span>  
 <span data-ttu-id="4785e-114">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4785e-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4785e-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4785e-115">Requirements</span></span>  
 <span data-ttu-id="4785e-116">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="4785e-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4785e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4785e-117">See Also</span></span>  
 [<span data-ttu-id="4785e-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4785e-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="4785e-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4785e-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="4785e-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="4785e-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
