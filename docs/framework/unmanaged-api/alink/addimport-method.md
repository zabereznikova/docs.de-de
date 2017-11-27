---
title: AddImport Methode1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- AddImport
- IALink.AddImport
api_location: alink.dll
api_type: COM
f1_keywords: AddImport
helpviewer_keywords: AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cd0e55cab6f0fdb7f971d7cf06e5703340e32307
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="addimport-method1"></a><span data-ttu-id="460e0-102">AddImport Methode1</span><span class="sxs-lookup"><span data-stu-id="460e0-102">AddImport Method1</span></span>
<span data-ttu-id="460e0-103">Importe und die Assembly hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="460e0-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="460e0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="460e0-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="460e0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="460e0-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="460e0-106">Eindeutige ID der Assembly, die erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="460e0-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="460e0-107">Eindeutige ID, die aus abgerufen [ImportFile-Methode](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), der zu importierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="460e0-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="460e0-108">COM+-FileDef-flags, z. B. `ffContainsNoMetaData` und `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="460e0-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="460e0-109">`dwFlags`wird zum übergeben [DefineFile-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="460e0-109">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="460e0-110">Zeiger auf Token, das die ID für die resultierende Datei empfängt.</span><span class="sxs-lookup"><span data-stu-id="460e0-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="460e0-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="460e0-111">Return Value</span></span>  
 <span data-ttu-id="460e0-112">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="460e0-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="460e0-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="460e0-113">Requirements</span></span>  
 <span data-ttu-id="460e0-114">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="460e0-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="460e0-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="460e0-115">See Also</span></span>  
 [<span data-ttu-id="460e0-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="460e0-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="460e0-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="460e0-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="460e0-118">ALink-API</span><span class="sxs-lookup"><span data-stu-id="460e0-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
