---
title: CorSymAddrKind-Enumeration
ms.date: 03/30/2017
api_name:
- CorSymAddrKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymAddrKind
helpviewer_keywords:
- CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type:
- apiref
ms.openlocfilehash: 5991b0abaedabe2337cd754c7bd19f96c5e9b685
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420616"
---
# <a name="corsymaddrkind-enumeration"></a>CorSymAddrKind-Enumeration
Gibt den Typ der Speicheradresse an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorSymAddrKind  
{  
    ADDR_IL_OFFSET          = 1,  
    ADDR_NATIVE_RVA         = 2,  
    ADDR_NATIVE_REGISTER    = 3,  
    ADDR_NATIVE_REGREL      = 4,  
    ADDR_NATIVE_OFFSET      = 5,  
    ADDR_NATIVE_REGREG      = 6,  
    ADDR_NATIVE_REGSTK      = 7,  
    ADDR_NATIVE_STKREG      = 8,  
    ADDR_BITFIELD           = 9,  
    ADDR_NATIVE_ISECTOFFSET = 10  
} CorSymAddrKind;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|Gibt eine lokale MSIL-Variable (Microsoft Intermediate Language) oder einen Parameter Index an.|  
|`ADDR_NATIVE_RVA`|Gibt eine relative virtuelle Adresse in einem Modul an.|  
|`ADDR_NATIVE_REGISTER`|Gibt ein CPU-Register an.|  
|`ADDR_NATIVE_REGREL`|Gibt an, dass die erste Adresse ein Register ist, und die zweite Adresse ist ein Offset.|  
|`ADDR_NATIVE_OFFSET`|Gibt einen Offset von einer Basisadresse an.|  
|`ADDR_NATIVE_REGREG`|Gibt an, dass die erste Adresse der niedrige Anteil eines Register ist, und die zweite Adresse ist der hohe Anteil.|  
|`ADDR_NATIVE_REGSTK`|Gibt an, dass die erste Adresse der niedrige Teil eines Registers ist, der zweite der hohe Anteil und der dritte ein Offset.|  
|`ADDR_NATIVE_STKREG`|Gibt an, dass die erste Adresse ein Register ist, der zweite ein Offset und der dritte der große Teil des Registers.|  
|`ADDR_BITFIELD`|Gibt an, dass die erste Adresse der Anfang eines Felds und die zweite Adresse die Feldlänge ist.|  
|`ADDR_NATIVE_ISECTOFFSET`|Gibt an, dass die erste Adresse der Abschnitt und die zweite Adresse ein Offset ist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Enumerationen](diagnostics-symbol-store-enumerations.md)
