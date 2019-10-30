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
ms.openlocfilehash: d1027aea1d800bda1654b223fec992aa70efd4b7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140708"
---
# <a name="gethashfromblob-function"></a>GetHashFromBlob-Funktion

Ruft einen Hash der Assembly unter der angegebenen Speicheradresse unter Verwendung des angegebenen Hashalgorithmus ab.

Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) -Methode.

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
in Ein Zeiger auf die Adresse des Speicherblocks, für den der Hashwert verwendet werden soll.

`cchBlob`\
in Die Länge des Speicherblocks in Bytes.

`piHashAlg`\
[in, out] Eine-Konstante, die den Hash Algorithmus angibt. Verwenden Sie 0 (null) für den Standard Algorithmus.

`pbHash`\
vorgenommen Der zurückgegebene Hash Puffer.

`cchHash`\
in Die angeforderte maximale Größe `pbHash`.

`pchHash`\
vorgenommen Die Größe (in Bytes) des zurückgegebenen `pbHash`.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** StrongName. h

**Bibliothek:** Als Ressource in Mscoree. dll enthalten

**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [GetHashFromBlob-Methode](../hosting/iclrstrongname-gethashfromblob-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
