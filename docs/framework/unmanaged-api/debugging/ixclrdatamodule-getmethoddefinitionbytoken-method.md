---
title: 'Ixclrdatamodule:: GetMethodDefinitionByToken-Methode'
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
ms.openlocfilehash: c70920205b27376d453bdd0a13223c6a5569075b
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395293"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a>Ixclrdatamodule:: GetMethodDefinitionByToken-Methode

Ruft die Methoden Definition ab, die einem angegebenen Metadatentoken entspricht.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a>Parameter

`token`\
in Das Methoden Token.

`methodDefinition`\
vorgenommen Die Methoden Definition.

## <a name="remarks"></a>Bemerkungen

Die bereitgestellte Methode ist Teil der `IXCLRDataModule` -Schnittstelle und entspricht dem 26. Slot der Tabelle der virtuellen Methode.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [IXCLRDataModule Interface-Schnittstelle](ixclrdatamodule-interface.md)
