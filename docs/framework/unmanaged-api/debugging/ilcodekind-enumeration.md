---
title: ILCodeKind-Enumeration
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ILCodeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b91765e4-82db-46f9-a6dc-6b80610276af
topic_type:
- apiref
ms.openlocfilehash: b9d27c3e3cd42039aeefcb517ecc81eadeb5c183
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557423"
---
# <a name="ilcodekind-enumeration"></a>ILCodeKind-Enumeration
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Stellt Werte bereit, die angeben, ob der Debugger auf lokale Variablen oder Code, die in der Profiler-ReJIT-Instrumentation hinzugefügt wurden, zugreifen kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a>Member  
  
|Membername|BESCHREIBUNG|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|Der Debugger hat keinen Zugriff auf Informationen aus der ReJIT-Instrumentierung.|  
|`ILCODE_REJIT_IL`|Der Debugger hat Zugriff auf Informationen aus der ReJIT-Instrumentierung.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Member der `ILCodeKind` -Enumeration kann an die Methoden [enumeratelocalvariablesex](icordebugilframe4-enumeratelocalvariablesex-method.md) und [getlocalvariableex](icordebugilframe4-getlocalvariableex-method.md) weitergegeben werden, um zu bestimmen, ob der Debugger auf Variablen zugreifen kann, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden, und auf die [getcodeex](icordebugilframe4-getcodeex-method.md) -Methode, um zu bestimmen, ob der Debugger auf instrumentierte Il  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugenumerationen](debugging-enumerations.md)
- [ICorDebugILFrame4-Schnittstelle](icordebugilframe4-interface.md)
- [ReJIT: Anleitung](/archive/blogs/davbr/rejit-a-how-to-guide)
