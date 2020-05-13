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
ms.openlocfilehash: fcf725ea98fa4351e72cf592f92968ee2233ecb0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213581"
---
# <a name="icordebugprocess4-interface"></a>ICorDebugProcess4-Schnittstelle

Bietet Unterstützung für die Out-of-Process-Ausführungs Steuerung.

## <a name="methods"></a>Methoden

| Methode                                                                 | Beschreibung                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) | Benachrichtigt die ICorDebug-Pipeline, dass der Out-of-Process-Debugger die Ausführung des Debuggens fortsetzt. |

## <a name="remarks"></a>Hinweise

Diese Schnittstelle befindet sich innerhalb der Laufzeit und wird nicht über Header oder Bibliotheksdateien verfügbar gemacht. Dabei handelt es sich jedoch um eine COM-Schnittstelle, die von `IUnknown` mit der GUID abgeleitet ist `E930C679-78AF-4953-8AB7-B0AABF0F9F80` , die über die üblichen com-Mechanismen abgerufen werden kann.

## <a name="requirements"></a>Requirements (Anforderungen)

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** Gar

**Bibliothek:** Gar

**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
