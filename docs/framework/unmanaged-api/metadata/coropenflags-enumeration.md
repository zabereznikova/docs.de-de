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
ms.openlocfilehash: ad582fc2fd1bd1d2fc9d5a0d483fdb3a51309a10
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436508"
---
# <a name="coropenflags-enumeration"></a><span data-ttu-id="c554b-102">CorOpenFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c554b-102">CorOpenFlags Enumeration</span></span>
<span data-ttu-id="c554b-103">Enthält Flagwerte, die das Verhalten von Metadaten beim Öffnen von Manifestdateien steuern.</span><span class="sxs-lookup"><span data-stu-id="c554b-103">Contains flag values that control metadata behavior upon opening manifest files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c554b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c554b-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="c554b-105">Member</span><span class="sxs-lookup"><span data-stu-id="c554b-105">Members</span></span>  
  
|<span data-ttu-id="c554b-106">Member</span><span class="sxs-lookup"><span data-stu-id="c554b-106">Member</span></span>|<span data-ttu-id="c554b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c554b-107">Description</span></span>|  
|------------|-----------------|  
|`ofRead`|<span data-ttu-id="c554b-108">Gibt an, dass die Datei nur zum Lesen geöffnet werden darf.</span><span class="sxs-lookup"><span data-stu-id="c554b-108">Indicates that the file should be opened for reading only.</span></span>|  
|`ofWrite`|<span data-ttu-id="c554b-109">Gibt an, dass die Datei nur zum Schreiben geöffnet werden darf.</span><span class="sxs-lookup"><span data-stu-id="c554b-109">Indicates that the file should be opened for writing.</span></span><br /><br /> <span data-ttu-id="c554b-110">Wenn Sie beim Öffnen einer .winmd-Datei das `ofWrite`-Flag verwenden, sollten Sie auch das `ofNoTransform`-Flag übergeben.</span><span class="sxs-lookup"><span data-stu-id="c554b-110">If you are using the `ofWrite` flag when opening a .winmd file, you should also pass the `ofNoTransform` flag.</span></span>|  
|`ofReadWriteMask`|<span data-ttu-id="c554b-111">Eine Maske zum Lesen und Schreiben.</span><span class="sxs-lookup"><span data-stu-id="c554b-111">A mask for reading and writing.</span></span>|  
|`ofCopyMemory`|<span data-ttu-id="c554b-112">Gibt an, dass die Datei in den Arbeitsspeicher gelesen werden muss.</span><span class="sxs-lookup"><span data-stu-id="c554b-112">Indicates that the file should be read into memory.</span></span> <span data-ttu-id="c554b-113">Metadaten müssen eine eigene Kopie verwalten.</span><span class="sxs-lookup"><span data-stu-id="c554b-113">Metadata should maintain its own copy.</span></span>|  
|`ofCacheImage`|<span data-ttu-id="c554b-114">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="c554b-114">Obsolete.</span></span> <span data-ttu-id="c554b-115">Dieses Flag wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c554b-115">This flag is ignored.</span></span>|  
|`ofManifestMetadata`|<span data-ttu-id="c554b-116">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="c554b-116">Obsolete.</span></span> <span data-ttu-id="c554b-117">Dieses Flag wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c554b-117">This flag is ignored.</span></span>|  
|`ofReadOnly`|<span data-ttu-id="c554b-118">Gibt an, dass die Datei zum Lesen geöffnet werden soll, und dass kein `QueryInterface` für eine [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) -Datei aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c554b-118">Indicates that the file should be opened for reading, and that a call to `QueryInterface` for an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) cannot be made.</span></span>|  
|`ofTakeOwnership`|<span data-ttu-id="c554b-119">Gibt an, dass der Arbeitsspeicher mithilfe eines Aufrufes [cotaskmemzuordc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) zugewiesen wurde und von den Metadaten freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c554b-119">Indicates that the memory was allocated using a call to [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) and will be freed by the metadata.</span></span>|  
|`ofNoTypeLib`|<span data-ttu-id="c554b-120">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="c554b-120">Obsolete.</span></span> <span data-ttu-id="c554b-121">Dieses Flag wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c554b-121">This flag is ignored.</span></span>|  
|`ofNoTransform`|<span data-ttu-id="c554b-122">Gibt an, dass automatische Transformationen von .winmd-Dateien deaktiviert sein sollten.</span><span class="sxs-lookup"><span data-stu-id="c554b-122">Indicates that automatic transforms of .winmd files should be disabled.</span></span> <span data-ttu-id="c554b-123">Anders ausgedrückt: Die Projektion eines Windows Runtime-Typs auf einen .NET Framework-Typ sollte deaktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="c554b-123">In other words, the projection of a Windows Runtime type to a .NET Framework type should be disabled.</span></span> <span data-ttu-id="c554b-124">Weitere Informationen finden Sie unter [Windows-Runtime und die CLR-unter der Haube mit .net und der Windows-Runtime](https://docs.microsoft.com/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime).</span><span class="sxs-lookup"><span data-stu-id="c554b-124">For more information, see [Windows Runtime and the CLR - Underneath the Hood with .NET and the Windows Runtime](https://docs.microsoft.com/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime).</span></span>|  
|`ofReserved1`|<span data-ttu-id="c554b-125">Reserviert für interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="c554b-125">Reserved for internal use.</span></span>|  
|`ofReserved2`|<span data-ttu-id="c554b-126">Reserviert für interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="c554b-126">Reserved for internal use.</span></span>|  
|`ofReserved`|<span data-ttu-id="c554b-127">Reserviert für interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="c554b-127">Reserved for internal use.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c554b-128">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c554b-128">Requirements</span></span>  
 <span data-ttu-id="c554b-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c554b-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c554b-130">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="c554b-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c554b-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c554b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c554b-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c554b-132">See also</span></span>

- [<span data-ttu-id="c554b-133">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="c554b-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
