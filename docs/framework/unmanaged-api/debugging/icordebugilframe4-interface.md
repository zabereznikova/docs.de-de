---
title: ICorDebugILFrame4-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame4
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1e739183-3e05-49e5-846f-4075256e41de
topic_type:
- apiref
ms.openlocfilehash: 7d0f3661c7941c5f2f85fa5b0b67af213de75f05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724948"
---
# <a name="icordebugilframe4-interface"></a>ICorDebugILFrame4-Schnittstelle

[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Bietet Methoden, mit denen Sie auf lokale Variablen und Code in einem Stapelrahmen aus Intermediate Language (IL)-Code zugreifen können. Ein Parameter legt fest, ob der Debugger Zugang zu Variablen und Code erhält, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[EnumerateLocalVariablesEx-Methode](icordebugilframe4-enumeratelocalvariablesex-method.md)|Gibt eine Liste der lokalen Variablen zurück, die im aktuellen Rahmen verfügbar sind.|  
|[GetCodeEx-Methode](icordebugilframe4-getcodeex-method.md)|Gibt den Code zurück, den dieser Stapelrahmen ausführt.|  
|[GetLocalVariableEx-Methode](icordebugilframe4-getlocalvariableex-method.md)|Gibt den Wert einer lokalen Variable im IL-Stapelrahmen zurück.|  
  
## <a name="remarks"></a>Hinweise  

 Diese Methoden bieten zusätzlich zu den Funktionen, die von den Methoden [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md), [GetCode](icordebugframe-getcode-method.md)und [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) bereitgestellt werden. Jede Methode enthält einen `flags`-Parameter, der angibt, ob zusätzliche, durch eine ReJIT-Anfrage eines Profilers definierte, lokale Variablen oder Code sichtbar sind.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
