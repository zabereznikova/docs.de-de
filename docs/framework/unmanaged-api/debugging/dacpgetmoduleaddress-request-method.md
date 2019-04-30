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
ms.openlocfilehash: 298620092c37b2c02332e9135f73584272e326bd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965899"
---
# <a name="dacpgetmoduleaddressrequest-method"></a>DacpGetModuleAddress::Request-Methode

Führt eine Anforderung zum Auffüllen der Struktur aus der angegebenen Runtime-Struktur.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a>Parameter

`pDataModule`\
[in] Ein Zeiger auf die Seed-Data-Modul.

## <a name="remarks"></a>Hinweise

Diese Struktur befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht. Um es zu verwenden, ist die einfachste Möglichkeit, um die Implementierung zu imitieren:

- Rückgabewert von Aufrufen der `Request` Methode für die `IXCLRDataModule*` Parameter mit den folgenden Parametern: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Keiner     
**Bibliothek:** Keiner  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [DacpGetModuleAddress-Schnittstelle](dacpgetmoduleaddress-structure.md)