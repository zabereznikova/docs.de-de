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
ms.openlocfilehash: 5eb6299526d69624056961cfb7f0387ff8f873cf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725026"
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
> Durch `RemapFunction` den Aufruf von [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md)werden alle Debugschnittstellen, die mit dem Erstellen einer Stapel Überwachung für den Thread verknüpft sind, sofort ungültig. Zu diesen Schnittstellen gehören [ICorDebugChain](icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame und ICorDebugNativeFrame.  
  
 Die `RemapFunction` -Methode kann nur im Kontext des aktuellen Frames aufgerufen werden, und zwar nur in einem der folgenden Fälle:  
  
- Nach dem Empfang eines [ICorDebugManagedCallback2:: FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md) -Rückrufs, der noch nicht fortgesetzt wurde.  
  
- Während die Codeausführung aufgrund eines [ICorDebugManagedCallback:: EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md) -Ereignisses für diesen Frame beendet wurde.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
