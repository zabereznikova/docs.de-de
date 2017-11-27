---
title: SetAssemblyFile2-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.SetAssemblyFile2
api_location: alink.dll
api_type: COM
f1_keywords: SetAssemblyFile2
helpviewer_keywords: SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7363a8f633d5f447f72e27ba03055f589564bdd2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="5e2f0-102">SetAssemblyFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="5e2f0-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="5e2f0-103">Legt den Namen und die Optionen für eine neue Assembly.</span><span class="sxs-lookup"><span data-stu-id="5e2f0-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="5e2f0-104">Rufen Sie diese Methode nicht, wenn Sie ungebundene Modulen erzeugen.</span><span class="sxs-lookup"><span data-stu-id="5e2f0-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e2f0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e2f0-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5e2f0-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5e2f0-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="5e2f0-107">Der Name der Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="5e2f0-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="5e2f0-108">[IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) -Schnittstelle für diese Datei.</span><span class="sxs-lookup"><span data-stu-id="5e2f0-108">[IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="5e2f0-109">Optionen durch dargestellt [AssemblyFlags-Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="5e2f0-109">Options represented by [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="5e2f0-110">Empfängt die eindeutige ID für die Assembly erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5e2f0-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e2f0-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5e2f0-111">Return Value</span></span>  
 <span data-ttu-id="5e2f0-112">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5e2f0-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e2f0-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5e2f0-113">Requirements</span></span>  
 <span data-ttu-id="5e2f0-114">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="5e2f0-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e2f0-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e2f0-115">See Also</span></span>  
 [<span data-ttu-id="5e2f0-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e2f0-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="5e2f0-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e2f0-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="5e2f0-118">ALink-API</span><span class="sxs-lookup"><span data-stu-id="5e2f0-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
