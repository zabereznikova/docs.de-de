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
# <a name="ceesectionreloctype-enumeration"></a>CeeSectionRelocType-Enumeration
Enthält Werte, um den Typ der beeinflussen `reloc` Anweisung ausgegeben, in einem Aufruf von [ICeeGen:: AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).  
  
## <a name="syntax"></a>Syntax  
  
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
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`srRelocAbsolute`|Generiert nur ein Abschnitt-relativer `reloc`und sendet nichts in einen .reloc-Abschnitt.|  
|`srRelocHighLow`|Generiert eine `reloc` für einen Standort mit Zeigergröße. Dies ist abhängig von der Plattform in BASED_HIGHLOW oder BASED_DIR64 transformiert.|  
|`srRelocHighAdj`|Generiert eine `reloc` für die oberen 16 Bits einer 32-Bit-Zahl, deren unteren 16 Bits in das nächste Wort in den .reloc-Tabelle enthalten sind.|  
|`srRelocMapToken`|Generiert eine token Zuordnung Umsetzung sendet nichts in einen .reloc-Abschnitt.|  
|`srRelocRelative`|Gibt an, dass der Wert eine Korrektur relative Adresse ist.|  
|`srRelocFilePos`|Generiert nur ein Abschnitt-relativer `reloc`und sendet nichts in einen .reloc-Abschnitt. Dies `reloc` ist relativ zur Dateiposition des Abschnitts, nicht im Abschnitt virtuelle Adresse.|  
|`srRelocCodeRelative`|Gibt einen Fixup Code Relative Adresse an.|  
|`srRelocIA64Imm64`|Generiert eine `reloc` für eine 64-Bit-Adresse in einer ia64 `movl` Anweisung.|  
|`srRelocDir64`|Generiert eine `reloc` für eine 64-Bit-Adresse.|  
|`srRelocIA64PcRel25`|Generieren einer `reloc` für ein 25-Bit-PC-Relative Adresse in einer ia64 `br.call` Anweisung.|  
|`srRelocIA64PcRel64`|Generiert eine `reloc` für eine 64-Bit-PC-Relative Adresse in einer ia64 `brl.call` Anweisung.|  
|`srRelocAbsoluteTagged`|Generiert eine 30-Bit-Abschnitt-Relative `reloc`für markierte Zeigerwerte, verwendet.|  
|`srRelocSentinel`|Ein Sentinelwert, um sicherzustellen, dass alle Ergänzungen für diese Enumeration sind reflektiert, um das interne `reloc` Namen Array.|  
|`srNoBaseReloc`|Gibt an, nicht um eine Basis ausgeben `reloc`.|  
|`srRelocPtr`|Ein Wert, der angibt, dass der Pre-Fixup-Inhalt des Arbeitsspeichers einen Zeiger anstelle von einem Abschnitt Offset.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [ICeeGen-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)  
 [AddSectionReloc-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
