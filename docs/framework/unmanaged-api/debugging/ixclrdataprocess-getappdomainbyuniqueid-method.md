---
title: IXCLRDataProcess::GetAppDomainByUniqueId Method
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
ms.openlocfilehash: 8b468d40ef8eb523ba8881627fae15cf9b7c7b80
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775258"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a>IXCLRDataProcess::GetAppDomainByUniqueId Method

Ruft eine `AppDomain` in einem Prozess, der auf Grundlage seines eindeutigen Bezeichners.

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
[in] Der eindeutige Bezeichner der Anwendungsdomäne

`appDomain`\
[out] Der AppDomain

## <a name="remarks"></a>Hinweise

Die angegebene Methode ist Teil der `IXCLRDataProcess` Schnittstelle und zum 20. Steckplatz der virtuellen Methodentabelle entspricht. Die `IXCLRDataAppDomain*` zurückgegeben, die für die Interaktion mit anderen APIs verwendet wird.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).
**Header:** Keine **Bibliothek:** Keine **.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [IXCLRDataProcess-Schnittstelle](ixclrdataprocess-interface.md)
