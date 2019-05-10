---
title: COR_IL_MAP-Struktur
ms.date: 03/30/2017
api_name:
- COR_IL_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_IL_MAP
helpviewer_keywords:
- COR_IL_MAP structure [.NET Framework debugging]
ms.assetid: 534ebc17-963d-4b26-8375-8cd940281db3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02a7bff021387f615c823b2df96615c1284cb82b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617715"
---
# <a name="corilmap-structure"></a>COR_IL_MAP-Struktur
Gibt Änderungen im relativen Offset einer Funktion an.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`oldOffset`|Die alten Microsoft intermediate Language (MSIL) offset relativ zum Anfang der Funktion.|  
|`newOffset`|Der neue MSIL-Offset relativ zum Anfang der Funktion.|  
|`fAccurate`|`true` Wenn die Zuordnung als genau bekannt wird; andernfalls `false`.|  
  
## <a name="remarks"></a>Hinweise  
 Das Format der Karte sieht folgendermaßen aus: Der Debugger geht davon aus, die `oldOffset` verweist auf einen MSIL-Offset innerhalb der ursprünglichen, unveränderten MSIL-Code. Die `newOffset` Parameter verweist auf die entsprechenden MSIL-Offset innerhalb der neuen, instrumentierten Code.  
  
 Für die schrittweise Ausführung, um ordnungsgemäß zu arbeiten, sollten die folgenden Anforderungen erfüllt sein:  
  
- Die Karte sollten in aufsteigender Reihenfolge sortiert werden.  
  
- Instrumentierter MSIL-Code muss nicht neu angeordnet werden.  
  
- Ursprüngliche MSIL-Code sollte nicht entfernt werden.  
  
- Die Zuordnung sollte Einträge zum Zuordnen der Sequenzpunkte über die Programmdatenbankdatei (PDB) enthalten.  
  
 Die Zuordnung wird nicht fehlenden Einträge interpoliert. Das folgende Beispiel zeigt eine Zuordnung und ihre Ergebnisse.  
  
 Ordnen Sie:  
  
- 0 alte Offset, 0 neue offset  
  
- 5 alte Offset, 10 neuen offset  
  
- 9 alte Offset, 20 neue offset  
  
 Ergebnisse:  
  
- Ein Alter Offset von 0, 1, 2, 3 oder 4 wird ein neuer Offset 0 zugeordnet werden.  
  
- Ein Alter Offset von 5, 6, 7 oder 8 wird zum neuen Offset 10 zugeordnet werden.  
  
- Ein Alter Offset des 9 oder höher wird zum neuen Offset 20 zugeordnet werden.  
  
- Ein neuer Offset von 0, 1, 2, 3, 4, 5, 6, 7, 8 oder 9 werden alte Offset 0 zugeordnet werden.  
  
- Alte Offset 5 wird ein neuer Offset von 10, 11, 12, 13, 14, 15, 16, 17, 18 oder 19 zugeordnet werden.  
  
- Ein neuer Offset von 20 oder höher werden alte Offset 9 zugeordnet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
