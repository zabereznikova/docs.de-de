---
title: ICorDebugProcess4::ProcessStateChanged-Methode
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
ms.openlocfilehash: a6f36f5b86b4fa58ce2a4ef4aa23d527f797a5a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178627"
---
# <a name="icordebugprocess4processstatechanged-method"></a>ICorDebugProcess4::ProcessStateChanged-Methode

Benachrichtigt die ICorDebug-Pipeline, dass der Fehlerdebugger out of process die Ausführung des Debugees fortsetzt.

## <a name="syntax"></a>Syntax

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a>Parameter

 `eChange`\
[in] Ein Member der [CorDebugStateChange-Enumeration,](cordebugstatechange-enumeration.md) der eine Änderung im Ausführungsstatus des Prozesses beschreibt.

## <a name="remarks"></a>Bemerkungen

Die bereitgestellte Methode `ICorDebugProcess4` ist Teil der Schnittstelle und entspricht dem vierten Steckplatz der virtuellen Methodentabelle.

## <a name="requirements"></a>Requirements (Anforderungen)

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

 **Kopfzeile:** nichts

 **Bibliothek:** nichts

 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Weitere Informationen

- [ICorDebugProcess4-Schnittstelle](icordebugprocess4-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
