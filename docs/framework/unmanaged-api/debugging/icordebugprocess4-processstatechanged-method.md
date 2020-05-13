---
title: ICorDebugProcess4::P rocess StateChanged-Methode
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4::ProcessStateChanged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4::ProcessStateChanged
helpviewer_keywords:
- ICorDebugProcess4::ProcessStateChanged method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 910c411d2c63ce2c6cf262e28e08546657dc2a4c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213568"
---
# <a name="icordebugprocess4processstatechanged-method"></a>ICorDebugProcess4::P rocess StateChanged-Methode

Benachrichtigt die ICorDebug-Pipeline, dass der Out-of-Process-Debugger die Ausführung des Debuggens fortsetzt.

## <a name="syntax"></a>Syntax

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a>Parameter

 `eChange`\
in Ein Member der [cordebugstatechange-Enumeration](cordebugstatechange-enumeration.md) , die eine Änderung des Ausführungs Status des Prozesses beschreibt.

## <a name="remarks"></a>Hinweise

Die bereitgestellte Methode ist Teil der `ICorDebugProcess4` -Schnittstelle und entspricht dem vierten Slot der Tabelle der virtuellen Methode.

## <a name="requirements"></a>Requirements (Anforderungen)

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

 **Header:** Gar

 **Bibliothek:** Gar

 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess4-Schnittstelle](icordebugprocess4-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
