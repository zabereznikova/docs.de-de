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
ms.openlocfilehash: 5e3a6714489e2051a09b5855ab9f911ef2f57450
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632284"
---
# <a name="icordebugprocess4processstatechanged-method"></a>ICorDebugProcess4::ProcessStateChanged-Methode

Benachrichtigt, dass die Out-of Prozess-Debugger, die zu debuggende Komponente Ausführung fortgesetzt wird der ICorDebug-Pipeline.

## <a name="syntax"></a>Syntax

```
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a>Parameter

 `eChange`\
[in] Ein Mitglied der [CorDebugStateChange-Enumeration](cordebugstatechange-enumeration.md) , beschreibt eine Änderung im Ausführungsstatus des Prozesses.

## <a name="remarks"></a>Hinweise

Die angegebene Methode ist Teil der `ICorDebugProcess4` Schnittstelle, und mit dem vierten Steckplatz der virtuellen Methodentabelle entspricht.

## <a name="requirements"></a>Anforderungen

 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

 **Header:** Keiner

 **Bibliothek:** Keiner
 
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess4-Schnittstelle](icordebugprocess4-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
