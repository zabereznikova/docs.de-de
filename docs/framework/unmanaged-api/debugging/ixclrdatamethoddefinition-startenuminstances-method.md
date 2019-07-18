---
title: IXCLRDataMethodDefinition::StartEnumInstances-Methode
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::StartEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 89473f2a6a3da73ee5d172a3700bdb4d624278ff
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756300"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a>IXCLRDataMethodDefinition::StartEnumInstances-Methode

Stellt ein Handle für die Enumeration der Methodeninstanzen für einen bestimmten `IXCLRDataAppDomain`.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a>Parameter

`appDomain`\
[in] Eine Anwendungsdomäne für die Enumeration.

`handle`\
[out] Ein Handle für das Auflisten der Instanzen.

## <a name="remarks"></a>Hinweise

Die angegebene Methode ist Teil der `IXCLRDataMethodDefinition` Schnittstelle, und im dritten Einschubfach von der Tabelle virtueller Methoden entspricht.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Keiner  
**Bibliothek:** Keiner  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [CLRDataSourceType-Enumeration](clrdatasourcetype-enumeration.md)
- [Debuggen](index.md)
- [IXCLRDataMethodDefinition-Schnittstelle](ixclrdatamethoddefinition-interface.md)
