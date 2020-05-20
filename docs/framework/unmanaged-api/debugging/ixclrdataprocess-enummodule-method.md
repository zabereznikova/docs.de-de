---
title: 'Ixclrdataprocess:: enummodule-Methode'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumModule Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumModule Method
helpviewer.keywords:
- IXCLRDataProcess::EnumModule Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 5caadcfe091393a8ff79106d57a50a532c349829
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420773"
---
# <a name="ixclrdataprocessenummodule-method"></a>Ixclrdataprocess:: enummodule-Methode

Listet die Module dieses Prozesses auf.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

## <a name="parameters"></a>Parameter

`handle`\
[in, out] Ein Handle zum Auflisten der Module.

`mod`\
vorgenommen Das-enumerationsmodul.

## <a name="remarks"></a>Hinweise

Die bereitgestellte Methode ist Teil der `IXCLRDataProcess` -Schnittstelle und entspricht dem 25. Slot der virtuellen Methoden Tabelle.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Clrdatasourcetype-Enumeration](clrdatasourcetype-enumeration.md)
- [Debuggen](index.md)
- [IXCLRDataModule Interface-Schnittstelle](ixclrdatamodule-interface.md)
- [IXCLRDataProcess-Schnittstelle](ixclrdataprocess-interface.md)
