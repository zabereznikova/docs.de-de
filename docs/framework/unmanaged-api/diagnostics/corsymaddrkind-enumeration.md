---
title: CorSymAddrKind-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSymAddrKind
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSymAddrKind
helpviewer_keywords: CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 56bb55d9c9f85ae8f8112f16dcf552295699826d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corsymaddrkind-enumeration"></a>CorSymAddrKind-Enumeration
Gibt den Typ der Speicheradresse.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|`ADDR_IL_OFFSET`|Gibt einen Microsoft intermediate Language (MSIL) lokale Variablen oder Parameter Index an.|  
|`ADDR_NATIVE_RVA`|Gibt eine relative virtuelle Adresse in einem Modul an.|  
|`ADDR_NATIVE_REGISTER`|Gibt einen CPU-Register an.|  
|`ADDR_NATIVE_REGREL`|Gibt an, dass die erste Adresse eines Registers und die zweite Adresse ein Offset ist.|  
|`ADDR_NATIVE_OFFSET`|Gibt einen Offset von einer Basisadresse an.|  
|`ADDR_NATIVE_REGREG`|Gibt an, dass die erste Adresse der niedrigen Teil eines Registers ist und die zweite Adresse der hohe Bereich.|  
|`ADDR_NATIVE_REGSTK`|Gibt an, dass die erste Adresse der niedrigen Teil eines Registers ist, das zweite der hohe Bereich ist und das dritte ein Offset ist.|  
|`ADDR_NATIVE_STKREG`|Gibt an, dass die erste Adresse eines Registers, das zweite ein Offset ist, und der dritte der hohe Bereich des Registers ist.|  
|`ADDR_BITFIELD`|Gibt an, dass die erste Adresse der Anfang eines Felds ist und die zweite Adresse die Feldlänge ist.|  
|`ADDR_NATIVE_ISECTOFFSET`|Gibt an, dass die erste Adresse der Abschnitt ist und die zweite Adresse ein Offset ist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [Diagnosesymbolspeicher-Enumerationen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
