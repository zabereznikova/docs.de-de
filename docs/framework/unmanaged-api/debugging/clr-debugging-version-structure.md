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
ms.openlocfilehash: 8a2abe847728a2bb1f1345ef73e55b58e4704001
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729810"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`wStructVersion`|Die Versionsnummer der-Struktur.|  
|`wMajor`|Die Hauptversionsnummer.|  
|`wMinor`|Die Nebenversionsnummer.|  
|`wBuild`|Die Buildnummer.|  
|`wRevision`|Die Revisionsnummer.|  
  
## <a name="remarks"></a>Hinweise  

 Die- `CLR_DEBUGGING_VERSION` Struktur ist identisch mit der COR_VERSION-Struktur, aber die- `CLR_DEBUGGING_VERSION` Struktur stellt ein zusätzliches Struktur Versions Feld ( `wStructVersion` ) bereit. Dieses Feld muss derzeit auf 0 (null) festgelegt werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
