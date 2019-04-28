---
title: IXCLRDataModule::GetMethodDefinitionByToken-Methode
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetMethodDefinitionByToken Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method
helpviewer.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 727005437289b4bc66ab90f280b80a79f4db06db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775496"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a>IXCLRDataModule::GetMethodDefinitionByToken-Methode

Ruft die Definition der Methode für einen angegebenen Metadatentoken ab.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a>Parameter

`token`\
[in] Das Methodentoken.

`methodDefinition`\
[out] Die Definition der Methode.

## <a name="remarks"></a>Hinweise

Die angegebene Methode ist Teil der `IXCLRDataModule` Schnittstelle, und mit dem 25. Steckplatz der virtuellen Methodentabelle entspricht.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Keiner  
**Bibliothek:** Keiner  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
 
## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [IXCLRDataModule-Schnittstelle](ixclrdatamodule-interface.md)
