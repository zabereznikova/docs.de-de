---
title: EmbedResource-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.EmbedResource
- EmbedResource
api_location: alink.dll
api_type: COM
f1_keywords: EmbedResource
helpviewer_keywords: EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 815e4b6abbb56b0998a12c096f0ba7cb678778ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="embedresource-method"></a><span data-ttu-id="3d8b2-102">EmbedResource-Methode</span><span class="sxs-lookup"><span data-stu-id="3d8b2-102">EmbedResource Method</span></span>
<span data-ttu-id="3d8b2-103">Deklariert eine eingebettete Ressource.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-103">Declares an embedded resource.</span></span> <span data-ttu-id="3d8b2-104">Diese Methode können Sie die Ressource nicht tatsächlich einbetten.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d8b2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d8b2-105">Syntax</span></span>  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d8b2-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="3d8b2-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3d8b2-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="3d8b2-108">Datei-Token oder Assembly-ID der Datei, die die Ressource enthält.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="3d8b2-109">Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="3d8b2-110">Offset der Ressource RVA.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3d8b2-111">Eingabehilfen kennzeichnet, wie z. B. `mrPublic` und `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="3d8b2-112">Diese Flags übergeben werden können, um [DefineExportedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="3d8b2-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d8b2-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3d8b2-113">Return Value</span></span>  
 <span data-ttu-id="3d8b2-114">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d8b2-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3d8b2-115">Requirements</span></span>  
 <span data-ttu-id="3d8b2-116">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d8b2-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d8b2-117">See Also</span></span>  
 [<span data-ttu-id="3d8b2-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3d8b2-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="3d8b2-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3d8b2-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="3d8b2-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="3d8b2-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
