---
title: AssemblyFlags-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: AssemblyFlags
helpviewer_keywords: AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 605817ef23246f708b6cf46a93072cde3003ab43
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="da4a9-102">AssemblyFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="da4a9-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="da4a9-103">Enthält Werte, die Laufzeitfunktionen einer Assembly zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="da4a9-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da4a9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="da4a9-104">Syntax</span></span>  
  
```  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="da4a9-105">Member</span><span class="sxs-lookup"><span data-stu-id="da4a9-105">Members</span></span>  
  
|<span data-ttu-id="da4a9-106">Member</span><span class="sxs-lookup"><span data-stu-id="da4a9-106">Member</span></span>|<span data-ttu-id="da4a9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da4a9-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="da4a9-108">Gibt an, dass exportierte Typdefinitionen implizit in den Dateien, die die Assembly bilden.</span><span class="sxs-lookup"><span data-stu-id="da4a9-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="da4a9-109">In der .NET Framework-Versionen 1.0 und 1.1 wird immer davon ausgegangen, dass dieser Wert festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="da4a9-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="da4a9-110">Gibt an, dass Ressourcendefinitionen implizit in den Dateien, die die Assembly bilden.</span><span class="sxs-lookup"><span data-stu-id="da4a9-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="da4a9-111">In .NET Framework 1.0 und 1.1 wird immer davon ausgegangen, dass dieser Wert festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="da4a9-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="da4a9-112">Gibt an, dass die Assembly mit anderen Versionen ausgeführt werden kann, wenn sie in der gleichen Anwendungsdomäne ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="da4a9-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="da4a9-113">Gibt an, dass die Assembly mit anderen Versionen ausgeführt werden kann, wenn sie in demselben Prozess ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="da4a9-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="da4a9-114">Gibt an, dass die Assembly mit anderen Versionen ausgeführt werden kann, wenn sie auf dem gleichen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="da4a9-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da4a9-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="da4a9-115">Remarks</span></span>  
 <span data-ttu-id="da4a9-116">Die Werte zwischen 0 x 0010 und 0x0070, einschließlich werden verwendet, um Kompatibilitätsfeatures von Seite-an-Seite der referenzierten Assembly zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="da4a9-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="da4a9-117">Wenn keiner dieser Werte festgelegt sind, wird davon ausgegangen, dass die Assembly Seite-an-Seite-kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="da4a9-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da4a9-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="da4a9-118">Requirements</span></span>  
 <span data-ttu-id="da4a9-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da4a9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da4a9-120">**Header:** MsCorEE.h</span><span class="sxs-lookup"><span data-stu-id="da4a9-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="da4a9-121">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="da4a9-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="da4a9-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da4a9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da4a9-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da4a9-123">See Also</span></span>  
 [<span data-ttu-id="da4a9-124">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="da4a9-124">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="da4a9-125">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="da4a9-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
