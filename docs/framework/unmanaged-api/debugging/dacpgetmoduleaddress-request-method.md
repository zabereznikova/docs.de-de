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
ms.openlocfilehash: 6850dc256a70e0c0343104b3904e9eda62d11e7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179199"
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

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Kopfzeile:** Keine **Bibliothek:** Keine  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Weitere Informationen

- [Debuggen](index.md)
- [DacpGetModuleAddress-Schnittstelle](dacpgetmoduleaddress-structure.md)
