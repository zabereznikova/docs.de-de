---
title: CodeChunkInfo-Struktur
ms.date: 03/30/2017
api_name:
- CodeChunkInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CodeChunkInfo
helpviewer_keywords:
- CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type:
- apiref
ms.openlocfilehash: 11197246662a93f6a8b57c6e61e49505a9999d00
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727431"
---
# <a name="codechunkinfo-structure"></a>CodeChunkInfo-Struktur

Stellt einen einzelnen Codeabschnitt im Speicher dar.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`startAddr`|Ein- `CORDB_ADDRESS` Wert, der die Anfangsadresse des Segments angibt.|  
|`length`|Die Größe des Blocks in Bytes.|  
  
## <a name="remarks"></a>Hinweise  

 Der einzelne Codeblock ist ein Bereich von System eigenem Code, der Teil eines Code Objekts ist, z. b. einer Funktion.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [GetCodeChunks-Methode](icordebugcode2-getcodechunks-method.md)
- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
