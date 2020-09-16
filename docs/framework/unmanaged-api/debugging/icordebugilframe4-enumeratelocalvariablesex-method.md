---
title: ICorDebugILFrame4::EnumerateLocalVariablesEx-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.EnumerateLocalVariablesEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6f60aae6-70ec-4c4c-963a-138df98c4668
topic_type:
- apiref
ms.openlocfilehash: 3149318a1dc20c96bccc9b81347192bfa2e4bfdf
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554826"
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a>ICorDebugILFrame4::EnumerateLocalVariablesEx-Methode
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Ruft einen Enumerator für die lokale Variable im Rahmen ab, und schließt optional Variablen ein, die in der Profiler-ReJIT-Instrumentation hinzugefügt wurden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `flags`  
 in Ein [ilcodekind](ilcodekind-enumeration.md) -Enumerationsmember, der angibt, ob in der Profiler-ReJIT-Instrumentation hinzugefügte Variablen in den Frame eingeschlossen werden.  
  
 `ppValueEnum`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugValueEnum-Objekts, bei dem es sich um den Enumerator für die lokalen Variablen in diesem Frame handelt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ähnelt der [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md) -Methode, außer dass Sie optional auf Variablen zugreift, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden. Das Festlegen `flags` von auf `ILCODE_ORIGINAL_IL` entspricht dem Aufrufen von [ICorDebugILFrame:: EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md). Die Einstellung von `flags` auf `ILCODE_REJIT_IL` ermöglicht dem Debugger Zugriff auf die lokalen Variablen, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden. Ist die Intermediate Language (IL) nicht instrumentiert, ist die Enumeration leer und die Methode gibt `S_OK` zurück.  
  
 Der Enumerator schließt möglicherweise nicht alle lokalen Variablen in die ausgeführte Methode ein, da einige von ihnen möglicherweise nicht aktiv sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugILFrame4-Schnittstelle](icordebugilframe4-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [ReJIT: Anleitung](/archive/blogs/davbr/rejit-a-how-to-guide)
