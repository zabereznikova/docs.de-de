---
title: CorOpenFlags-Enumeration
ms.date: 03/30/2017
api_name:
- CorOpenFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorOpenFlags
helpviewer_keywords:
- CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c08b1f6be41de63886115e5aed6bcad901658bb5
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509219"
---
# <a name="coropenflags-enumeration"></a><span data-ttu-id="e09c2-102">CorOpenFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e09c2-102">CorOpenFlags Enumeration</span></span>
<span data-ttu-id="e09c2-103">Enthält Flagwerte, die das Verhalten von Metadaten beim Öffnen von Manifestdateien steuern.</span><span class="sxs-lookup"><span data-stu-id="e09c2-103">Contains flag values that control metadata behavior upon opening manifest files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e09c2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e09c2-104">Syntax</span></span>  
  
```  
typedef enum CorOpenFlags  
{  
    ofRead              =   0x00000000,  
    ofWrite             =   0x00000001,  
    ofReadWriteMask     =   0x00000001,  
    ofCopyMemory        =   0x00000002,  
    ofCacheImage        =   0x00000004,  
    ofManifestMetadata  =   0x00000008,  
    ofReadOnly          =   0x00000010,  
    ofTakeOwnership     =   0x00000020,  
    ofCacheImage        =   0x00000004,  
    ofNoTypeLib         =   0x00000080,  
    ofNoTransform       =   0x00001000,  
    ofReserved1         =   0x00000100,  
    ofReserved2         =   0x00000200,  
    ofReserved          =   0xffffff40  
} CorOpenFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="e09c2-105">Member</span><span class="sxs-lookup"><span data-stu-id="e09c2-105">Members</span></span>  
  
|<span data-ttu-id="e09c2-106">Member</span><span class="sxs-lookup"><span data-stu-id="e09c2-106">Member</span></span>|<span data-ttu-id="e09c2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e09c2-107">Description</span></span>|  
|------------|-----------------|  
|`ofRead`|<span data-ttu-id="e09c2-108">Gibt an, dass die Datei nur zum Lesen geöffnet werden darf.</span><span class="sxs-lookup"><span data-stu-id="e09c2-108">Indicates that the file should be opened for reading only.</span></span>|  
|`ofWrite`|<span data-ttu-id="e09c2-109">Gibt an, dass die Datei nur zum Schreiben geöffnet werden darf.</span><span class="sxs-lookup"><span data-stu-id="e09c2-109">Indicates that the file should be opened for writing.</span></span><br /><br /> <span data-ttu-id="e09c2-110">Wenn Sie beim Öffnen einer .winmd-Datei das `ofWrite`-Flag verwenden, sollten Sie auch das `ofNoTransform`-Flag übergeben.</span><span class="sxs-lookup"><span data-stu-id="e09c2-110">If you are using the `ofWrite` flag when opening a .winmd file, you should also pass the `ofNoTransform` flag.</span></span>|  
|`ofReadWriteMask`|<span data-ttu-id="e09c2-111">Eine Maske zum Lesen und Schreiben.</span><span class="sxs-lookup"><span data-stu-id="e09c2-111">A mask for reading and writing.</span></span>|  
|`ofCopyMemory`|<span data-ttu-id="e09c2-112">Gibt an, dass die Datei in den Arbeitsspeicher gelesen werden muss.</span><span class="sxs-lookup"><span data-stu-id="e09c2-112">Indicates that the file should be read into memory.</span></span> <span data-ttu-id="e09c2-113">Metadaten müssen eine eigene Kopie verwalten.</span><span class="sxs-lookup"><span data-stu-id="e09c2-113">Metadata should maintain its own copy.</span></span>|  
|`ofCacheImage`|<span data-ttu-id="e09c2-114">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="e09c2-114">Obsolete.</span></span> <span data-ttu-id="e09c2-115">Dieses Flag wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="e09c2-115">This flag is ignored.</span></span>|  
|`ofManifestMetadata`|<span data-ttu-id="e09c2-116">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="e09c2-116">Obsolete.</span></span> <span data-ttu-id="e09c2-117">Dieses Flag wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="e09c2-117">This flag is ignored.</span></span>|  
|`ofReadOnly`|<span data-ttu-id="e09c2-118">Gibt an, dass die Datei zum Lesen und, die geöffnet werden darf einen Aufruf von `QueryInterface` für eine [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) kann nicht hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e09c2-118">Indicates that the file should be opened for reading, and that a call to `QueryInterface` for an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) cannot be made.</span></span>|  
|`ofTakeOwnership`|<span data-ttu-id="e09c2-119">Gibt an, dass der Speicher belegt wurde über einen Aufruf an [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) und von den Metadaten freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e09c2-119">Indicates that the memory was allocated using a call to [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) and will be freed by the metadata.</span></span>|  
|`ofNoTypeLib`|<span data-ttu-id="e09c2-120">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="e09c2-120">Obsolete.</span></span> <span data-ttu-id="e09c2-121">Dieses Flag wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="e09c2-121">This flag is ignored.</span></span>|  
|`ofNoTransform`|<span data-ttu-id="e09c2-122">Gibt an, dass automatische Umwandlungen von .winmd-Dateien deaktiviert sein sollten.</span><span class="sxs-lookup"><span data-stu-id="e09c2-122">Indicates that automatic transforms of .winmd files should be disabled.</span></span> <span data-ttu-id="e09c2-123">Anders ausgedrückt: Die Projektion eines Windows Runtime-Typs auf einen .NET Framework-Typ sollte deaktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="e09c2-123">In other words, the projection of a Windows Runtime type to a .NET Framework type should be disabled.</span></span> <span data-ttu-id="e09c2-124">Weitere Informationen finden Sie unter [darunter das System mit .NET und die Windows-Runtime](https://msdn.microsoft.com/magazine/jj651569.aspx).</span><span class="sxs-lookup"><span data-stu-id="e09c2-124">For more information, see [Underneath the Hood with .NET and the Windows Runtime](https://msdn.microsoft.com/magazine/jj651569.aspx).</span></span>|  
|`ofReserved1`|<span data-ttu-id="e09c2-125">Für die interne Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="e09c2-125">Reserved for internal use.</span></span>|  
|`ofReserved2`|<span data-ttu-id="e09c2-126">Für die interne Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="e09c2-126">Reserved for internal use.</span></span>|  
|`ofReserved`|<span data-ttu-id="e09c2-127">Für die interne Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="e09c2-127">Reserved for internal use.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e09c2-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e09c2-128">Requirements</span></span>  
 <span data-ttu-id="e09c2-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e09c2-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e09c2-130">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="e09c2-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e09c2-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e09c2-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e09c2-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e09c2-132">See Also</span></span>  
 [<span data-ttu-id="e09c2-133">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="e09c2-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
