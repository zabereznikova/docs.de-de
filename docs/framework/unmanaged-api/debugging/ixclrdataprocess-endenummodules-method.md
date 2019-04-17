---
title: IXCLRDataProcess::EndEnumModules-Methode
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: de30384b4c12c4fcac3eafe580484685f8a43fa4
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611431"
---
# <a name="ixclrdataprocessendenummodules-method"></a>IXCLRDataProcess::EndEnumModules-Methode

Gibt die Ressourcen, die von internen Iteratoren, die verwendet werden, während der Modul-Enumeration verwendet.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a>Parameter

`handle`\
[out] Ein Handle für das Auflisten der Module.

## <a name="remarks"></a>Hinweise

Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle, und mit dem 26. Steckplatz der virtuellen Methodentabelle entspricht.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).
**Header:** Keine **Bibliothek:** Keine **.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [IXCLRDataProcess-Schnittstelle](ixclrdataprocess-interface.md)
