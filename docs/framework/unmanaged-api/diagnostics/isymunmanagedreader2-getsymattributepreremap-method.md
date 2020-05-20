---
title: ISymUnmanagedReader2::GetSymAttributePreRemap-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetSymAttributePreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type:
- apiref
ms.openlocfilehash: e6248aba1c41b2815f2806942d419da869ed94b4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614915"
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a>ISymUnmanagedReader2::GetSymAttributePreRemap-Methode
Ruft ein benutzerdefiniertes Attribut basierend auf seinem Namen ab. Im Gegensatz zu benutzerdefinierten Metadaten-Attributen werden diese Attribute im Symbol Speicher gespeichert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `parent`  
 in Das Metadatentoken des übergeordneten Elements.  
  
 `name`  
 in Ein Zeiger auf einen `WCHAR` , der den Namen enthält.  
  
 `cBuffer`  
 in Ein-Wert `ULONG32` , der die Größe des `buffer` Arrays angibt.  
  
 `pcBuffer`  
 vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers empfängt, der zum enthalten der Attribut Bytes erforderlich ist.  
  
 `buffer`  
 vorgenommen Ein Zeiger auf den Puffer, der die Attribut Bytes empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedReader2-Schnittstelle](isymunmanagedreader2-interface.md)
