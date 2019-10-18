---
title: ICorDebugController::Continue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugController.Continue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62e2be44165472e2fbf368f61b865d39a5e9fc28
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395463"
---
# <a name="icordebugcontrollercontinue-method"></a>ICorDebugController::Continue-Methode

Setzt die Ausführung verwalteter Threads nach einem Aufrufvorgang der [Methode "Ende](icordebugcontroller-stop-method.md)" fort.

## <a name="syntax"></a>Syntax

```cpp
HRESULT Continue (
    [in] BOOL fIsOutOfBand
);
```

## <a name="parameters"></a>Parameter

`fIsOutOfBand`  
in Wird auf `true` festgelegt, wenn ein Out-of-Band-Ereignis fortgesetzt wird. andernfalls legen Sie auf `false` fest.

## <a name="remarks"></a>Hinweise

`Continue` setzt den Prozess nach einem aufzurufenden `ICorDebugController::Stop`-Methode fort.

Wenn Sie das Debuggen im gemischten Modus durchführen, sollten Sie `Continue` nicht für den Win32-Ereignis Thread aufzurufen, es sei denn, Sie setzen ein Out-of-Band-Ereignis

Ein *in-Band-Ereignis* ist entweder ein verwaltetes Ereignis oder ein normales nicht verwaltetes Ereignis, in dem der Debugger die Interaktion mit dem verwalteten Status des Prozesses unterstützt. In diesem Fall empfängt der Debugger den [ICorDebugUnmanagedCallback::D ebugevent](icordebugunmanagedcallback-debugevent-method.md) -Rückruf, dessen `fOutOfBand`-Parameter auf `false` festgelegt ist.

Bei einem *out-of-Band-Ereignis* handelt es sich um ein nicht verwaltetes Ereignis, bei dem die Interaktion mit dem verwalteten Zustand des Prozesses unmöglich ist, während der Prozess aufgrund des Ereignisses beendet wird. In diesem Fall empfängt der Debugger den `ICorDebugUnmanagedCallback::DebugEvent`-Rückruf, dessen `fOutOfBand`-Parameter auf `true` festgelegt ist.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** CorDebug.idl, CorDebug.h

**Bibliothek:** CorGuids.lib

**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
