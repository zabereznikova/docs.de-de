---
title: DacpGetModuleAddress::Anforderungsmethode
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
ms.openlocfilehash: 4dbe6a2c295e5afae1b6761f0c7b695fdb906428
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102906"
---
# <a name="dacpgetmoduleaddressrequest-method"></a>DacpGetModuleAddress::Anforderungsmethode

Führt eine Anforderung aus, um die Struktur aus der angegebenen Laufzeitstruktur aufzufüllen.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a>Parameter

`pDataModule`\
[in] Ein Zeiger auf das Seed-Datenmodul.

## <a name="remarks"></a>Bemerkungen

Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht. Um es zu verwenden, ist der einfachste Weg, die Implementierung nachzuahmen:

- Geben Sie den Wert `Request` zurück, `IXCLRDataModule*` der durch Aufrufen der Methode für den Parameter mit den folgenden Parametern erhalten wurde:`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`

## <a name="requirements"></a>Requirements (Anforderungen)

**Plattformen:** Siehe [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md)\
**Kopfzeile:** Keine
**Bibliothek:** Keine
**.NET Framework-Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Weitere Informationen

- [Debuggen](index.md)
- [DacpGetModuleAddress-Struktur](dacpgetmoduleaddress-structure.md)
