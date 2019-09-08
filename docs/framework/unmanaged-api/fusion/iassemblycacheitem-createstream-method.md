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
ms.openlocfilehash: 5af7dc4e1694b66fc4a5ce37e515c71e9fa3db49
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796732"
---
# <a name="iassemblycacheitemcreatestream-method"></a>IAssemblyCacheItem::CreateStream-Methode

Erstellt einen Stream mit dem angegebenen Namen und Format.

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
in In Fusion. idl definierte Flags.

`pszStreamName`\
in Der Name des Streams, der erstellt werden soll.

`dwFormat`\
in Das Format der Datei, die gestreamt werden soll.

`dwFormatFlags`\
in Format spezifische Flags, die in Fusion. idl definiert sind.

`ppIStream`\
vorgenommen Ein Zeiger auf die Adresse der zurückgegebenen [IStream](/windows/desktop/api/objidl/nn-objidl-istream) -Instanz.

`puliMaxSize`\
[in, optional] Die maximale Größe des Streams, auf den `ppIStream`von verwiesen wird.

## <a name="requirements"></a>Anforderungen

**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** Fusion. h

**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [IAssemblyCacheItem-Schnittstelle](iassemblycacheitem-interface.md)
