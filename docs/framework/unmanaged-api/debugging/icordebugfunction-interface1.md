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
ms.openlocfilehash: ba0e0b1b2bac785e28f41e09dda74841121a748d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794506"
---
# <a name="icordebugfunction-interface"></a>ICorDebugFunction-Schnittstelle

Stellt eine verwaltete Funktion oder Methode dar.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[CreateBreakpoint-Methode](icordebugfunction-createbreakpoint-method.md)|Erstellt am Anfang dieser Funktion einen Haltepunkt.|  
|[GetClass-Methode](icordebugfunction-getclass-method.md)|Ruft ein ICorDebugClass-Objekt ab, das die Klasse darstellt, deren Member diese Funktion ist.|  
|[GetCurrentVersionNumber-Methode](icordebugfunction-getcurrentversionnumber-method.md)|Ruft die Versionsnummer der aktuellen Bearbeitung ab, die an dieser Funktion vorgenommen wurde.|  
|[GetILCode-Methode](icordebugfunction-getilcode-method.md)|Ruft den MSIL-Code (Microsoft Intermediate Language) für diese Funktion ab.|  
|[GetLocalVarSigToken-Methode](icordebugfunction-getlocalvarsigtoken-method.md)|Ruft das Metadatentoken für die Signatur der lokalen Variablen der Funktion ab, die von dieser `ICorDebugFunction` Instanz dargestellt wird.|  
|[GetModule-Methode](icordebugfunction-getmodule-method.md)|Ruft das Modul ab, in dem diese Funktion definiert ist.|  
|[GetNativeCode-Methode](icordebugfunction-getnativecode-method.md)|Ruft den nativen Code für diese Funktion ab.|  
|[GetToken-Methode](icordebugfunction-gettoken-method.md)|Ruft das Metadatentoken für diese Funktion ab.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugFunction`-Schnittstelle stellt keine Funktion mit generischen Typparametern dar. Beispielsweise würde eine `ICorDebugFunction` Instanz `Func<T>`, aber nicht `Func<string>`darstellen. Ruft [ICorDebugILFrame2:: enumeratetypeer Parameters](icordebugilframe2-enumeratetypeparameters-method.md) auf, um die generischen Typparameter abzurufen.  
  
 Die Beziehung zwischen dem Metadatentoken einer Methode, `mdMethodDef`und dem `ICorDebugFunction` Objekt einer Methode hängt davon ab, ob "Bearbeiten und Fortfahren" für die Funktion zulässig ist:  
  
- Wenn für die Funktion "Bearbeiten und Fortfahren" nicht zulässig ist, besteht eine 1:1-Beziehung zwischen dem `ICorDebugFunction` Objekt und dem `mdMethodDef` Token. Das heißt, die Funktion verfügt über ein `ICorDebugFunction` Objekt und ein `mdMethodDef` Token.  
  
- Wenn für die Funktion "Bearbeiten und Fortfahren" zulässig ist, besteht eine n:1-Beziehung zwischen dem `ICorDebugFunction` Objekt und dem `mdMethodDef` Token. Das heißt, die Funktion kann über viele Instanzen von `ICorDebugFunction`verfügen, eine für jede Version der Funktion, aber nur ein `mdMethodDef` Token.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:**  Corguids. lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
