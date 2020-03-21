---
title: IXCLRDataProcess::EnumMethodInstanceByAddress-Methode
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: afc5fc377dd45d5e8d4d2d7b3385ca0524df69e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176655"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a>IXCLRDataProcess::EnumMethodInstanceByAddress-Methode

Zählt die Methodeninstanzen dieses Prozesses auf, beginnend mit einem Adressoffset.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a>Parameter

`handle`\
[in] Ein Handle zum Aufzählen der Methodeninstanzen.

`mod`\
[out] Die aufgezählte Methodeninstanz.

## <a name="remarks"></a>Bemerkungen

Die bereitgestellte Methode `IXCLRDataProcess` ist Teil der Schnittstelle und entspricht dem 28. Slot der virtuellen Methodentabelle.

## <a name="requirements"></a>Requirements (Anforderungen)

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).
**Kopfzeile:** Keine **Bibliothek:** Keine **.NET Framework-Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Weitere Informationen

- [CLRDataSourceType-Enumeration](clrdatasourcetype-enumeration.md)
- [Debuggen](index.md)
- [IXCLRDataProcess-Schnittstelle](ixclrdataprocess-interface.md)
