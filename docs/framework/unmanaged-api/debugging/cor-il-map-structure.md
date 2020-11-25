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
ms.openlocfilehash: fb6b5d43e60b52c867535c42d59a098ef3c959bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726382"
---
# <a name="cor_il_map-structure"></a>COR_IL_MAP-Struktur

Gibt Änderungen im relativen Offset einer Funktion an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;
    ULONG32 newOffset;
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`oldOffset`|Der alte MSIL-Offset (Microsoft Intermediate Language) relativ zum Anfang der Funktion.|  
|`newOffset`|Der neue MSIL-Offset relativ zum Anfang der Funktion.|  
|`fAccurate`|`true` , wenn die Zuordnung bekanntermaßen korrekt ist. andernfalls `false` .|  
  
## <a name="remarks"></a>Hinweise  

 Das Format der Zuordnung lautet wie folgt: der Debugger geht davon aus, dass `oldOffset` auf einen MSIL-Offset im ursprünglichen, nicht geänderten MSIL-Code verweist. Der- `newOffset` Parameter verweist auf den entsprechenden MSIL-Offset innerhalb des neuen, instrumentierten Codes.  
  
 Die folgenden Anforderungen müssen erfüllt sein, damit die Schritt Ausführung ordnungsgemäß funktioniert:  
  
- Die Zuordnung sollte in aufsteigender Reihenfolge sortiert werden.  
  
- Instrumentierter MSIL-Code sollte nicht neu angeordnet werden.  
  
- Der ursprüngliche MSIL-Code sollte nicht entfernt werden.  
  
- Die Zuordnung sollte Einträge enthalten, mit denen alle Sequenz Punkte aus der Programm Datenbankdatei (PDB) zugeordnet werden können.  
  
 Fehlende Einträge werden von der Zuordnung nicht interpolieren. Das folgende Beispiel zeigt eine Karte und ihre Ergebnisse.  
  
 Bilden  
  
- 0 Alter Offset, 0 neuer Offset  
  
- 5-jähriger Offset, 10 neuer Offset  
  
- 9 Alter Offset, 20 neue Offset  
  
 Ergebnisse:  
  
- Der alte Offset 0, 1, 2, 3 oder 4 wird einem neuen Offset von 0 zugeordnet.  
  
- Der alte Offset 5, 6, 7 oder 8 wird dem neuen Offset 10 zugeordnet.  
  
- Ein Alter Offset von 9 oder höher wird dem neuen Offset 20 zugeordnet.  
  
- Der neue Offset 0, 1, 2, 3, 4, 5, 6, 7, 8 oder 9 wird dem alten Offset 0 zugeordnet.  
  
- Ein neuer Offset von 10, 11, 12, 13, 14, 15, 16, 17, 18 oder 19 wird dem alten Offset 5 zugeordnet.  
  
- Ein neuer Offset von 20 oder höher wird dem alten Offset 9 zugeordnet.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Corprof. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
