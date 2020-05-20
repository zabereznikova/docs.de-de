---
title: ESymbolReadingPolicy-Enumeration
ms.date: 03/30/2017
api_name:
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
ms.openlocfilehash: 5c3d1d0ebc56ee93c950afb4f015c8e10ec6a0f7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616176"
---
# <a name="esymbolreadingpolicy-enumeration"></a>ESymbolReadingPolicy-Enumeration
Enthält Werte, mit denen die Richtlinie zum Lesen von Programm Datenbankdateien (PDB) festgelegt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`eSymbolReadingAlways`|Gibt an, dass der Debugger immer PDB-Dateien lesen soll.|  
|`eSymbolReadingFullTrustOnly`|Gibt an, dass der Debugger nur PDB-Dateien lesen soll, die mit vollständig vertrauenswürdigen Assemblys verknüpft sind.|  
|`eSymbolReadingNever`|Gibt an, dass der Debugger niemals PDB-Dateien lesen soll.|  
  
## <a name="remarks"></a>Hinweise  
 Die- `ESymbolReadingPolicy` Enumeration wird mit der [ICLRDebugManager:: setsymbolleserpolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md) -Methode verwendet.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Enumerationen](hosting-enumerations.md)
