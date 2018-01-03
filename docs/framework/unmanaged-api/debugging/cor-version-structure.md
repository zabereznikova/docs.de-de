---
title: COR_VERSION-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_VERSION
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_VERSION
helpviewer_keywords: COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b527cb9175315af98a9ad4e9be06d459ad6e188e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corversion-structure"></a>COR_VERSION-Struktur
Speichert die standardmäßige vierstellige Versionsnummer der Common Language Runtime.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`dwMajor`|Die Hauptversionsnummer.|  
|`dwMinor`|Die Nebenversionsnummer.|  
|`dwBuild`|Die Buildnummer.|  
|`dwSubBuild`|Sub-Buildnummer.|  
  
## <a name="remarks"></a>Hinweise  
 Ist die Versionsnummer 1.0.3705.288, 1 ist die Hauptversionsnummer, 0 ist die Nummer der Nebenversion 3705 wird die Buildnummer und 288 ist das Sub-Buildnummer.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
