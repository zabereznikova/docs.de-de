---
title: 'Ixclrdatamethoddefinition:: enuminstance-Methode'
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
ms.openlocfilehash: b6393d7fa4853c230203521e665bbe89d7b228e2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790440"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a>Ixclrdatamethoddefinition:: enuminstance-Methode

Listet die Instanzen dieser Methoden Definition auf.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a>Parameters

`handle`\
[in, out] Ein Handle zum Auflisten der-Instanzen.

`instance`\
vorgenommen Die Enumerationsinstanz.

## <a name="remarks"></a>Hinweise

Die bereitgestellte Methode ist Teil der `IXCLRDataMethodDefinition`-Schnittstelle und entspricht dem vierten Slot der Tabelle der virtuellen Methode.

## <a name="requirements"></a>-Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Clrdatasourcetype-Enumeration](clrdatasourcetype-enumeration.md)
- [Debuggen](index.md)
- [Ixclrdatamethoddefinition-Schnittstelle](ixclrdatamethoddefinition-interface.md)
- [Ixclrdatamethodinstance-Schnittstelle](ixclrdatamethodinstance-interface.md)
