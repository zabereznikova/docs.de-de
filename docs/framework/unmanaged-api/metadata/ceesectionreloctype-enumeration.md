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
ms.openlocfilehash: efce0c13944b383c42cbff6a6af4795293ee2989
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444158"
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="41aef-102">CeeSectionRelocType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="41aef-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="41aef-103">Stellt Werte bereit, die den Typ der `reloc` Anweisung beeinflussen, die bei einem [callegen:: AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)-Befehl ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="41aef-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41aef-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41aef-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="41aef-105">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="41aef-105">Members</span></span>  
  
|<span data-ttu-id="41aef-106">Member</span><span class="sxs-lookup"><span data-stu-id="41aef-106">Member</span></span>|<span data-ttu-id="41aef-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41aef-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="41aef-108">Generiert nur einen Abschnitt relativer `reloc`und sendet nichts an einen. reloc-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="41aef-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="41aef-109">Generiert eine `reloc` für einen Speicherort mit Zeiger Größen.</span><span class="sxs-lookup"><span data-stu-id="41aef-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="41aef-110">Dies wird abhängig von der Plattform in BASED_HIGHLOW oder BASED_DIR64 transformiert.</span><span class="sxs-lookup"><span data-stu-id="41aef-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="41aef-111">Generiert eine `reloc` für die oberen 16 Bits einer 32-Bit-Zahl, wobei die unteren 16 Bits im nächsten Wort in der reloc-Tabelle enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="41aef-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="41aef-112">Generiert eine tokenzuordnungs-Verlagerung und sendet nichts an einen. reloc-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="41aef-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="41aef-113">Gibt an, dass der Wert ein relativer Adress Fixup ist.</span><span class="sxs-lookup"><span data-stu-id="41aef-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="41aef-114">Generiert nur einen Abschnitt relativer `reloc`und sendet nichts an einen. reloc-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="41aef-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="41aef-115">Diese `reloc` ist relativ zur Dateiposition des Abschnitts, nicht zur virtuellen Adresse des Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="41aef-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="41aef-116">Gibt einen Code relativen Adress Fixup an.</span><span class="sxs-lookup"><span data-stu-id="41aef-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="41aef-117">Generiert eine `reloc` für eine 64-Bit-Adresse in einer ia64-`movl` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="41aef-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="41aef-118">Generiert eine `reloc` für eine 64-Bit-Adresse.</span><span class="sxs-lookup"><span data-stu-id="41aef-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="41aef-119">Generieren Sie eine `reloc` für eine 25-Bit-PC-relative Adresse in einer ia64-`br.call` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="41aef-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="41aef-120">Generiert eine `reloc` für eine 64-Bit-PC-relative Adresse in einer ia64-`brl.call` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="41aef-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="41aef-121">Generiert einen 30-Bit-Abschnitt relativer `reloc`, der für markierte Zeiger Werte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="41aef-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="41aef-122">Ein Sentinelwert, mit dem sichergestellt wird, dass Ergänzungen zu dieser Enumeration dem internen `reloc` Namen Array widergespiegelt werden.</span><span class="sxs-lookup"><span data-stu-id="41aef-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="41aef-123">Gibt an, dass keine Basis `reloc`ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="41aef-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="41aef-124">Ein-Wert, der angibt, dass der vorfixupinhalt des Arbeitsspeichers ein Zeiger anstelle eines Abschnitts Offsets ist.</span><span class="sxs-lookup"><span data-stu-id="41aef-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="41aef-125">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="41aef-125">Requirements</span></span>  
 <span data-ttu-id="41aef-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41aef-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41aef-127">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="41aef-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="41aef-128">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="41aef-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="41aef-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41aef-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41aef-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41aef-130">See also</span></span>

- [<span data-ttu-id="41aef-131">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="41aef-131">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="41aef-132">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41aef-132">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [<span data-ttu-id="41aef-133">AddSectionReloc-Methode</span><span class="sxs-lookup"><span data-stu-id="41aef-133">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
