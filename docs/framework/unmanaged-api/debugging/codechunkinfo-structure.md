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
ms.openlocfilehash: d33c8b31473e389e07fb24076dc32272e9dde387
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132397"
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
  
|Member|Beschreibung|  
|------------|-----------------|  
|`startAddr`|Ein `CORDB_ADDRESS`-Wert, der die Anfangsadresse des Blocks angibt.|  
|`length`|Die Größe des Blocks in Bytes.|  
  
## <a name="remarks"></a>Hinweise  
 Der einzelne Codeblock ist ein Bereich von System eigenem Code, der Teil eines Code Objekts ist, z. b. einer Funktion.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetCodeChunks-Methode](icordebugcode2-getcodechunks-method.md)
- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
