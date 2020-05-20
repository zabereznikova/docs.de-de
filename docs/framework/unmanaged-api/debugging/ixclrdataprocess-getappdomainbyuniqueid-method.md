---
title: 'Ixclrdataprocess:: getappdomainbyuniqueid-Methode'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
helpviewer.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: bb02ffed09cbcc31e653bfd3165050c247908c5d
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420782"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a>Ixclrdataprocess:: getappdomainbyuniqueid-Methode

Ruft ein-Attribut `AppDomain` in einem Prozess auf der Grundlage seines eindeutigen Bezeichners ab.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

## <a name="parameters"></a>Parameter

`id`\
in Der eindeutige Bezeichner der AppDomain.

`appDomain`\
vorgenommen Die AppDomain

## <a name="remarks"></a>Hinweise

Die bereitgestellte Methode ist Teil der `IXCLRDataProcess` -Schnittstelle und entspricht dem 20. Slot der Tabelle der virtuellen Methode. Der `IXCLRDataAppDomain*` zurückgegebene wird für die Interaktion mit anderen APIs verwendet.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).
**Header:** Keine **Bibliothek:** keine **.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [IXCLRDataProcess-Schnittstelle](ixclrdataprocess-interface.md)
