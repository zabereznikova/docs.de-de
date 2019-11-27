---
title: AssemblyFlags-Enumeration
ms.date: 03/30/2017
api_name:
- AssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyFlags
helpviewer_keywords:
- AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type:
- apiref
ms.openlocfilehash: ffb5953c843a338b4548253457a0c3b1ca0c20f5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444299"
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="22f61-102">AssemblyFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="22f61-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="22f61-103">Enthält Werte, die Lauf Zeitfunktionen einer Assembly beschreiben.</span><span class="sxs-lookup"><span data-stu-id="22f61-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22f61-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="22f61-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="22f61-105">Member</span><span class="sxs-lookup"><span data-stu-id="22f61-105">Members</span></span>  
  
|<span data-ttu-id="22f61-106">Member</span><span class="sxs-lookup"><span data-stu-id="22f61-106">Member</span></span>|<span data-ttu-id="22f61-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="22f61-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="22f61-108">Gibt an, dass die exportierten Typdefinitionen in den Dateien implizit sind, aus denen die Assembly besteht.</span><span class="sxs-lookup"><span data-stu-id="22f61-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="22f61-109">In den .NET Framework Versionen 1,0 und 1,1 wird dieser Wert immer als festgelegt angenommen.</span><span class="sxs-lookup"><span data-stu-id="22f61-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="22f61-110">Gibt an, dass Ressourcen Definitionen in den Dateien implizit sind, aus denen die Assembly besteht.</span><span class="sxs-lookup"><span data-stu-id="22f61-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="22f61-111">In den .NET Framework 1,0 und 1,1 wird dieser Wert immer als festgelegt angenommen.</span><span class="sxs-lookup"><span data-stu-id="22f61-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="22f61-112">Gibt an, dass die Assembly nicht mit anderen Versionen ausgeführt werden kann, wenn Sie in derselben Anwendungsdomäne ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="22f61-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="22f61-113">Gibt an, dass die Assembly nicht mit anderen Versionen ausgeführt werden kann, wenn Sie in demselben Prozess ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="22f61-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="22f61-114">Gibt an, dass die Assembly nicht mit anderen Versionen ausgeführt werden kann, wenn Sie auf demselben Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="22f61-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22f61-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22f61-115">Remarks</span></span>  
 <span data-ttu-id="22f61-116">Die Werte zwischen 0x0010 und 0x0070, einschließlich, werden verwendet, um die parallelen Kompatibilitäts Features der Assembly zu beschreiben, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="22f61-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="22f61-117">Wenn keiner dieser Werte festgelegt wird, wird davon ausgegangen, dass die Assembly nebeneinander kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="22f61-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22f61-118">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="22f61-118">Requirements</span></span>  
 <span data-ttu-id="22f61-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22f61-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22f61-120">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="22f61-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="22f61-121">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="22f61-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="22f61-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22f61-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22f61-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22f61-123">See also</span></span>

- [<span data-ttu-id="22f61-124">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="22f61-124">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="22f61-125">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22f61-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
