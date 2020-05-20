---
title: ISymUnmanagedWriter::DefineField-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineField
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type:
- apiref
ms.openlocfilehash: aba551a1973a41a909869316cda07e8d655e9882
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614837"
---
# <a name="isymunmanagedwriterdefinefield-method"></a>ISymUnmanagedWriter::DefineField-Methode
Definiert eine einzelne Variable, die sich nicht innerhalb einer Methode befindet. Diese Methode wird für bestimmte Felder in Klassen, Bitfeldern usw. verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a>Parameter  
 `parent`  
 in Der Metadatentyp oder das Methoden Token.  
  
 `name`  
 in Der Feldname.  
  
 `attributes`  
 in Die Feld Attribute.  
  
 `cSig`  
 in Ein mit `ULONG32` der Größe (in Zeichen) des Puffers, der die Feld Signatur enthalten muss.  
  
 `signature`  
 in Das Array von Feld Signaturen.  
  
 `addrKind`  
 in Der adrestyp.  
  
 `addr1`  
 in Die erste Adresse für die Feld Angabe.  
  
 `addr2`  
 in Die zweite Adresse für die Feld Angabe.  
  
 `addr3`  
 in Die dritte Adresse für die Feld Angabe.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)
