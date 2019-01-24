---
title: IXCLRDataMethodDefinition::EnumInstance-Methode
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EnumInstance Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 0fbb246f8c4bf791dd705aedf8eab6ef8bfeae56
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680264"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a>IXCLRDataMethodDefinition::EnumInstance-Methode

Listet die Instanzen dieser Definition der Methode.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

### <a name="parameters"></a>Parameter

`handle` [in, out] Ein Handle für das Auflisten der Instanzen.

`instance` [out] Die aufgelisteten Instanz.

## <a name="remarks"></a>Hinweise

Die angegebene Methode ist Teil der `IXCLRDataMethodDefinition` Schnittstelle, und mit dem vierten Steckplatz der virtuellen Methodentabelle entspricht.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Keine  
**Bibliothek:** Keine  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [CLRDataSourceType-Enumeration](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [IXCLRDataMethodDefinition-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
- [IXCLRDataMethodInstance-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md)
