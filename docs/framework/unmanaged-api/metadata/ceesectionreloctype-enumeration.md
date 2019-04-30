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
ms.openlocfilehash: 882242da493c49a2e6aa09888e9503dcf2933589
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906138"
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="ec608-102">CeeSectionRelocType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ec608-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="ec608-103">Enthält Werte, um den Typ der beeinflussen `reloc` Anweisung ausgegeben wird, in einem Aufruf von [ICeeGen:: AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span><span class="sxs-lookup"><span data-stu-id="ec608-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec608-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec608-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ec608-105">Member</span><span class="sxs-lookup"><span data-stu-id="ec608-105">Members</span></span>  
  
|<span data-ttu-id="ec608-106">Member</span><span class="sxs-lookup"><span data-stu-id="ec608-106">Member</span></span>|<span data-ttu-id="ec608-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec608-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="ec608-108">Generiert nur ein Abschnitt relativen `reloc`und sendet nichts in einen .reloc-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="ec608-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="ec608-109">Generiert eine `reloc` für einen Standort mit Zeigergröße.</span><span class="sxs-lookup"><span data-stu-id="ec608-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="ec608-110">Dies ist abhängig von der Plattform in BASED_HIGHLOW oder BASED_DIR64 transformiert.</span><span class="sxs-lookup"><span data-stu-id="ec608-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="ec608-111">Generiert eine `reloc` für den oberen 16 Bits des einer 32-Bit-Zahl, die, in dem die unteren 16 Bits in das nächste Wort in der .reloc-Tabelle enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ec608-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="ec608-112">Generiert eine tokenzuordnung Umsetzung "nothing" in einen .reloc-Abschnitt zu senden.</span><span class="sxs-lookup"><span data-stu-id="ec608-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="ec608-113">Gibt an, dass der Wert eine Korrektur relative Adresse ist.</span><span class="sxs-lookup"><span data-stu-id="ec608-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="ec608-114">Generiert nur ein Abschnitt relativen `reloc`und sendet nichts in einen .reloc-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="ec608-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="ec608-115">Dies `reloc` ist relativ zur Dateiposition des Abschnitts, nicht virtuelle Adresse des Abschnitts der.</span><span class="sxs-lookup"><span data-stu-id="ec608-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="ec608-116">Gibt ein Fixup Code Relative Adresse an.</span><span class="sxs-lookup"><span data-stu-id="ec608-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="ec608-117">Generiert eine `reloc` für eine 64-Bit-Adresse in einer ia64 `movl` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ec608-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="ec608-118">Generiert eine `reloc` für eine 64-Bit-Adresse.</span><span class="sxs-lookup"><span data-stu-id="ec608-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="ec608-119">Generieren einer `reloc` für eine 25-Bit-PC-Relative Adresse in einer ia64 `br.call` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ec608-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="ec608-120">Generiert eine `reloc` für eine 64-Bit-PC-Relative Adresse in einer ia64 `brl.call` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ec608-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="ec608-121">Generiert eine 30-Bit-Abschnitt bezogene `reloc`, die für die markierte Zeigerwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="ec608-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="ec608-122">Einen Sentinelwert, um sicherzustellen, dass alle Hinzufügungen zu dieser Enumeration werden reflektiert, um die interne `reloc` Array von Namen.</span><span class="sxs-lookup"><span data-stu-id="ec608-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="ec608-123">Gibt an, nicht, dass eine Basis ausgeben `reloc`.</span><span class="sxs-lookup"><span data-stu-id="ec608-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="ec608-124">Ein Wert, der angibt, dass den Pre-Fixup-Inhalt des Arbeitsspeichers auf einen Zeiger anstelle eines Abschnitts sind Offset.</span><span class="sxs-lookup"><span data-stu-id="ec608-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ec608-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec608-125">Requirements</span></span>  
 <span data-ttu-id="ec608-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec608-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec608-127">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ec608-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ec608-128">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ec608-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ec608-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec608-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec608-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec608-130">See also</span></span>

- [<span data-ttu-id="ec608-131">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="ec608-131">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="ec608-132">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ec608-132">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [<span data-ttu-id="ec608-133">AddSectionReloc-Methode</span><span class="sxs-lookup"><span data-stu-id="ec608-133">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
