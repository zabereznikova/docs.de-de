---
title: ICorDebugProcess4-Schnittstelle
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4
helpviewer_keywords:
- ICorDebugProcess4 interface [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 1bdc958f2516bcd7c2eb74312fbf478e6d49535a
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221425"
---
# <a name="icordebugprocess4-interface"></a>ICorDebugProcess4-Schnittstelle

Bietet Unterstützung für die Out-of ausführungssteuerung Prozess.

## <a name="methods"></a>Methoden

| Methode                                                                 | Beschreibung                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) | Benachrichtigt, dass die Out-of Prozess-Debugger, die zu debuggende Komponente Ausführung fortgesetzt wird der ICorDebug-Pipeline. |

## <a name="remarks"></a>Hinweise

Diese Schnittstelle befindet sich in der Common Language Runtime und wird nicht über alle Header oder Bibliotheksdateien verfügbar gemacht werden. Es ist jedoch eine COM-Schnittstelle, die von abgeleitet `IUnknown` mit GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` , die über die üblichen Mechanismen der COM-abgerufen werden kann.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** Keine

**Bibliothek:** Keine

**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
