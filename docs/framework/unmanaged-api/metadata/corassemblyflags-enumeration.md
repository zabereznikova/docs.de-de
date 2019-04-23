---
title: CorAssemblyFlags-Enumeration
ms.date: 03/30/2017
api_name:
- CorAssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAssemblyFlags
helpviewer_keywords:
- CorAssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: bb8db3b6-d81d-49fc-b74c-dbc908a9eab9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eca4b66a3f7c1a96bb06827dde477f34cb904ba3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072713"
---
# <a name="corassemblyflags-enumeration"></a><span data-ttu-id="626d9-102">CorAssemblyFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="626d9-102">CorAssemblyFlags Enumeration</span></span>
<span data-ttu-id="626d9-103">Enthält Werte, die die auf eine Assemblykompilierung angewendeten Metadaten beschreiben.</span><span class="sxs-lookup"><span data-stu-id="626d9-103">Contains values that describe the metadata applied to an assembly compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="626d9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="626d9-104">Syntax</span></span>  
  
```  
typedef enum CorAssemblyFlags {  
  
    afPublicKey             =   0x0001,  
    afPA_None               =   0x0000,  
    afPA_MSIL               =   0x0010,  
    afPA_x86                =   0x0020,  
    afPA_IA64               =   0x0030,  
    afPA_AMD64              =   0x0040,  
    afPA_ARM                =   0x0050,  
    afPA_NoPlatform         =   0x0070,  
    afPA_Specified          =   0x0080,  
    afPA_Mask               =   0x0070,  
    afPA_FullMask           =   0x00F0,  
    afPA_Shift              =   0x0004,  
  
    afEnableJITcompileTracking  =   0x8000,  
    afDisableJITcompileOptimizer=   0x4000,  
  
    afRetargetable          =   0x0100,  
    afContentType_Default        =   0x0000,  
    afContentType_WindowsRuntime =   0x0200,  
    afContentType_Mask           =   0x0E00,  
  
} CorAssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="626d9-105">Member</span><span class="sxs-lookup"><span data-stu-id="626d9-105">Members</span></span>  
  
|<span data-ttu-id="626d9-106">Member</span><span class="sxs-lookup"><span data-stu-id="626d9-106">Member</span></span>|<span data-ttu-id="626d9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="626d9-107">Description</span></span>|  
|------------|-----------------|  
|`afPublicKey`|<span data-ttu-id="626d9-108">Gibt an, dass der Assemblyverweis auf den öffentlichen Schlüssel für vollständigen, nicht gehashte enthält.</span><span class="sxs-lookup"><span data-stu-id="626d9-108">Indicates that the assembly reference holds the full, unhashed public key.</span></span>|  
|`afPA_None`|<span data-ttu-id="626d9-109">Gibt an, dass die Prozessorarchitektur nicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="626d9-109">Indicates that the processor architecture is unspecified.</span></span>|  
|`afPA_MSIL`|<span data-ttu-id="626d9-110">Gibt an, dass die Prozessorarchitektur neutral ist (PE32).</span><span class="sxs-lookup"><span data-stu-id="626d9-110">Indicates that the processor architecture is neutral (PE32).</span></span>|  
|`afPA_x86`|<span data-ttu-id="626d9-111">Gibt an, dass die Prozessorarchitektur X86 (PE32) ist.</span><span class="sxs-lookup"><span data-stu-id="626d9-111">Indicates that the processor architecture is x86 (PE32).</span></span>|  
|`afPA_IA64`|<span data-ttu-id="626d9-112">Gibt an, dass die Prozessorarchitektur Itanium (PE32 +) ist.</span><span class="sxs-lookup"><span data-stu-id="626d9-112">Indicates that the processor architecture is Itanium (PE32+).</span></span>|  
|`afPA_AMD64`|<span data-ttu-id="626d9-113">Gibt an, dass die Prozessorarchitektur AMD X64 (PE32 +) ist.</span><span class="sxs-lookup"><span data-stu-id="626d9-113">Indicates that the processor architecture is AMD X64 (PE32+).</span></span>|  
|`afPA_ARM`|<span data-ttu-id="626d9-114">Gibt an, dass die Prozessorarchitektur ARM (PE32) ist.</span><span class="sxs-lookup"><span data-stu-id="626d9-114">Indicates that the processor architecture is ARM (PE32).</span></span>|  
|`afPA_NoPlatform`|<span data-ttu-id="626d9-115">Gibt an, dass die Assembly eine Verweisassembly; Das heißt, es gilt für jede Architektur, jedoch kann nicht auf jeder Architektur ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="626d9-115">Indicates that the assembly is a reference assembly; that is, it applies to any architecture but cannot run on any architecture.</span></span> <span data-ttu-id="626d9-116">Daher das Flag ist identisch mit `afPA_Mask`.</span><span class="sxs-lookup"><span data-stu-id="626d9-116">Thus, the flag is the same as `afPA_Mask`.</span></span>|  
|`afPA_Specified`|<span data-ttu-id="626d9-117">Gibt an, dass die Flags der Prozessorarchitektur soll, um weitergegeben werden die `AssemblyRef` Datensatz.</span><span class="sxs-lookup"><span data-stu-id="626d9-117">Indicates that the processor architecture flags should be propagated to the `AssemblyRef` record.</span></span>|  
|`afPA_Mask`|<span data-ttu-id="626d9-118">Eine Maske, die die Prozessorarchitektur beschreibt.</span><span class="sxs-lookup"><span data-stu-id="626d9-118">A mask that describes the processor architecture.</span></span>|  
|`afPA_FullMask`|<span data-ttu-id="626d9-119">Gibt an, dass die Beschreibung der Prozessorarchitektur enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="626d9-119">Specifies that the processor architecture description is included.</span></span>|  
|`afPA_Shift`|<span data-ttu-id="626d9-120">Gibt ein Verschiebungswert in die Flags der Prozessorarchitektur in und aus dem Index an.</span><span class="sxs-lookup"><span data-stu-id="626d9-120">Indicates a shift count in the processor architecture flags to and from the index.</span></span>|  
|`afEnableJITcompileTracking`|<span data-ttu-id="626d9-121">Gibt den entsprechenden Wert aus der <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> von der <xref:System.Diagnostics.DebuggableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="626d9-121">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afDisableJITcompileOptimizer`|<span data-ttu-id="626d9-122">Gibt den entsprechenden Wert aus der <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> von der <xref:System.Diagnostics.DebuggableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="626d9-122">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afRetargetable`|<span data-ttu-id="626d9-123">Gibt an, dass die Assembly zur Laufzeit auf eine Assembly von einem anderen Verleger umgeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="626d9-123">Indicates that the assembly can be retargeted at run time to an assembly from a different publisher.</span></span>|  
|`afContentType_Mask`|<span data-ttu-id="626d9-124">Eine Maske, die den Inhaltstyp beschreibt.</span><span class="sxs-lookup"><span data-stu-id="626d9-124">A mask that describes the content type.</span></span>|  
|`afContentType_Default`|<span data-ttu-id="626d9-125">Gibt den Standardinhaltstyp an.</span><span class="sxs-lookup"><span data-stu-id="626d9-125">Indicates the default content type.</span></span>|  
|`afContentType_WindowsRuntime`|<span data-ttu-id="626d9-126">Gibt an, die [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="626d9-126">Indicates the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] content type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="626d9-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="626d9-127">Requirements</span></span>  
 <span data-ttu-id="626d9-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="626d9-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="626d9-129">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="626d9-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="626d9-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="626d9-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="626d9-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="626d9-131">See also</span></span>

- [<span data-ttu-id="626d9-132">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="626d9-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
