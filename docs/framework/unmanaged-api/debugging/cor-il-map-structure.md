---
title: COR_IL_MAP-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_IL_MAP
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_IL_MAP
helpviewer_keywords: COR_IL_MAP structure [.NET Framework debugging]
ms.assetid: 534ebc17-963d-4b26-8375-8cd940281db3
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ffcd4dc32f2f509dd9421b2c24781fb2819418b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
|`oldOffset`|Die alte Microsoft intermediate Language (MSIL)-offset relativ zum Anfang der Funktion.|  
|`newOffset`|Der neue MSIL-Offset relativ zum Anfang der Funktion.|  
|`fAccurate`|`true`Wenn die Zuordnung als genau bekannt ist; andernfalls `false`.|  
  
## <a name="remarks"></a>Hinweise  
 Das Format der Zuordnung lautet wie folgt: der Debugger wird vorausgesetzt, dass `oldOffset` bezieht sich auf einen MSIL-Offset innerhalb der ursprünglichen, unveränderten MSIL-Code. Die `newOffset` Parameter verweist auf den entsprechenden MSIL-Offset innerhalb der neuen, instrumentierten Code.  
  
 Für die schrittweise Ausführung, um ordnungsgemäß zu arbeiten, sollten die folgenden Anforderungen erfüllt sein:  
  
-   Die Zuordnung sollte in aufsteigender Reihenfolge sortiert werden.  
  
-   Instrumentierter MSIL-Code sollten nicht neu angeordnet werden.  
  
-   Ursprüngliche MSIL-Code sollten nicht entfernt werden.  
  
-   Die Zuordnung sollte Einträge zum Zuordnen der Sequenzpunkte aus der Programmdatenbankdatei (PDB) enthalten.  
  
 Die Zuordnung ist nicht fehlenden Einträge interpolieren. Das folgende Beispiel zeigt eine Karte und die Ergebnisse an.  
  
 Ordnen Sie:  
  
-   0 Alter Offset, 0 neuer offset  
  
-   5 Alter Offset, 10 neue offset  
  
-   9 Alter Offset, 20 neuer offset  
  
 Ergebnisse:  
  
-   Ein Alter Offset von 0, 1, 2, 3 oder 4 wird ein neuer Offset von 0 zugeordnet werden.  
  
-   Ein Alter Offset von 5, 6, 7 oder 8 wird dem neuen Offset 10 zugeordnet werden.  
  
-   Ein Alter Offset von 9 oder höher werden neue Offset 20 zugeordnet werden.  
  
-   Ein neuer Offset von 0, 1, 2, 3, 4, 5, 6, 7, 8 oder 9 wird dem alten Offset 0 zugeordnet werden.  
  
-   Ein neuer Offset von 10, 11, 12, 13, 14, 15, 16, 17, 18 oder 19 wird dem alten Offset 5 zugeordnet werden.  
  
-   Ein neuer Offset von 20 oder höher wird dem alten Offset 9 zugeordnet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
