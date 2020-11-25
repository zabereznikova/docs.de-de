---
title: ISymUnmanagedWriter::CloseScope-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
ms.openlocfilehash: 561a6348b9976789b02961fadb37d9127f5a6a13
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713040"
---
# <a name="isymunmanagedwriterclosescope-method"></a>ISymUnmanagedWriter::CloseScope-Methode

Schließt den aktuellen lexikalischen Gültigkeitsbereich.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a>Parameter  

 `endOffset`  
 in Der Offset vom Anfang der Methode des Punkts am Ende der letzten Anweisung im lexikalischen Gültigkeitsbereich (in Bytes).  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="remarks"></a>Hinweise  

 Nachdem ein Bereich geschlossen wurde, können darin keine weiteren Variablen definiert werden.  
  
 [ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) gibt einen nicht transparenten Bereichs Bezeichner zurück, der mit [ISymUnmanagedWriter:: SetScopeRange](isymunmanagedwriter-setscoperange-method.md) verwendet werden kann, um den Start-und Endoffset eines Bereichs zu einem späteren Zeitpunkt zu definieren. In diesem Fall werden die an `ISymUnmanagedWriter::OpenScope` und `ISymUnmanagedWriter::CloseScope` übergebenen Offsets ignoriert. Bereichs Bezeichner sind nur in der aktuellen Methode gültig.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)
