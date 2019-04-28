---
title: IMetaDataTables::GetUserString-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserString
helpviewer_keywords:
- IMetaDataTables::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 35b8f0d6-9aba-4714-adb2-62020a38fb7e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0fefbab6b2ea9fbbfd90e03c41578a924f99c7a0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645200"
---
# <a name="imetadatatablesgetuserstring-method"></a>IMetaDataTables::GetUserString-Methode

Ruft die hartcodierten Zeichenfolge am angegebenen Index in die Zeichenfolgenspalte im aktuellen Bereich ab.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetUserString (
    [in]  ULONG       ixUserString,
    [out] ULONG       *pcbData,
    [out] const void  **ppData
);
```

## <a name="parameters"></a>Parameter

`ixUserString`\
[in] Der Indexwert aus dem die hartcodierten Zeichenfolge abgerufen wird.

`pcbData`\
[out] Ein Zeiger auf die Größe des `ppData`.

`ppData`\
[out] Ein Zeiger auf einen Zeiger auf die zurückgegebene Zeichenfolge.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** Cor.h

**Bibliothek:** Als Ressource in MsCorEE.dll verwendet

**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [IMetaDataTables-Schnittstelle](imetadatatables-interface.md)
- [IMetaDataTables2-Schnittstelle](imetadatatables2-interface.md)