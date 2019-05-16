---
title: IAssemblyCacheItem::CreateStream-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a98273307003485202d8c12d5c27fda04ff5a0ae
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65629877"
---
# <a name="iassemblycacheitemcreatestream-method"></a>IAssemblyCacheItem::CreateStream-Methode

Erstellt einen Datenstrom mit dem angegebenen Namen und Format.

## <a name="syntax"></a>Syntax

```cpp
HRESULT CreateStream (
    [in]  DWORD dwFlags,
    [in]  LPCWSTR pszStreamName,
    [in]  DWORD dwFormat,
    [in]  DWORD dwFormatFlags,
    [out] IStream **ppIStream,
    [in, optional] ULARGE_INTEGER *puliMaxSize
);
```

## <a name="parameters"></a>Parameter

`dwFlags`\
[in] Flags, die in Fusion.idl definiert sind.

`pszStreamName`\
[in] Der Name des zu erstellenden Datenstroms.

`dwFormat`\
[in] Das Format der Datei, die gestreamt werden.

`dwFormatFlags`\
[in] Formatspezifische-Flags in Fusion.idl definiert sind.

`ppIStream`\
[out] Ein Zeiger auf die Adresse des zurückgegebenen [IStream](/windows/desktop/api/objidl/nn-objidl-istream) Instanz.

`puliMaxSize`\
[in, optional] Die maximale Größe des Streams verweist `ppIStream`.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** Fusion.h

**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [IAssemblyCacheItem-Schnittstelle](iassemblycacheitem-interface.md)
