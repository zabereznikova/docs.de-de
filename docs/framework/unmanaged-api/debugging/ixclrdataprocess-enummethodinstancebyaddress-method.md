---
title: IXCLRDataProcess::EnumMethodInstanceByAddress Method
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
ms.openlocfilehash: 89b89a0cb056a0515bf0859069455a73f62aae4a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769615"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a>IXCLRDataProcess::EnumMethodInstanceByAddress Method

Listet die Methodeninstanzen dieses Prozesses, der einen Adressoffset ab.

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
[in] Ein Handle für das Auflisten der Methodeninstanzen.

`mod`\
[out] Die aufgelisteten Methodeninstanz.

## <a name="remarks"></a>Hinweise

Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle, und mit dem 28. Steckplatz der virtuellen Methodentabelle entspricht.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).   
**Header:** Keiner   
**Bibliothek:** Keiner   
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]   
 
## <a name="see-also"></a>Siehe auch

- [CLRDataSourceType-Enumeration](clrdatasourcetype-enumeration.md)
- [Debuggen](index.md)
- [IXCLRDataProcess-Schnittstelle](ixclrdataprocess-interface.md)
