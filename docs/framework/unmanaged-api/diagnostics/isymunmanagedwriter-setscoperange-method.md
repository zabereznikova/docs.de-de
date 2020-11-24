---
title: ISymUnmanagedWriter::SetScopeRange-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetScopeRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetScopeRange
helpviewer_keywords:
- SetScopeRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetScopeRange method [.NET Framework debugging]
ms.assetid: d4d98676-444b-46ca-bfe6-0d827385cd22
topic_type:
- apiref
ms.openlocfilehash: 06dff4847ec3d15f446f1c89219b10eddb8eec4f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683523"
---
# <a name="isymunmanagedwritersetscoperange-method"></a>ISymUnmanagedWriter::SetScopeRange-Methode

Definiert den Offsetbereich für den angegebenen lexikalischen Gültigkeitsbereich. Der Gültigkeitsbereich wird zum neuen aktuellen Bereich und wird auf einen Stapel von Bereichen übermittelt. Bereiche müssen eine Hierarchie bilden. Gleich geordnete Elemente dürfen sich nicht überlappen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
## <a name="parameters"></a>Parameter  

 `scopeId`  
 in Der Bereichs Bezeichner für den Bereich.  
  
 `startOffset`  
 in Der Offset (in Bytes) der ersten Anweisung im lexikalischen Gültigkeitsbereich vom Anfang der Methode.  
  
 `endOffset`  
 in Der Offset (in Bytes) der letzten Anweisung im lexikalischen Gültigkeitsbereich ab dem Anfang der Methode.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="remarks"></a>Hinweise  

 [ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) gibt einen nicht transparenten Bereichs Bezeichner zurück, der mit verwendet werden kann `ISymUnmanagedWriter::SetScopeRange` , um den Start-und Endoffset eines Bereichs zu einem späteren Zeitpunkt zu definieren. In diesem Fall werden die an `ISymUnmanagedWriter::OpenScope` -und [ISymUnmanagedWriter:: CloseScope](isymunmanagedwriter-closescope-method.md) übergebenen Offsets ignoriert. Bereichs Bezeichner sind nur in der aktuellen Methode gültig.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)
