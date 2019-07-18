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
ms.openlocfilehash: 1218ee76a3b7a2f501f87adf1e0bc8133d5329b5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781347"
---
# <a name="ceesectionreloctype-enumeration"></a>CeeSectionRelocType-Enumeration
Enthält Werte, um den Typ der beeinflussen `reloc` Anweisung ausgegeben wird, in einem Aufruf von [ICeeGen:: AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).  
  
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
|`srRelocAbsolute`|Generiert nur ein Abschnitt relativen `reloc`und sendet nichts in einen .reloc-Abschnitt.|  
|`srRelocHighLow`|Generiert eine `reloc` für einen Standort mit Zeigergröße. Dies ist abhängig von der Plattform in BASED_HIGHLOW oder BASED_DIR64 transformiert.|  
|`srRelocHighAdj`|Generiert eine `reloc` für den oberen 16 Bits des einer 32-Bit-Zahl, die, in dem die unteren 16 Bits in das nächste Wort in der .reloc-Tabelle enthalten sind.|  
|`srRelocMapToken`|Generiert eine tokenzuordnung Umsetzung "nothing" in einen .reloc-Abschnitt zu senden.|  
|`srRelocRelative`|Gibt an, dass der Wert eine Korrektur relative Adresse ist.|  
|`srRelocFilePos`|Generiert nur ein Abschnitt relativen `reloc`und sendet nichts in einen .reloc-Abschnitt. Dies `reloc` ist relativ zur Dateiposition des Abschnitts, nicht virtuelle Adresse des Abschnitts der.|  
|`srRelocCodeRelative`|Gibt ein Fixup Code Relative Adresse an.|  
|`srRelocIA64Imm64`|Generiert eine `reloc` für eine 64-Bit-Adresse in einer ia64 `movl` Anweisung.|  
|`srRelocDir64`|Generiert eine `reloc` für eine 64-Bit-Adresse.|  
|`srRelocIA64PcRel25`|Generieren einer `reloc` für eine 25-Bit-PC-Relative Adresse in einer ia64 `br.call` Anweisung.|  
|`srRelocIA64PcRel64`|Generiert eine `reloc` für eine 64-Bit-PC-Relative Adresse in einer ia64 `brl.call` Anweisung.|  
|`srRelocAbsoluteTagged`|Generiert eine 30-Bit-Abschnitt bezogene `reloc`, die für die markierte Zeigerwerte verwendet.|  
|`srRelocSentinel`|Einen Sentinelwert, um sicherzustellen, dass alle Hinzufügungen zu dieser Enumeration werden reflektiert, um die interne `reloc` Array von Namen.|  
|`srNoBaseReloc`|Gibt an, nicht, dass eine Basis ausgeben `reloc`.|  
|`srRelocPtr`|Ein Wert, der angibt, dass den Pre-Fixup-Inhalt des Arbeitsspeichers auf einen Zeiger anstelle eines Abschnitts sind Offset.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [ICeeGen-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [AddSectionReloc-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
