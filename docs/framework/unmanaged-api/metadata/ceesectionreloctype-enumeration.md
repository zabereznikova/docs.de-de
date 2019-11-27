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
# <a name="ceesectionreloctype-enumeration"></a>CeeSectionRelocType-Enumeration
Stellt Werte bereit, die den Typ der `reloc` Anweisung beeinflussen, die bei einem [callegen:: AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)-Befehl ausgegeben wird.  
  
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
  
## <a name="members"></a>Mitglieder  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`srRelocAbsolute`|Generiert nur einen Abschnitt relativer `reloc`und sendet nichts an einen. reloc-Abschnitt.|  
|`srRelocHighLow`|Generiert eine `reloc` für einen Speicherort mit Zeiger Größen. Dies wird abhängig von der Plattform in BASED_HIGHLOW oder BASED_DIR64 transformiert.|  
|`srRelocHighAdj`|Generiert eine `reloc` für die oberen 16 Bits einer 32-Bit-Zahl, wobei die unteren 16 Bits im nächsten Wort in der reloc-Tabelle enthalten sind.|  
|`srRelocMapToken`|Generiert eine tokenzuordnungs-Verlagerung und sendet nichts an einen. reloc-Abschnitt.|  
|`srRelocRelative`|Gibt an, dass der Wert ein relativer Adress Fixup ist.|  
|`srRelocFilePos`|Generiert nur einen Abschnitt relativer `reloc`und sendet nichts an einen. reloc-Abschnitt. Diese `reloc` ist relativ zur Dateiposition des Abschnitts, nicht zur virtuellen Adresse des Abschnitts.|  
|`srRelocCodeRelative`|Gibt einen Code relativen Adress Fixup an.|  
|`srRelocIA64Imm64`|Generiert eine `reloc` für eine 64-Bit-Adresse in einer ia64-`movl` Anweisung.|  
|`srRelocDir64`|Generiert eine `reloc` für eine 64-Bit-Adresse.|  
|`srRelocIA64PcRel25`|Generieren Sie eine `reloc` für eine 25-Bit-PC-relative Adresse in einer ia64-`br.call` Anweisung.|  
|`srRelocIA64PcRel64`|Generiert eine `reloc` für eine 64-Bit-PC-relative Adresse in einer ia64-`brl.call` Anweisung.|  
|`srRelocAbsoluteTagged`|Generiert einen 30-Bit-Abschnitt relativer `reloc`, der für markierte Zeiger Werte verwendet wird.|  
|`srRelocSentinel`|Ein Sentinelwert, mit dem sichergestellt wird, dass Ergänzungen zu dieser Enumeration dem internen `reloc` Namen Array widergespiegelt werden.|  
|`srNoBaseReloc`|Gibt an, dass keine Basis `reloc`ausgegeben werden soll.|  
|`srRelocPtr`|Ein-Wert, der angibt, dass der vorfixupinhalt des Arbeitsspeichers ein Zeiger anstelle eines Abschnitts Offsets ist.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [ICeeGen-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [AddSectionReloc-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
