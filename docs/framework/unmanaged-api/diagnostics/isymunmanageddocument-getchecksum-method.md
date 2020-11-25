---
title: ISymUnmanagedDocument::GetCheckSum-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type:
- apiref
ms.openlocfilehash: 4030da31400b7075952d146e5d6740306863e9ad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721087"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a>ISymUnmanagedDocument::GetCheckSum-Methode

Ruft die Prüfsumme ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a>Parameter  

 `cData`  
 in Die Länge des Puffers, der vom-Parameter bereitgestellt wird. `data`  
  
 `pcData`  
 vorgenommen Die Größe und Länge der Prüfsumme in Bytes.  
  
 `data`  
 vorgenommen Der Puffer, der die Prüfsumme empfängt.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls ein Fehlercode.  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedDocument-Schnittstelle](isymunmanageddocument-interface.md)
