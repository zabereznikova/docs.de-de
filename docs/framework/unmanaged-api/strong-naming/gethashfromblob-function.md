---
title: GetHashFromBlob-Funktion
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d9e7b52c9061a1a7b470f9d4abf735e605087dc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352073"
---
# <a name="gethashfromblob-function"></a>GetHashFromBlob-Funktion

Ruft einen Hash der Assembly unter der angegebenen Speicheradresse unter Verwendung des angegebenen Hashalgorithmus ab.

Diese Funktion wurde als veraltet markiert. Verwenden der [ICLRStrongName:: GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) Methode stattdessen.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetHashFromBlob (
    [in]  BYTE    *pbBlob,
    [in]  DWORD   cchBlob,
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE    *pbHash,
    [in]  DWORD   cchHash,
    [out] DWORD   *pchHash
);
```

## <a name="parameters"></a>Parameter

`pbBlob`\
[in] Ein Zeiger auf die Adresse des Speicherblocks, der Hashwert berechnet werden soll.

`cchBlob`\
[in] Die Länge des Speicherblocks in Bytes.

`piHashAlg`\
[in, out] Eine Konstante, die den Hashalgorithmus angibt. Verwenden Sie 0 (null), für den Standardalgorithmus.

`pbHash`\
[out] Der zurückgegebene Hashpuffer.

`cchHash`\
[in] Die angeforderte maximale Größe des `pbHash`.

`pchHash`\
[out] Die Größe in Bytes, des zurückgegebenen `pbHash`.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** StrongName.h

**Bibliothek:** Als Ressource in MsCorEE.dll enthalten

**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [GetHashFromBlob-Methode](../hosting/iclrstrongname-gethashfromblob-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)