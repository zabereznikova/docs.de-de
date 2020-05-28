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
ms.openlocfilehash: 78b30f624bd71234e8f1b56600b3a23d15fdf517
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006029"
---
# <a name="ceesectionreloctype-enumeration"></a>CeeSectionRelocType-Enumeration
Stellt Werte bereit, die den Typ der Anweisung beeinflussen, die `reloc` bei einem [callegen:: AddSectionReloc](iceegen-addsectionreloc-method.md)-Befehl ausgegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
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
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`srRelocAbsolute`|Generiert nur einen Abschnitt (relativ) `reloc` und sendet nichts an einen. reloc-Abschnitt.|  
|`srRelocHighLow`|Generiert einen `reloc` für einen Speicherort mit Zeiger Größen. Dies wird abhängig von der Plattform in BASED_HIGHLOW oder BASED_DIR64 transformiert.|  
|`srRelocHighAdj`|Generiert ein `reloc` -Wert für die oberen 16 Bits einer 32-Bit-Zahl, wobei die unteren 16 Bits im nächsten Wort in der reloc-Tabelle enthalten sind.|  
|`srRelocMapToken`|Generiert eine tokenzuordnungs-Verlagerung und sendet nichts an einen. reloc-Abschnitt.|  
|`srRelocRelative`|Gibt an, dass der Wert ein relativer Adress Fixup ist.|  
|`srRelocFilePos`|Generiert nur einen Abschnitt (relativ) `reloc` und sendet nichts an einen. reloc-Abschnitt. Dies `reloc` ist relativ zur Dateiposition des Abschnitts, nicht zur virtuellen Adresse des Abschnitts.|  
|`srRelocCodeRelative`|Gibt einen Code relativen Adress Fixup an.|  
|`srRelocIA64Imm64`|Generiert einen `reloc` für eine 64-Bit-Adresse in einer ia64- `movl` Anweisung.|  
|`srRelocDir64`|Generiert einen `reloc` für eine 64-Bit-Adresse.|  
|`srRelocIA64PcRel25`|Generieren eines `reloc` für eine 25-Bit-PC-relative Adresse in einer ia64- `br.call` Anweisung.|  
|`srRelocIA64PcRel64`|Generiert einen `reloc` für eine 64-Bit-PC-relative Adresse in einer ia64- `brl.call` Anweisung.|  
|`srRelocAbsoluteTagged`|Generiert einen 30-Bit-Abschnitt `reloc` , der für markierte Zeiger Werte verwendet wird.|  
|`srRelocSentinel`|Ein Sentinelwert, mit dem sichergestellt wird, dass Ergänzungen zu dieser Enumeration dem internen namens Array widergespiegelt werden `reloc` .|  
|`srNoBaseReloc`|Gibt an, dass keine Basis ausgegeben werden soll `reloc` .|  
|`srRelocPtr`|Ein-Wert, der angibt, dass der vorfixupinhalt des Arbeitsspeichers ein Zeiger anstelle eines Abschnitts Offsets ist.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](metadata-enumerations.md)
- [ICeeGen-Schnittstelle](iceegen-interface.md)
- [AddSectionReloc-Methode](iceegen-addsectionreloc-method.md)
