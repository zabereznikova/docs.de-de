---
title: ICorDebugILFrame2::RemapFunction-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a9fed4759576d1b6d2fec1a5e9c1e36019e5944c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe2remapfunction-method"></a>ICorDebugILFrame2::RemapFunction-Methode
Ordnet eine bearbeitete Funktion durch Angabe des neuen Microsoft intermediate Language (MSIL)-Offsets  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `newILOffset`  
 [in] Der Stapelrahmen neue MSIL-Offset an dem der Anweisungszeiger platziert werden soll. Dieser Wert muss ein Sequenzpunkt sein.  
  
 Es ist die Verantwortung des Aufrufers, um die Gültigkeit dieses Werts sicherzustellen. Der MSIL-Offset ist beispielsweise ungültig, wenn es außerhalb des gültigen Bereichs der Funktion ist.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Funktion eines Frames bearbeitet wurde, kann der Debugger Aufrufen der `RemapFunction` Methode, um in der neuesten Version der Funktion des Frames austauschen, damit sie ausgeführt werden kann. Die Ausführung des Codes beginnt an der angegebenen MSIL-Offset.  
  
> [!NOTE]
>  Aufrufen von `RemapFunction`, z. B. Aufrufen [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), werden sofort alle debugging-Schnittstellen, die im Zusammenhang mit der eine stapelüberwachung für den Thread generiert ungültig. Zu diesen Schnittstellen gehören [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame ICorDebugInternalFrame und ICorDebugNativeFrame.  
  
 Die `RemapFunction` Methode kann aufgerufen werden, nur im Kontext des aktuellen Frames und nur in einem der folgenden Fälle:  
  
-   Nach dem Empfang einer [ICorDebugManagedCallback2:: FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) Rückruf, der noch nicht fortgesetzt wurde.  
  
-   Während der Ausführung von Code aufgrund des beendet wird ein [ICorDebugManagedCallback:: EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) -Ereignis für dieses Rahmens.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
