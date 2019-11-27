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
ms.openlocfilehash: 85e65f6a3ec13c2acc31b8f87dbe4b4476ffc2a5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427867"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a>ISymUnmanagedWriter::SetMethodSourceRange-Methode
Gibt den tatsächlichen Start und das Ende einer Methode in einer Quelldatei an. Verwenden Sie diese Methode, um den Umfang einer Methode unabhängig von den Sequenz Punkten anzugeben, die in der Methode vorhanden sind.  
  
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
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
