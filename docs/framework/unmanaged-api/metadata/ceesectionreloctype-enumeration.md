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
# <a name="ceesectionreloctype-enumeration"></a>CeeSectionRelocType-Enumeration
Stellt Werte bereit, `reloc` um den Typ der Anweisung zu beeinflussen, die in einem Aufruf von [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)abgegeben wird.  
  
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
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`srRelocAbsolute`|Generiert nur einen `reloc`Abschnitt-Verwandten , der nichts in einen .reloc-Abschnitt sendet.|  
|`srRelocHighLow`|Generiert `reloc` eine für eine Position in Zeigergröße. Dies wird je nach Plattform in BASED_HIGHLOW oder BASED_DIR64 umgewandelt.|  
|`srRelocHighAdj`|Generiert `reloc` eine für die obersten 16 Bits einer 32-Bit-Zahl, wobei die unteren 16 Bits im nächsten Wort in der .reloc-Tabelle enthalten sind.|  
|`srRelocMapToken`|Generiert eine Tokenzuordnungsverlagerung, die nichts in einen .reloc-Abschnitt sendet.|  
|`srRelocRelative`|Gibt an, dass es sich bei dem Wert um eine relative Adresskorrektur handelt.|  
|`srRelocFilePos`|Generiert nur einen `reloc`Abschnitt-Verwandten , der nichts in einen .reloc-Abschnitt sendet. Dies `reloc` ist relativ zur Dateiposition des Abschnitts, nicht zur virtuellen Adresse des Abschnitts.|  
|`srRelocCodeRelative`|Gibt ein coderelatives Adressfixup an.|  
|`srRelocIA64Imm64`|Generiert `reloc` eine für eine 64-Bit-Adresse `movl` in einer ia64-Anweisung.|  
|`srRelocDir64`|Generiert `reloc` eine für eine 64-Bit-Adresse.|  
|`srRelocIA64PcRel25`|Generieren `reloc` Sie eine für eine 25-Bit-PC-relative `br.call` Adresse in einer ia64-Anweisung.|  
|`srRelocIA64PcRel64`|Generiert `reloc` eine für eine 64-Bit-PC-relative Adresse `brl.call` in einer ia64-Anweisung.|  
|`srRelocAbsoluteTagged`|Generiert einen 30-Bit-Abschnittsrelativ, `reloc`der für markierte Zeigerwerte verwendet wird.|  
|`srRelocSentinel`|Ein Sentinelwert, mit dem sichergestellt werden soll, dass `reloc` alle Hinzufügungen zu dieser Enumerat im internen Namensarray widergespiegelt werden.|  
|`srNoBaseReloc`|Gibt an, keine Basis `reloc`auszusenden.|  
|`srRelocPtr`|Ein Wert, der angibt, dass der Vorfixupinhalt des Speichers ein Zeiger und kein Abschnittsversatz ist.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [ICeeGen-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [AddSectionReloc-Methode](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
