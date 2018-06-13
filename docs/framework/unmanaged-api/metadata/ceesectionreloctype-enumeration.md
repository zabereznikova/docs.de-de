---
title: CeeSectionRelocType-Enumeration
ms.date: 03/30/2017
api_name:
- CeeSectionRelocType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocType
helpviewer_keywords:
- CeeSectionRelocType enumeration [.NET Framework metadata]
ms.assetid: 124656f6-0dad-4ceb-9043-d3869ab65cde
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: babd7d87f1bb6f238c347d68814a3ecdaef64b40
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442870"
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="fb997-102">CeeSectionRelocType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="fb997-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="fb997-103">Enthält Werte, um den Typ der beeinflussen `reloc` Anweisung ausgegeben, in einem Aufruf von [ICeeGen:: AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span><span class="sxs-lookup"><span data-stu-id="fb997-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb997-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb997-104">Syntax</span></span>  
  
```  
typedef enum  {  
    srRelocAbsolute,  
    srRelocHighLow          = 3,  
    srRelocHighAdj,       
    srRelocMapToken,  
    srRelocRelative,  
    srRelocFilePos,  
    srRelocCodeRelative,  
    srRelocIA64Imm64,  
    srRelocDir64,  
    srRelocIA64PcRel25,  
    srRelocIA64PcRel64,    srRelocAbsoluteTagged,    srRelocSentinel,    srNoBaseReloc       = 0x4000,  
    srRelocPtr          = 0x8000,  
    srRelocAbsolutePtr      = srRelocPtr + srRelocAbsolute,  
    srRelocHighLowPtr       = srRelocPtr + srRelocHighLow,  
    srRelocRelativePtr      = srRelocPtr + srRelocRelative,  
    srRelocIA64Imm64Ptr     = srRelocPtr + srRelocIA64Imm64,  
    srRelocDir64Ptr         = srRelocPtr + srRelocDir64  
    } CeeSectionRelocType;  
```  
  
## <a name="members"></a><span data-ttu-id="fb997-105">Member</span><span class="sxs-lookup"><span data-stu-id="fb997-105">Members</span></span>  
  
|<span data-ttu-id="fb997-106">Member</span><span class="sxs-lookup"><span data-stu-id="fb997-106">Member</span></span>|<span data-ttu-id="fb997-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb997-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="fb997-108">Generiert nur ein Abschnitt-relativer `reloc`und sendet nichts in einen .reloc-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="fb997-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="fb997-109">Generiert eine `reloc` für einen Standort mit Zeigergröße.</span><span class="sxs-lookup"><span data-stu-id="fb997-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="fb997-110">Dies ist abhängig von der Plattform in BASED_HIGHLOW oder BASED_DIR64 transformiert.</span><span class="sxs-lookup"><span data-stu-id="fb997-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="fb997-111">Generiert eine `reloc` für die oberen 16 Bits einer 32-Bit-Zahl, deren unteren 16 Bits in das nächste Wort in den .reloc-Tabelle enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="fb997-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="fb997-112">Generiert eine token Zuordnung Umsetzung sendet nichts in einen .reloc-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="fb997-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="fb997-113">Gibt an, dass der Wert eine Korrektur relative Adresse ist.</span><span class="sxs-lookup"><span data-stu-id="fb997-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="fb997-114">Generiert nur ein Abschnitt-relativer `reloc`und sendet nichts in einen .reloc-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="fb997-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="fb997-115">Dies `reloc` ist relativ zur Dateiposition des Abschnitts, nicht im Abschnitt virtuelle Adresse.</span><span class="sxs-lookup"><span data-stu-id="fb997-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="fb997-116">Gibt einen Fixup Code Relative Adresse an.</span><span class="sxs-lookup"><span data-stu-id="fb997-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="fb997-117">Generiert eine `reloc` für eine 64-Bit-Adresse in einer ia64 `movl` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="fb997-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="fb997-118">Generiert eine `reloc` für eine 64-Bit-Adresse.</span><span class="sxs-lookup"><span data-stu-id="fb997-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="fb997-119">Generieren einer `reloc` für ein 25-Bit-PC-Relative Adresse in einer ia64 `br.call` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="fb997-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="fb997-120">Generiert eine `reloc` für eine 64-Bit-PC-Relative Adresse in einer ia64 `brl.call` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="fb997-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="fb997-121">Generiert eine 30-Bit-Abschnitt-Relative `reloc`für markierte Zeigerwerte, verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb997-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="fb997-122">Ein Sentinelwert, um sicherzustellen, dass alle Ergänzungen für diese Enumeration sind reflektiert, um das interne `reloc` Namen Array.</span><span class="sxs-lookup"><span data-stu-id="fb997-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="fb997-123">Gibt an, nicht um eine Basis ausgeben `reloc`.</span><span class="sxs-lookup"><span data-stu-id="fb997-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="fb997-124">Ein Wert, der angibt, dass der Pre-Fixup-Inhalt des Arbeitsspeichers einen Zeiger anstelle von einem Abschnitt Offset.</span><span class="sxs-lookup"><span data-stu-id="fb997-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb997-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fb997-125">Requirements</span></span>  
 <span data-ttu-id="fb997-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb997-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb997-127">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fb997-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fb997-128">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fb997-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fb997-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb997-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb997-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb997-130">See Also</span></span>  
 [<span data-ttu-id="fb997-131">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="fb997-131">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="fb997-132">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb997-132">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)  
 [<span data-ttu-id="fb997-133">AddSectionReloc-Methode</span><span class="sxs-lookup"><span data-stu-id="fb997-133">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
