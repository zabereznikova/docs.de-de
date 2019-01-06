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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fecd5af43f4b984a4ab626e9832b3318715c0516
ms.sourcegitcommit: deb9225a55485a5a6e6c7914deb30ccfceb69d3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2019
ms.locfileid: "54058359"
---
# <a name="clrdebuggingversion-structure"></a>CLR_DEBUGGING_VERSION-Struktur
Definiert die Produktversion der Common Language Runtime (CLR) zu Debugzwecken.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|`wStructVersion`|Die Versionsnummer der Struktur|  
|`wMajor`|Die Hauptversionsnummer.|  
|`wMinor`|Die Nebenversionsnummer.|  
|`wBuild`|Die Nummer des Builds.|  
|`wRevision`|Die Revisionsnummer.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CLR_DEBUGGING_VERSION` hat die gleiche Struktur wie COR_VERSION-Struktur, jedoch die `CLR_DEBUGGING_VERSION` Struktur bietet eine zusätzliche Strukturversionsfeld (`wStructVersion`). Derzeit muss dieses Feld auf NULL festgelegt werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
