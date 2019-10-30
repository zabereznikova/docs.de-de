---
title: CLR_DEBUGGING_VERSION-Struktur
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_VERSION
helpviewer_keywords:
- CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type:
- apiref
ms.openlocfilehash: 651b916a0e3ca178432094428611f9bcc8f0fd17
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132420"
---
# <a name="clr_debugging_version-structure"></a>CLR_DEBUGGING_VERSION-Struktur
Definiert die Produktversion der Common Language Runtime (CLR) zu Debugzwecken.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`wStructVersion`|Die Versionsnummer der-Struktur.|  
|`wMajor`|Die Hauptversionsnummer.|  
|`wMinor`|Die Nebenversionsnummer.|  
|`wBuild`|Die Buildnummer.|  
|`wRevision`|Die Revisionsnummer.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CLR_DEBUGGING_VERSION`-Struktur ist identisch mit der COR_VERSION-Struktur. die `CLR_DEBUGGING_VERSION` Struktur bietet jedoch ein zusätzliches Struktur Versions Feld (`wStructVersion`). Dieses Feld muss derzeit auf 0 (null) festgelegt werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
