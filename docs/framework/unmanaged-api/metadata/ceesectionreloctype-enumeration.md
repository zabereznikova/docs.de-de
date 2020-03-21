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
ms.openlocfilehash: 44a84e0752eecc1c694f3b8cf6e568b72b7d0f5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176213"
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="6bd3f-102">CeeSectionRelocType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6bd3f-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="6bd3f-103">Stellt Werte bereit, `reloc` um den Typ der Anweisung zu beeinflussen, die in einem Aufruf von [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)abgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6bd3f-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bd3f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6bd3f-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="6bd3f-105">Members</span><span class="sxs-lookup"><span data-stu-id="6bd3f-105">Members</span></span>  
  
|<span data-ttu-id="6bd3f-106">Member</span><span class="sxs-lookup"><span data-stu-id="6bd3f-106">Member</span></span>|<span data-ttu-id="6bd3f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6bd3f-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="6bd3f-108">Generiert nur einen `reloc`Abschnitt-Verwandten , der nichts in einen .reloc-Abschnitt sendet.</span><span class="sxs-lookup"><span data-stu-id="6bd3f-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="6bd3f-109">Generiert `reloc` eine für eine Position in Zeigergröße.</span><span class="sxs-lookup"><span data-stu-id="6bd3f-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="6bd3f-110">Dies wird je nach Plattform in BASED_HIGHLOW oder BASED_DIR64 umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="6bd3f-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="6bd3f-111">Generiert `reloc` eine für die obersten 16 Bits einer 32-Bit-Zahl, wobei die unteren 16 Bits im nächsten Wort in der .reloc-Tabelle enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="6bd3f-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="6bd3f-112">Generiert eine Tokenzuordnungsverlagerung, die nichts in einen .reloc-Abschnitt sendet.</span><span class="sxs-lookup"><span data-stu-id="6bd3f-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="6bd3f-113">Gibt an, dass es sich bei dem Wert um eine relative Adresskorrektur handelt.</span><span class="sxs-lookup"><span data-stu-id="6bd3f-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="6bd3f-114">Generiert nur einen `reloc`Abschnitt-Verwandten , der nichts in einen .reloc-Abschnitt sendet.</span><span class="sxs-lookup"><span data-stu-id="6bd3f-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="6bd3f-115">Dies `reloc` ist relativ zur Dateiposition des Abschnitts, nicht zur virtuellen Adresse des Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="6bd3f-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="6bd3f-116">Gibt ein coderelatives Adressfixup an.</span><span class="sxs-lookup"><span data-stu-id="6bd3f-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="6bd3f-117">Generiert `reloc` eine für eine 64-Bit-Adresse `movl` in einer ia64-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6bd3f-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="6bd3f-118">Generiert `reloc` eine für eine 64-Bit-Adresse.</span><span class="sxs-lookup"><span data-stu-id="6bd3f-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="6bd3f-119">Generieren `reloc` Sie eine für eine 25-Bit-PC-relative `br.call` Adresse in einer ia64-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6bd3f-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="6bd3f-120">Generiert `reloc` eine für eine 64-Bit-PC-relative Adresse `brl.call` in einer ia64-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6bd3f-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="6bd3f-121">Generiert einen 30-Bit-Abschnittsrelativ, `reloc`der für markierte Zeigerwerte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6bd3f-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="6bd3f-122">Ein Sentinelwert, mit dem sichergestellt werden soll, dass `reloc` alle Hinzufügungen zu dieser Enumerat im internen Namensarray widergespiegelt werden.</span><span class="sxs-lookup"><span data-stu-id="6bd3f-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="6bd3f-123">Gibt an, keine Basis `reloc`auszusenden.</span><span class="sxs-lookup"><span data-stu-id="6bd3f-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="6bd3f-124">Ein Wert, der angibt, dass der Vorfixupinhalt des Speichers ein Zeiger und kein Abschnittsversatz ist.</span><span class="sxs-lookup"><span data-stu-id="6bd3f-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6bd3f-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6bd3f-125">Requirements</span></span>  
 <span data-ttu-id="6bd3f-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bd3f-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bd3f-127">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6bd3f-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6bd3f-128">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6bd3f-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6bd3f-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bd3f-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bd3f-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6bd3f-130">See also</span></span>

- [<span data-ttu-id="6bd3f-131">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="6bd3f-131">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="6bd3f-132">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6bd3f-132">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [<span data-ttu-id="6bd3f-133">AddSectionReloc-Methode</span><span class="sxs-lookup"><span data-stu-id="6bd3f-133">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
