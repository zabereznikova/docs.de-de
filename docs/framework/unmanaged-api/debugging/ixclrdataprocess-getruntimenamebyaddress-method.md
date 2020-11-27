---
title: 'Ixclrdataprocess:: getruntimenamebyaddress-Methode'
ms.date: 4/27/2020
api.name:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: tommcdon
ms.author: tommcdon
ms.openlocfilehash: 6648bdafe6e5cdd402bcfa02a148c57f0f1e209e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275566"
---
# <a name="ixclrdataprocessgetruntimenamebyaddress-method"></a>Ixclrdataprocess:: getruntimenamebyaddress-Methode

Ruft einen Namen für die angegebene Adresse ab.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetRuntimeNameByAddress(
    [in] CLRDATA_ADDRESS address,
    [in] ULONG32 flags,
    [in] ULONG32 bufLen,
    [out] ULONG32 *nameLen,
    [out, size_is(bufLen)] WCHAR nameBuf[],
    [out] CLRDATA_ADDRESS* displacement
);
```

## <a name="parameters"></a>Parameter

`address`\
in Ein- `CLRDATA_ADDRESS` Wert, der eine Code Adresse darstellt.

`flags`\
in Auf "0" festgelegt.

`bufLen`\
in Die Länge des Puffers.

`namLen`\
vorgenommen Ein Zeiger auf die Anzahl der zurückgegebenen Zeichen.

`namBuf`\
[out, size_is ( `bufLen` )] der Eingabepuffer der Länge `bufLen` , in der der Lauf Zeit Name gespeichert wird.

`displacement`\
vorgenommen Ein `CLRDATA_ADDRESS` Zeiger auf den Code Offset des zurückgegebenen Symbols.

## <a name="remarks"></a>Hinweise

Die bereitgestellte Methode ist Teil der `IXCLRDataProcess` -Schnittstelle und entspricht dem 16. Slot der Virtual-Method-Tabelle.

> [!NOTE]
> Wenn der Puffer nicht groß genug für den Namen ist, gibt diese Methode zurück `S_FALSE` und legt `nameLen` auf die erforderliche Pufferlänge fest.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Siehe [System Anforderungen](../../get-started/system-requirements.md)\
**Header:** Gar
**Bibliothek:** Gar
**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Weitere Informationen

- [Debuggen](index.md)
- [IXCLRDataProcess-Schnittstelle](ixclrdataprocess-interface.md)
