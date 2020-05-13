---
title: ICorDebugThread4::GetCurrentCustomDebuggerNotification-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetCurrentCustomDebuggerNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetCurrentCustomDebuggerNotification
helpviewer_keywords:
- GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
- ICorDebugThread4::GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
ms.assetid: 57e0f2d2-5f0e-4e2d-99ec-3f26632eb693
topic_type:
- apiref
ms.openlocfilehash: 76ad1c0ac421f05cf30f6d3d1f3e65848796a0c7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378697"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a>ICorDebugThread4::GetCurrentCustomDebuggerNotification-Methode

Ruft das aktuelle [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) -Objekt für den aktuellen Thread ab.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a>Parameter

`ppNotificationObject`\
vorgenommen Ein Zeiger auf das aktuelle- `ICorDebugManagedCallback3::CustomNotification` Objekt im aktuellen Thread.

## <a name="remarks"></a>Hinweise

Der Wert von `ppNotificationObject` ist NULL, wenn die Methode nicht innerhalb eines `ICorDebugManagedCallback3::CustomNotification` Rückrufs aufgerufen wird, oder, wenn kein Aktuelles Benachrichtigungs Objekt vorhanden ist.

## <a name="requirements"></a>Requirements (Anforderungen)

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** CorDebug.idl, CorDebug.h

**Bibliothek:** CorGuids.lib

**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorDebugThread4-Schnittstelle](icordebugthread4-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
