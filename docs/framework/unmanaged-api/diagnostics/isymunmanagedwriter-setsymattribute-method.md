---
title: ISymUnmanagedWriter::SetSymAttribute-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
ms.openlocfilehash: 484affb2ca87ca50a805d1bb46b7749d294d09f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683510"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a>ISymUnmanagedWriter::SetSymAttribute-Methode

Definiert ein benutzerdefiniertes Attribut basierend auf seinem Namen. Diese Attribute werden im Symbol Speicher gespeichert, im Gegensatz zu benutzerdefinierten Metadaten-Attributen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a>Parameter  

 `parent`  
 in Das Metadatentoken, für das das Attribut definiert wird.  
  
 `name`  
 in Ein Zeiger auf einen `WCHAR` , der den Attributnamen enthält.  
  
 `cData`  
 in Ein-Wert `ULONG32` , der die Größe des `data` Arrays angibt.  
  
 `data`  
 in Der Attribut Wert.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)
