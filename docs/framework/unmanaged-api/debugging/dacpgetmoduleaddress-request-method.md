---
title: DacpGetModuleAddress::Request-Methode
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress::Request Method
helpviewer.keywords:
- DacpGetModuleAddress::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 1755526636bed6d78663112e4c2ad5ab7c3f731c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860837"
---
# <a name="dacpgetmoduleaddressrequest-method"></a>DacpGetModuleAddress::Request-Methode

Führt eine Anforderung aus, um die-Struktur aus der angegebenen Laufzeitstruktur aufzufüllen.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a>Parameter

`pDataModule`\
in Ein Zeiger auf das Seed Data-Modul.

## <a name="remarks"></a>Hinweise

Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht. Um es zu verwenden, ist die einfachste Möglichkeit, die Implementierung zu imitieren:

- Gibt den Wert zurück, der durch `Request` Aufrufen der- `IXCLRDataModule*` Methode für den-Parameter mit den folgenden Parametern abgerufen wurde:`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`

## <a name="requirements"></a>Anforderungen

**Plattformen:** Siehe [System Anforderungen](../../get-started/system-requirements.md)\
**Header:** Gar
**Bibliothek:** Gar
**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Weitere Informationen:

- [Debuggen](index.md)
- [Dacpgetmoduleaddress-Struktur](dacpgetmoduleaddress-structure.md)
