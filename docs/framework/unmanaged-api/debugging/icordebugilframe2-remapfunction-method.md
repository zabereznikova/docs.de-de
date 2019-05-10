---
title: ICorDebugILFrame2::RemapFunction-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.RemapFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbec4a4ba05a7e6d50f9740582415219eafb1e57
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64621474"
---
# <a name="icordebugilframe2remapfunction-method"></a>ICorDebugILFrame2::RemapFunction-Methode
Ordnet eine bearbeitete Funktion durch Angabe des neuen Microsoft intermediate Language (MSIL)-Offsets neu  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `newILOffset`  
 [in] Der Stapelrahmen neue MSIL-Offset zu dem der Anweisungszeiger eingefügt werden soll. Dieser Wert muss es sich um ein Sequenzpunkt sein.  
  
 Es ist der Verantwortung des Aufrufers um sicherzustellen, dass die Gültigkeit dieses Werts. Der MSIL-Offset ist z. B. nicht gültig, wenn sie außerhalb der Grenzen der Funktion.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Funktion eines Frames bearbeitet wurde, kann der Debugger Aufrufen der `RemapFunction` Methode in der neuesten Version der Funktion des Frames austauschen, damit sie ausgeführt werden kann. Die Ausführung des Codes beginnt an der angegebenen MSIL-Offset.  
  
> [!NOTE]
>  Aufrufen von `RemapFunction`, z. B. Aufrufen von [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), alle debugging-Schnittstellen, die im Zusammenhang mit der eine stapelüberwachung für den Thread zu generieren, wird sofort ungültig. Diese Schnittstellen umfassen [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame ICorDebugInternalFrame und ICorDebugNativeFrame.  
  
 Die `RemapFunction` Methode kann aufgerufen werden, nur im Kontext des aktuellen Frames und nur in einem der folgenden Fälle:  
  
- Nach dem Empfang einer [ICorDebugManagedCallback2:: FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) Rückruf, der noch nicht fortgesetzt wurde.  
  
- Während der Ausführung von Code beendet wird, da ein [ICorDebugManagedCallback:: EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) Ereignis für diesen Frame.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
