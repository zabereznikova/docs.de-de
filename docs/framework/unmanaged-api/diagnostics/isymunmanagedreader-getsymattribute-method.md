---
title: ISymUnmanagedReader::GetSymAttribute-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
ms.openlocfilehash: b7e2814e56765037b69c6ef7ca0ba610dd7d3c95
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614928"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a>ISymUnmanagedReader::GetSymAttribute-Methode
Ruft ein benutzerdefiniertes Attribut basierend auf seinem Namen ab. Im Gegensatz zu benutzerdefinierten Metadaten-Attributen werden diese benutzerdefinierten Attribute im Symbol Speicher gespeichert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `parent`  
 in Das Metadatentoken für das-Objekt, für das das Attribut angefordert wird.  
  
 `name`  
 in Ein Zeiger auf die Variable, die das abzurufende Attribut angibt.  
  
 `cBuffer`  
 [in] Die Größe des `buffer`-Arrays.  
  
 `pcBuffer`  
 vorgenommen Ein Zeiger auf die Variable, die die Länge der Attributdaten empfängt.  
  
 `buffer`  
 vorgenommen Ein Zeiger auf die Variable, die die Attributdaten empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedReader-Schnittstelle](isymunmanagedreader-interface.md)
