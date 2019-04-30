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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: adef1010d08561c0a0fe38480fe0d2f519a80b49
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993433"
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
|`ADDR_IL_OFFSET`|Gibt einen Microsoft intermediate Language (MSIL) lokale Variable oder Parameter Index an.|  
|`ADDR_NATIVE_RVA`|Gibt eine relative virtuelle Adresse in einem Modul an.|  
|`ADDR_NATIVE_REGISTER`|Gibt ein CPU-Register an.|  
|`ADDR_NATIVE_REGREL`|Gibt an, dass die erste Adresse ein Register ist und die zweite Adresse eine Abweichung ist.|  
|`ADDR_NATIVE_OFFSET`|Gibt an, ein Offset von einer Basisadresse.|  
|`ADDR_NATIVE_REGREG`|Gibt an, dass die erste Adresse der niedrige Teil eines Registers ist, und die zweite Adresse der hohe Teil ist.|  
|`ADDR_NATIVE_REGSTK`|Gibt an, dass die erste Adresse der niedrige Teil eines Registers ist, das zweite der hohe Teil ist, und die dritte ein Offset ist.|  
|`ADDR_NATIVE_STKREG`|Gibt an, dass die erste Adresse ein Register ist, die zweite ein Offset ist und der dritte der hohe Teil der Registrierung ist.|  
|`ADDR_BITFIELD`|Gibt an, dass die erste Adresse der Anfang eines Felds ist, und die zweite Adresse die Feldlänge stellt.|  
|`ADDR_NATIVE_ISECTOFFSET`|Gibt an, dass die erste Adresse der Abschnitt ist, und die zweite Adresse eine Abweichung ist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Enumerationen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
