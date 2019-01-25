---
title: CorDebugJITCompilerFlagsDeprecated-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlagsDeprecated
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlagsDeprecated
helpviewer_keywords:
- CorDebugJITCompilerFlagsDeprecated enumeration [.NET Framework debugging]
ms.assetid: af15e2ca-6be1-472b-bd36-03644a1e3ddd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ef262fcae117b27f06d4dba3b2087028b5cfa65
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743256"
---
# <a name="cordebugjitcompilerflagsdeprecated-enumeration"></a>CorDebugJITCompilerFlagsDeprecated-Enumeration
Diese Enumeration ist veraltet. Verwenden der `CORDEBUG_JIT_DEFAULT` Mitglied der [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) Enumeration stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum CorDebugJITCompilerFlagsDeprecated {  
    CORDEBUG_JIT_TRACK_DEBUG_INFO  = 0x1  
} CorDebugJITCompilerFlagsDeprecated;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`CORDEBUG_JIT_TRACK_DEBUG_INFO`|Verwenden Sie stattdessen `CORDEBUG_JIT_DEFAULT`.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** 1.0, 1.1  
  
## <a name="see-also"></a>Siehe auch
- [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
