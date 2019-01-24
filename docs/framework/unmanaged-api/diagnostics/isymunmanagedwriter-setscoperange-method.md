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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: da50542d9f57e008b31ce2e6ed9698df1275d5eb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618807"
---
# <a name="isymunmanagedwritersetscoperange-method"></a>ISymUnmanagedWriter::SetScopeRange-Methode
Definiert den Offsetbereich für den angegebenen lexikalischen Gültigkeitsbereich. Der Bereich wird der neue aktuelle Bereich und auf einen Stapel von Bereichen mithilfe von Push übertragen wird. Bereiche müssen eine Hierarchie zu bilden. Gleichgeordnete Elemente dürfen sich nicht überlappen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
#### <a name="parameters"></a>Parameter  
 `scopeId`  
 [in] Der Bereichsbezeichner für den Bereich.  
  
 `startOffset`  
 [in] Der Offset in Bytes, der ersten Anweisung im lexikalischen Gültigkeitsbereich vom Anfang der Methode.  
  
 `endOffset`  
 [in] Der Offset in Bytes, der die letzte Anweisung im lexikalischen Gültigkeitsbereich vom Anfang der Methode.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="remarks"></a>Hinweise  
 [ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) gibt einen nicht transparenter Bezeichner, die mit verwendet werden kann `ISymUnmanagedWriter::SetScopeRange` zum Definieren eines Bereichs den Anfangs- und der Endoffset zu einem späteren Zeitpunkt. In diesem Fall die Offsets zu übergeben, um `ISymUnmanagedWriter::OpenScope` und [ISymUnmanagedWriter:: CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) werden ignoriert. Bereichsbezeichnern sind nur gültig, in der aktuellen Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch
- [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
