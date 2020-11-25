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
ms.openlocfilehash: f7aa9699e9929608c90020c6b2d66c301fc11955
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732709"
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="ccb37-102">CeeSectionRelocType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ccb37-102">CeeSectionRelocType Enumeration</span></span>

<span data-ttu-id="ccb37-103">Stellt Werte bereit, die den Typ der Anweisung beeinflussen, die `reloc` bei einem [callegen:: AddSectionReloc](iceegen-addsectionreloc-method.md)-Befehl ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ccb37-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccb37-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ccb37-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ccb37-105">Member</span><span class="sxs-lookup"><span data-stu-id="ccb37-105">Members</span></span>  
  
|<span data-ttu-id="ccb37-106">Member</span><span class="sxs-lookup"><span data-stu-id="ccb37-106">Member</span></span>|<span data-ttu-id="ccb37-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ccb37-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="ccb37-108">Generiert nur einen Abschnitt (relativ) `reloc` und sendet nichts an einen. reloc-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="ccb37-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="ccb37-109">Generiert einen `reloc` für einen Speicherort mit Zeiger Größen.</span><span class="sxs-lookup"><span data-stu-id="ccb37-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="ccb37-110">Dies wird abhängig von der Plattform in BASED_HIGHLOW oder BASED_DIR64 transformiert.</span><span class="sxs-lookup"><span data-stu-id="ccb37-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="ccb37-111">Generiert ein `reloc` -Wert für die oberen 16 Bits einer 32-Bit-Zahl, wobei die unteren 16 Bits im nächsten Wort in der reloc-Tabelle enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ccb37-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="ccb37-112">Generiert eine tokenzuordnungs-Verlagerung und sendet nichts an einen. reloc-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="ccb37-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="ccb37-113">Gibt an, dass der Wert ein relativer Adress Fixup ist.</span><span class="sxs-lookup"><span data-stu-id="ccb37-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="ccb37-114">Generiert nur einen Abschnitt (relativ) `reloc` und sendet nichts an einen. reloc-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="ccb37-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="ccb37-115">Dies `reloc` ist relativ zur Dateiposition des Abschnitts, nicht zur virtuellen Adresse des Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="ccb37-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="ccb37-116">Gibt einen Code relativen Adress Fixup an.</span><span class="sxs-lookup"><span data-stu-id="ccb37-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="ccb37-117">Generiert einen `reloc` für eine 64-Bit-Adresse in einer ia64- `movl` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ccb37-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="ccb37-118">Generiert einen `reloc` für eine 64-Bit-Adresse.</span><span class="sxs-lookup"><span data-stu-id="ccb37-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="ccb37-119">Generieren eines `reloc` für eine 25-Bit-PC-relative Adresse in einer ia64- `br.call` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ccb37-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="ccb37-120">Generiert einen `reloc` für eine 64-Bit-PC-relative Adresse in einer ia64- `brl.call` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ccb37-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="ccb37-121">Generiert einen 30-Bit-Abschnitt `reloc` , der für markierte Zeiger Werte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ccb37-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="ccb37-122">Ein Sentinelwert, mit dem sichergestellt wird, dass Ergänzungen zu dieser Enumeration dem internen namens Array widergespiegelt werden `reloc` .</span><span class="sxs-lookup"><span data-stu-id="ccb37-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="ccb37-123">Gibt an, dass keine Basis ausgegeben werden soll `reloc` .</span><span class="sxs-lookup"><span data-stu-id="ccb37-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="ccb37-124">Ein-Wert, der angibt, dass der vorfixupinhalt des Arbeitsspeichers ein Zeiger anstelle eines Abschnitts Offsets ist.</span><span class="sxs-lookup"><span data-stu-id="ccb37-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ccb37-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ccb37-125">Requirements</span></span>  

 <span data-ttu-id="ccb37-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccb37-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccb37-127">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ccb37-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ccb37-128">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ccb37-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ccb37-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccb37-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb37-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ccb37-130">See also</span></span>

- [<span data-ttu-id="ccb37-131">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="ccb37-131">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="ccb37-132">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ccb37-132">ICeeGen Interface</span></span>](iceegen-interface.md)
- [<span data-ttu-id="ccb37-133">AddSectionReloc-Methode</span><span class="sxs-lookup"><span data-stu-id="ccb37-133">AddSectionReloc Method</span></span>](iceegen-addsectionreloc-method.md)
