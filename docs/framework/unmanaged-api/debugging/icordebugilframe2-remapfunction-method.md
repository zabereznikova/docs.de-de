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
ms.openlocfilehash: 75004f646c01897ef3e3016b073220ad33a0d925
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967580"
---
# <a name="icordebugilframe2remapfunction-method"></a>ICorDebugILFrame2::RemapFunction-Methode
Ordnet eine bearbeitete Funktion neu zu, indem der neue MSIL-Offset (Microsoft Intermediate Language) angegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `newILOffset`  
 in Der neue MSIL-Offset des Stapel Rahmens, bei dem der Anweisungs Zeiger platziert werden soll. Dieser Wert muss ein Sequenz Punkt sein.  
  
 Es liegt in der Verantwortung des Aufrufers, die Gültigkeit dieses Werts sicherzustellen. Beispielsweise ist der MSIL-Offset nicht gültig, wenn er sich außerhalb der Grenzen der Funktion befindet.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Funktion eines Frames bearbeitet wurde, kann der Debugger die `RemapFunction` Methode zum austauschen in der aktuellen Version der Funktion des Frames aufzurufen, sodass Sie ausgeführt werden kann. Die Codeausführung beginnt am angegebenen MSIL-Offset.  
  
> [!NOTE]
> Durch `RemapFunction`den Aufruf von [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)werden alle Debugschnittstellen, die mit dem Erstellen einer Stapel Überwachung für den Thread verknüpft sind, sofort ungültig. Zu diesen Schnittstellen gehören [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame und ICorDebugNativeFrame.  
  
 Die `RemapFunction` -Methode kann nur im Kontext des aktuellen Frames aufgerufen werden, und zwar nur in einem der folgenden Fälle:  
  
- Nach dem Empfang eines [ICorDebugManagedCallback2:: FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) -Rückrufs, der noch nicht fortgesetzt wurde.  
  
- Während die Codeausführung aufgrund eines [ICorDebugManagedCallback:: EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) -Ereignisses für diesen Frame beendet wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
