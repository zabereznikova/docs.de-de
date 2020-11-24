---
title: ISymUnmanagedWriter::SetMethodSourceRange-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetMethodSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetMethodSourceRange
helpviewer_keywords:
- SetMethodSourceRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetMethodSourceRange method [.NET Framework debugging]
ms.assetid: c698b86e-ace7-4b21-9549-f52d6a034959
topic_type:
- apiref
ms.openlocfilehash: a918b5c2334683348adc6a7382527faedb52d7b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683536"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a>ISymUnmanagedWriter::SetMethodSourceRange-Methode

Gibt den tatsächlichen Anfang und das tatsächliche Ende einer Methode in einer Quelldatei an. Verwenden Sie diese Methode, um den Umfang einer Methode unabhängig von den Sequenz Punkten anzugeben, die in der Methode vorhanden sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a>Parameter  

 `startDoc`  
 in Ein Zeiger auf das Dokument, das die Anfangsposition enthält.  
  
 `startLine`  
 in Die Anfangs Zeilennummer.  
  
 `startColumn`  
 in Die Anfangs Spalte.  
  
 `endDoc`  
 in Ein Zeiger auf das Dokument, das die Endposition enthält.  
  
 `endLine`  
 in Die Endzeilennummer.  
  
 `endColumn`  
 in Die Nummer der Endspalte.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)
