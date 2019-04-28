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
ms.openlocfilehash: 380e248c8c4e3407fff868cdd9a5c63b63e50c69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697512"
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