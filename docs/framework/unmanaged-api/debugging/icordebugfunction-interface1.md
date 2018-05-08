---
title: ICorDebugFunction Schnittstelle1
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
ms.openlocfilehash: 344acf109d58d0ed2fbc8a91da0761b4dd148a27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugfunction-interface1"></a>ICorDebugFunction Schnittstelle1
Stellt eine verwaltete Funktion oder Methode dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateBreakpoint-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|Erstellt einen Haltepunkt am Anfang dieser Funktion.|  
|[GetClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|Ruft ein ICorDebugClass-Objekt, das die Klasse darstellt, der diese Funktion ein Mitglied ist.|  
|[GetCurrentVersionNumber-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|Ruft die Versionsnummer der letzten Änderung dieser Funktion ab.|  
|[GetILCode-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|Ruft die Microsoft intermediate Language (MSIL)-Code für diese Funktion.|  
|[GetLocalVarSigToken-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|Ruft das Metadatentoken für die Signatur der lokalen Variablen der Funktion, die von diesem dargestellt wird `ICorDebugFunction` Instanz.|  
|[GetModule-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|Ruft das Modul, in dem diese Funktion definiert ist.|  
|[GetNativeCode-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|Ruft den systemeigenen Code für diese Funktion.|  
|[GetToken-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|Ruft die Metadaten für diese Funktion ab.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugFunction` Schnittstelle stellt eine Funktion mit generischen Typparametern keine dar. Angenommen, ein `ICorDebugFunction` Instanz darstellen würde `Func<T>` , aber nicht `Func<string>`. Rufen Sie [ICorDebugILFrame2:: EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) zum Abrufen der generischen Typparameter.  
  
 Die Beziehung zwischen einer Methode Metadatentoken `mdMethodDef`, und eine Methode `ICorDebugFunction` Objekt ist abhängig von bearbeiten und Fortfahren ist, ob für die Funktion zulässig:  
  
-   Wenn Bearbeiten und Fortfahren wird für die Funktion nicht zulässig, besteht eine 1: 1-Beziehung zwischen der `ICorDebugFunction` Objekt und die `mdMethodDef` token. D. h. die Funktion verfügt über einen `ICorDebugFunction` -Objekt und ein `mdMethodDef` token.  
  
-   Wenn Bearbeiten und Fortfahren für die Funktion zulässig ist, besteht eine viele-zu-eins-Beziehung zwischen der `ICorDebugFunction` Objekt und die `mdMethodDef` token. D. h. möglicherweise die Funktion vielen Instanzen von `ICorDebugFunction`, eine für jede Version der Funktion, aber nur eine `mdMethodDef` token.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
