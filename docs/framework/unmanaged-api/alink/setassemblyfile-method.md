---
title: SetAssemblyFile-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.SetAssemblyFile
api_location: alink.dll
api_type: COM
f1_keywords: SetAssemblyFile
helpviewer_keywords: SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d83062db41b5fa1485555de40be0a39a65e0459a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="bb18d-102">SetAssemblyFile-Methode</span><span class="sxs-lookup"><span data-stu-id="bb18d-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="bb18d-103">Weist den Namen der Assembly erstellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bb18d-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="bb18d-104">Nicht zur Verwendung beim Erstellen von ungebundener Modules.</span><span class="sxs-lookup"><span data-stu-id="bb18d-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb18d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb18d-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb18d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="bb18d-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="bb18d-107">Vollständig qualifizierte Name der Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="bb18d-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="bb18d-108">Zeiger auf [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="bb18d-108">Pointer to [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="bb18d-109">Flags gemäß [AssemblyFlags-Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="bb18d-109">Flags as defined in [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="bb18d-110">Ein Zeiger auf die ID des sich ergebenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="bb18d-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb18d-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bb18d-111">Return Value</span></span>  
 <span data-ttu-id="bb18d-112">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bb18d-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb18d-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb18d-113">Requirements</span></span>  
 <span data-ttu-id="bb18d-114">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="bb18d-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb18d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb18d-115">See Also</span></span>  
 [<span data-ttu-id="bb18d-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb18d-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="bb18d-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb18d-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="bb18d-118">ALink-API</span><span class="sxs-lookup"><span data-stu-id="bb18d-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
