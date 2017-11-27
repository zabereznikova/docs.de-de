---
title: CLR_DEBUGGING_VERSION-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLR_DEBUGGING_VERSION
api_location: mscordbi.dll
api_type: COM
f1_keywords: CLR_DEBUGGING_VERSION
helpviewer_keywords: CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 98124b7b9efb2c92ebee6b6e99f73edc6cf173a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="clrdebuggingversion-structure"></a>CLR_DEBUGGING_VERSION-Struktur
Definiert die Produktversion der Common Language Runtime (CLR) zu Debugzwecken.  
  
## <a name="syntax"></a>Syntax  
  
```  
Typedef struct _CLR_DEBUGGING_VERSION  
{  
WORD wStructVersion;  
WORD wMajor;   
WORD wMinor;  
WORD wBuild;  
WORD wRevision;  
}  CLR_DEBUGGING_VERSION;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`wStructVersion`|Die Versionsnummer der Struktur|  
|`wMajor`|Die Hauptversionsnummer.|  
|`wMinor`|Die Nebenversionsnummer.|  
|`wBuild`|Die Buildnummer.|  
|`wRevision`|Die Revisionsnummer.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CLR_DEBUGGING_VERSION` Struktur ist identisch mit der COR_VERSION-Struktur, jedoch die `CLR_DEBUGGING_VERSION` Struktur bietet eine zusätzliche Version Strukturfeld (`wStructVersion`). Derzeit muss dieses Feld auf NULL festgelegt werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
