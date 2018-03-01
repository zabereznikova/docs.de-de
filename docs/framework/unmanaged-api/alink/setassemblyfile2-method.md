---
title: SetAssemblyFile2-Methode
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
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 671fb857015a5babd388366066d282cb87462c18
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="1ee7f-102">SetAssemblyFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="1ee7f-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="1ee7f-103">Legt den Namen und die Optionen für eine neue Assembly.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="1ee7f-104">Rufen Sie diese Methode nicht, wenn Sie ungebundene Modulen erzeugen.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ee7f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ee7f-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1ee7f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1ee7f-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="1ee7f-107">Der Name der Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="1ee7f-108">[IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) -Schnittstelle für diese Datei.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-108">[IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="1ee7f-109">Optionen durch dargestellt [AssemblyFlags-Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="1ee7f-109">Options represented by [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="1ee7f-110">Empfängt die eindeutige ID für die Assembly erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ee7f-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1ee7f-111">Return Value</span></span>  
 <span data-ttu-id="1ee7f-112">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ee7f-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1ee7f-113">Requirements</span></span>  
 <span data-ttu-id="1ee7f-114">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ee7f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ee7f-115">See Also</span></span>  
 [<span data-ttu-id="1ee7f-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ee7f-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="1ee7f-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ee7f-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="1ee7f-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="1ee7f-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
