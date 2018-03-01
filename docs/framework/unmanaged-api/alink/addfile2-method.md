---
title: AddFile2-Methode
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
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dd04b8435c7296b1c7b097ab426d103adaa0e993
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="addfile2-method"></a><span data-ttu-id="9a79d-102">AddFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="9a79d-102">AddFile2 Method</span></span>
<span data-ttu-id="9a79d-103">Dateien hinzugefügt der Assembly.</span><span class="sxs-lookup"><span data-stu-id="9a79d-103">Adds files to the assembly.</span></span> <span data-ttu-id="9a79d-104">Kann auch zum Erstellen von ungebundener Modules verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9a79d-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a79d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a79d-105">Syntax</span></span>  
  
```  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a79d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9a79d-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="9a79d-107">Die ID für die Assembly, die die Datei hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="9a79d-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="9a79d-108">Der Name der Datei hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9a79d-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9a79d-109">COM+- `FileDef` kennzeichnet, wie z. B. `ffContainsNoMetaData` und `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="9a79d-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="9a79d-110">`dwFlags`wird zum übergeben [DefineFile-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="9a79d-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="9a79d-111">Schnittstelle zu [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9a79d-111">Interface to [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="9a79d-112">Empfängt die ID für die Datei hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="9a79d-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a79d-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9a79d-113">Return Value</span></span>  
 <span data-ttu-id="9a79d-114">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9a79d-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a79d-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a79d-115">Requirements</span></span>  
 <span data-ttu-id="9a79d-116">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="9a79d-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a79d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a79d-117">See Also</span></span>  
 [<span data-ttu-id="9a79d-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a79d-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="9a79d-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a79d-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="9a79d-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="9a79d-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
