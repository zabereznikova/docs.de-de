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
ms.openlocfilehash: e676547d20dc9535241150d24b65e1fbaf9e89ab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725104"
---
# <a name="coropenflags-enumeration"></a><span data-ttu-id="13aa7-102">CorOpenFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="13aa7-102">CorOpenFlags Enumeration</span></span>

<span data-ttu-id="13aa7-103">Enthält Flagwerte, die das Verhalten von Metadaten beim Öffnen von Manifestdateien steuern.</span><span class="sxs-lookup"><span data-stu-id="13aa7-103">Contains flag values that control metadata behavior upon opening manifest files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13aa7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13aa7-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="13aa7-105">Member</span><span class="sxs-lookup"><span data-stu-id="13aa7-105">Members</span></span>  
  
|<span data-ttu-id="13aa7-106">Member</span><span class="sxs-lookup"><span data-stu-id="13aa7-106">Member</span></span>|<span data-ttu-id="13aa7-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="13aa7-107">Description</span></span>|  
|------------|-----------------|  
|`ofRead`|<span data-ttu-id="13aa7-108">Gibt an, dass die Datei nur zum Lesen geöffnet werden darf.</span><span class="sxs-lookup"><span data-stu-id="13aa7-108">Indicates that the file should be opened for reading only.</span></span>|  
|`ofWrite`|<span data-ttu-id="13aa7-109">Gibt an, dass die Datei nur zum Schreiben geöffnet werden darf.</span><span class="sxs-lookup"><span data-stu-id="13aa7-109">Indicates that the file should be opened for writing.</span></span><br /><br /> <span data-ttu-id="13aa7-110">Wenn Sie beim Öffnen einer .winmd-Datei das `ofWrite`-Flag verwenden, sollten Sie auch das `ofNoTransform`-Flag übergeben.</span><span class="sxs-lookup"><span data-stu-id="13aa7-110">If you are using the `ofWrite` flag when opening a .winmd file, you should also pass the `ofNoTransform` flag.</span></span>|  
|`ofReadWriteMask`|<span data-ttu-id="13aa7-111">Eine Maske zum Lesen und Schreiben.</span><span class="sxs-lookup"><span data-stu-id="13aa7-111">A mask for reading and writing.</span></span>|  
|`ofCopyMemory`|<span data-ttu-id="13aa7-112">Gibt an, dass die Datei in den Arbeitsspeicher gelesen werden muss.</span><span class="sxs-lookup"><span data-stu-id="13aa7-112">Indicates that the file should be read into memory.</span></span> <span data-ttu-id="13aa7-113">Metadaten müssen eine eigene Kopie verwalten.</span><span class="sxs-lookup"><span data-stu-id="13aa7-113">Metadata should maintain its own copy.</span></span>|  
|`ofCacheImage`|<span data-ttu-id="13aa7-114">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="13aa7-114">Obsolete.</span></span> <span data-ttu-id="13aa7-115">Dieses Flag wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="13aa7-115">This flag is ignored.</span></span>|  
|`ofManifestMetadata`|<span data-ttu-id="13aa7-116">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="13aa7-116">Obsolete.</span></span> <span data-ttu-id="13aa7-117">Dieses Flag wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="13aa7-117">This flag is ignored.</span></span>|  
|`ofReadOnly`|<span data-ttu-id="13aa7-118">Gibt an, dass die Datei zum Lesen geöffnet werden soll, und dass ein Aufrufvorgang `QueryInterface` für eine [IMetaDataEmit](imetadataemit-interface.md) nicht erfolgen kann.</span><span class="sxs-lookup"><span data-stu-id="13aa7-118">Indicates that the file should be opened for reading, and that a call to `QueryInterface` for an [IMetaDataEmit](imetadataemit-interface.md) cannot be made.</span></span>|  
|`ofTakeOwnership`|<span data-ttu-id="13aa7-119">Gibt an, dass der Arbeitsspeicher mithilfe eines Aufrufes [cotaskmemzuordc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) zugewiesen wurde und von den Metadaten freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="13aa7-119">Indicates that the memory was allocated using a call to [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) and will be freed by the metadata.</span></span>|  
|`ofNoTypeLib`|<span data-ttu-id="13aa7-120">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="13aa7-120">Obsolete.</span></span> <span data-ttu-id="13aa7-121">Dieses Flag wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="13aa7-121">This flag is ignored.</span></span>|  
|`ofNoTransform`|<span data-ttu-id="13aa7-122">Gibt an, dass automatische Transformationen von .winmd-Dateien deaktiviert sein sollten.</span><span class="sxs-lookup"><span data-stu-id="13aa7-122">Indicates that automatic transforms of .winmd files should be disabled.</span></span> <span data-ttu-id="13aa7-123">Anders ausgedrückt: Die Projektion eines Windows Runtime-Typs auf einen .NET Framework-Typ sollte deaktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="13aa7-123">In other words, the projection of a Windows Runtime type to a .NET Framework type should be disabled.</span></span> <span data-ttu-id="13aa7-124">Weitere Informationen finden Sie unter [Windows-Runtime und die CLR-unter der Haube mit .net und der Windows-Runtime](/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime).</span><span class="sxs-lookup"><span data-stu-id="13aa7-124">For more information, see [Windows Runtime and the CLR - Underneath the Hood with .NET and the Windows Runtime](/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime).</span></span>|  
|`ofReserved1`|<span data-ttu-id="13aa7-125">Für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="13aa7-125">Reserved for internal use.</span></span>|  
|`ofReserved2`|<span data-ttu-id="13aa7-126">Für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="13aa7-126">Reserved for internal use.</span></span>|  
|`ofReserved`|<span data-ttu-id="13aa7-127">Für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="13aa7-127">Reserved for internal use.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13aa7-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="13aa7-128">Requirements</span></span>  

 <span data-ttu-id="13aa7-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13aa7-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13aa7-130">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="13aa7-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="13aa7-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13aa7-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13aa7-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="13aa7-132">See also</span></span>

- [<span data-ttu-id="13aa7-133">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="13aa7-133">Metadata Enumerations</span></span>](metadata-enumerations.md)
