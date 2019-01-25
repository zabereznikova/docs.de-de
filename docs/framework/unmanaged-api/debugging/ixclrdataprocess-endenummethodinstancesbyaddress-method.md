---
title: IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 67978e49a8c23c4b25234ecbb3639c696c7232f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655646"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a>IXCLRDataProcess::EndEnumMethodInstancesByAddress Method

Gibt die vom internen Iteratoren, die verwendet werden, während der Instanzenumeration verwendeten Ressourcen frei.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

### <a name="parameters"></a>Parameter

`handle` [out] Ein Handle für das Auflisten der Methodeninstanzen.

## <a name="remarks"></a>Hinweise

Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle, und mit dem 29. Steckplatz der virtuellen Methodentabelle entspricht.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Keine  
**Bibliothek:** Keine  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [CLRDataSourceType-Enumeration](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [IXCLRDataProcess-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
