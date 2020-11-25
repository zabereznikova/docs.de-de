---
title: COR_PRF_CODEGEN_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_CODEGEN_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODEGEN_FLAGS
helpviewer_keywords:
- COR_PRF_CODEGEN_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 3e184022-0247-4824-a23d-6b29593d8d01
topic_type:
- apiref
ms.openlocfilehash: 3252e3b33da743c0e146e25f798c0e669aeb74ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718604"
---
# <a name="cor_prf_codegen_flags-enumeration"></a>COR_PRF_CODEGEN_FLAGS-Enumeration

Definiert die Codegenerierungs-Flags, die mit der [icorprofilerfunctioncontrol:: setcodegenflags](icorprofilerfunctioncontrol-setcodegenflags-method.md) -Methode festgelegt werden können.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|Keine Funktionen werden in den Text dieser Funktion eingebettet. Die Funktion selbst kann jedoch in ihre Aufrufer eingebunden werden.|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|Alle Optimierungen werden für den Text dieser Funktion deaktiviert. Die Funktion selbst kann jedoch weiterhin in ihren Aufrufern eingebunden werden.|  
  
## <a name="remarks"></a>Hinweise  

 Die- `COR_PRF_CODEGEN_FLAGS` Enumeration wird von der [icorprofilerfunctioncontrol:: setcodegenflags](icorprofilerfunctioncontrol-setcodegenflags-method.md) -Methode verwendet, um dem Profiler zu ermöglichen, die Codegenerierung für die JIT-neu kompilierte Funktion zu steuern.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Profilerstellungsenumerationen](profiling-enumerations.md)
