---
title: ISymUnmanagedWriter::OpenScope-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenScope
helpviewer_keywords:
- OpenScope method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::OpenScope method [.NET Framework debugging]
ms.assetid: dbea0644-3873-4329-90b8-624163e87467
topic_type:
- apiref
ms.openlocfilehash: 5afc91d1dc6d02f052e860787ebf0858a2f5d12d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730044"
---
# <a name="isymunmanagedwriteropenscope-method"></a>ISymUnmanagedWriter::OpenScope-Methode

Öffnet einen neuen lexikalischen Gültigkeitsbereich in der aktuellen Methode. Der Gültigkeitsbereich wird zum neuen aktuellen Bereich und wird auf einen Stapel von Bereichen übermittelt. Bereiche müssen eine Hierarchie bilden. Gleich geordnete Elemente dürfen sich nicht überlappen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  

 `startOffset`  
 in Der Offset der ersten Anweisung im lexikalischen Gültigkeitsbereich (in Bytes) vom Anfang der Methode.  
  
 `pRetVal`  
 vorgenommen Ein Zeiger auf einen `ULONG32` , der den Bereichs Bezeichner empfängt.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="remarks"></a>Hinweise  

 `ISymUnmanagedWriter::OpenScope` Gibt einen nicht transparenten Bereichs Bezeichner zurück, der mit [ISymUnmanagedWriter:: SetScopeRange](isymunmanagedwriter-setscoperange-method.md) verwendet werden kann, um den Start-und Endoffset eines Bereichs zu einem späteren Zeitpunkt zu definieren. In diesem Fall werden die an `ISymUnmanagedWriter::OpenScope` -und [ISymUnmanagedWriter:: CloseScope](isymunmanagedwriter-closescope-method.md) übergebenen Offsets ignoriert. Bereichs Bezeichner sind nur in der aktuellen Methode gültig.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)
