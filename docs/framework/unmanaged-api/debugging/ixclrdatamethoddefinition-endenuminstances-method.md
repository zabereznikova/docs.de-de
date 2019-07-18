---
title: IXCLRDataMethodDefinition::EndEnumInstances-Methode
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EndEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 3d9e3ca31eddff9d08607c4d6d37ca76139bf5d2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756304"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a>IXCLRDataMethodDefinition::EndEnumInstances-Methode

Gibt die vom internen Iteratoren, die verwendet werden, während der Instanzenumeration verwendeten Ressourcen frei.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a>Parameter

`handle`\
[out] Ein Handle für das Auflisten der Instanzen.

## <a name="remarks"></a>Hinweise

Die angegebene Methode ist Teil der `IXCLRDataMethodDefinition` Schnittstelle, und mit dem fünften Steckplatz der virtuellen Methodentabelle entspricht.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Keiner  
**Bibliothek:** Keiner  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [IXCLRDataMethodDefinition-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
