---
title: ICorDebugFunction-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction
helpviewer_keywords:
- ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae65c59efe1d925b5e058e8664d1e093fdfec875
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917206"
---
# <a name="icordebugfunction-interface"></a>ICorDebugFunction-Schnittstelle

Stellt eine verwaltete Funktion oder Methode dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateBreakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|Erstellt am Anfang dieser Funktion einen Haltepunkt.|  
|[GetClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|Ruft ein ICorDebugClass-Objekt ab, das die Klasse darstellt, deren Member diese Funktion ist.|  
|[GetCurrentVersionNumber-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|Ruft die Versionsnummer der aktuellen Bearbeitung ab, die an dieser Funktion vorgenommen wurde.|  
|[GetILCode-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|Ruft den MSIL-Code (Microsoft Intermediate Language) für diese Funktion ab.|  
|[GetLocalVarSigToken-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|Ruft das Metadatentoken für die Signatur der lokalen Variablen der Funktion ab, `ICorDebugFunction` die durch diese Instanz dargestellt wird.|  
|[GetModule-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|Ruft das Modul ab, in dem diese Funktion definiert ist.|  
|[GetNativeCode-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|Ruft den nativen Code für diese Funktion ab.|  
|[GetToken-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|Ruft das Metadatentoken für diese Funktion ab.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugFunction` -Schnittstelle stellt keine Funktion mit generischen Typparametern dar. Beispielsweise würde eine `ICorDebugFunction` Instanz, jedoch `Func<T>` nicht `Func<string>`, darstellen. Ruft [ICorDebugILFrame2:: enumeratetypeer Parameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) auf, um die generischen Typparameter abzurufen.  
  
 Die Beziehung zwischen dem Metadatentoken `mdMethodDef`einer Methode, und dem `ICorDebugFunction` -Objekt einer Methode hängt davon ab, ob "Bearbeiten und Fortfahren" für die Funktion zulässig ist:  
  
- Wenn für die Funktion "Bearbeiten und Fortfahren" nicht zulässig ist, besteht eine 1:1-Beziehung `ICorDebugFunction` zwischen dem Objekt `mdMethodDef` und dem Token. Das heißt, die Funktion verfügt über `ICorDebugFunction` ein Objekt und `mdMethodDef` ein Token.  
  
- Wenn für die Funktion "Bearbeiten und Fortfahren" zulässig ist, besteht eine n:1-Beziehung zwischen `ICorDebugFunction` dem Objekt und `mdMethodDef` dem Token. Das heißt, die Funktion verfügt möglicherweise über viele `ICorDebugFunction`Instanzen von, eine für jede Version der Funktion, aber nur `mdMethodDef` ein Token.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern**  CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
