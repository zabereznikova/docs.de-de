---
title: ISymUnmanagedReader::GetSymbolStoreFileName-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymbolStoreFileName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymbolStoreFileName
helpviewer_keywords:
- GetSymbolStoreFileName method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymbolStoreFileName method [.NET Framework debugging]
ms.assetid: c84f4846-9bc8-44a4-9a76-e39106d6d8b2
topic_type:
- apiref
ms.openlocfilehash: df503e44f20a0b1f02e2c609cc4b52712520faea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720567"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a>ISymUnmanagedReader::GetSymbolStoreFileName-Methode

Gibt den Dateinamen des Symbol Speicher auf dem Datenträger an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a>Parameter  

 `cchName`  
 in Die Größe des `szName` Puffers.  
  
 `pcchName`  
 vorgenommen Ein Zeiger auf die Variable, die die Länge des in zurückgegebenen namens `szName` einschließlich der NULL-Beendigung empfängt.  
  
 `szName`  
 vorgenommen Ein Zeiger auf die Variable, die den Dateinamen des Symbol Speicher empfängt.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedReader-Schnittstelle](isymunmanagedreader-interface.md)
