---
title: CorDebugEHClause-Struktur
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugEHClause
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0e350a1b-6997-46d0-bfc5-962a5011ef43
topic_type:
- apiref
ms.openlocfilehash: 225523280a2e1e0d8f51321e9dd865d901e725ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712702"
---
# <a name="cordebugehclause-structure"></a>CorDebugEHClause-Struktur

[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Stellt eine Ausnahmebehandlung (Exception Handling, EH)-Klausel für einen bestimmten Intermediate Language (IL)-Codeabschnitt dar.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
typedef struct _CorDebugEHClause {  
   ULONG32 Flags;  
   ULONG32 TryOffset;  
   ULONG32 TryLength;  
   ULONG32 HandlerOffset;  
   ULONG32 HandlerLength;  
   ULONG32 ClassToken;  
   ULONG32 FilterOffset;  
} CorDebugEHClause;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`Flags`|Ein Bitfeld, das die Ausnahmeinformationen in der EH-Klausel beschreibt. Weitere Informationen finden Sie im Abschnitt "Hinweise".|  
|`TryOffset`|Der Offset, in Bytes, des `try`-Blocks vom Beginn des Methodentextes.|  
|`TryLength`|Die Länge, in Bytes, des `try`-Blocks.|  
|`HandlerOffset`|Der Speicherort des Handlers für diesen `try`-Block.|  
|`HandlerLength`|Die Größe des Handlercodes in Bytes.|  
|`ClassToken`|Der Metadatentoken für einen typenbasierten Ausnahmehandler.|  
|`FilterOffset`|Der Offset, in Bytes, vom Beginn des Methodentextes für einen filterbasierten Ausnahmehandler.|  
  
## <a name="remarks"></a>Hinweise  

 Ein Array von `CoreDebugEHClause` Werten wird von der [getehklauseln](icordebugilcode-getehclauses-method.md) -Methode zurückgegeben.  
  
 Die Informationen der EH-Klausel werden durch die CLI-Spezifikation definiert. Weitere Informationen finden Sie unter [Standard-ECMA-355: Common Language Infrastructure (CLI), Sechste Edition](https://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
 Das `flags`-Feld kann die folgenden Flags enthalten. Beachten Sie, dass diese nicht in CorDebug.idl oder CorDebug.h definiert sind.  
  
|Flag|Wert|BESCHREIBUNG|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|0x00000000|Eine typisierte Ausnahmeklausel.|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|0x00000001|Ein Ausnahmefilter und eine Handlerklausel.|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|0x00000002|Eine `finally`-Klausel.|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|0x00000004|Eine fault-Klausel (eine `finally`-Klausel, die nur aufgerufen wird, wenn eine Ausnahme ausgelöst wird).|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [GetEHClauses-Methode](icordebugilcode-getehclauses-method.md)
- [Debuggen von Strukturen](debugging-structures.md)
