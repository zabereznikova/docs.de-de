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
ms.openlocfilehash: f4f73b99b4cb48690a2a8611dbf5a5420adab5d4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794356"
---
# <a name="icordebugilframe2remapfunction-method"></a>ICorDebugILFrame2::RemapFunction-Methode
Ordnet eine bearbeitete Funktion neu zu, indem der neue MSIL-Offset (Microsoft Intermediate Language) angegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `newILOffset`  
 in Der neue MSIL-Offset des Stapel Rahmens, bei dem der Anweisungs Zeiger platziert werden soll. Dieser Wert muss ein Sequenz Punkt sein.  
  
 Es liegt in der Verantwortung des Aufrufers, die Gültigkeit dieses Werts sicherzustellen. Beispielsweise ist der MSIL-Offset nicht gültig, wenn er sich außerhalb der Grenzen der Funktion befindet.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Funktion eines Frames bearbeitet wurde, kann der Debugger die `RemapFunction`-Methode zum austauschen in der aktuellen Version der Funktion des Frames abrufen, sodass Sie ausgeführt werden kann. Die Codeausführung beginnt am angegebenen MSIL-Offset.  
  
> [!NOTE]
> Wenn Sie `RemapFunction`aufrufen, wie z. b. [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md), werden alle Debugschnittstellen, die mit dem Erstellen einer Stapel Überwachung für den Thread verknüpft sind, sofort ungültig. Zu diesen Schnittstellen gehören [ICorDebugChain](icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame und ICorDebugNativeFrame.  
  
 Die `RemapFunction`-Methode kann nur im Kontext des aktuellen Frames aufgerufen werden, und zwar nur in einem der folgenden Fälle:  
  
- Nach dem Empfang eines [ICorDebugManagedCallback2:: FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md) -Rückrufs, der noch nicht fortgesetzt wurde.  
  
- Während die Codeausführung aufgrund eines [ICorDebugManagedCallback:: EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md) -Ereignisses für diesen Frame beendet wurde.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
