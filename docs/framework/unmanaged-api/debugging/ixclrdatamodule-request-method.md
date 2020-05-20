---
title: 'Ixclrdatamodule:: Request-Methode'
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::Request Method
helpviewer.keywords:
- IXCLRDataModule::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 3c18fc5c947cbb89fc4e9aed60d3cedcbe22d749
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420811"
---
# <a name="ixclrdatamodulerequest-method"></a>Ixclrdatamodule:: Request-Methode

Fordert an, den mit den Modul Daten angegebenen Puffer aufzufüllen.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a>Parameter

`reqCode`\
in Der zu sendende Anforderungstyp.

`inBufferSize`\
[in] Größe des Eingabe Puffers, der eingegeben werden soll.

`inBuffer`\
[in, size_is (InBufferSize)] Puffer Zeiger für die Rohdaten, die in der Anforderung gesendet werden sollen.

`outBufferSize`\
in Größe des Ausgabepuffers.

`outBuffer`\
[out, size_is (OutBufferSize)] Puffer Zeiger, der zum Speichern der Anforderungs Antwort verwendet wird.

## <a name="remarks"></a>Hinweise

Die bereitgestellte Methode ist Teil der `IXCLRDataModule` -Schnittstelle und entspricht dem 37. Slot der Tabelle der virtuellen Methode.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).
**Header:** Keine **Bibliothek:** keine **.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [IXCLRDataModule Interface-Schnittstelle](ixclrdatamodule-interface.md)
