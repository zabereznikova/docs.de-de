---
title: ISymUnmanagedWriter::SetScopeRange-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.SetScopeRange
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::SetScopeRange
helpviewer_keywords:
- SetScopeRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetScopeRange method [.NET Framework debugging]
ms.assetid: d4d98676-444b-46ca-bfe6-0d827385cd22
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b86df423d53c9fa3a738c603d6cc575add594cae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwritersetscoperange-method"></a>ISymUnmanagedWriter::SetScopeRange-Methode
Definiert den Offsetbereich für den angegebenen lexikalischen Gültigkeitsbereich. Der Bereich wird der neue aktuelle Bereich und wird auf einen Stapel von Bereichen abgelegt. Bereiche müssen eine Hierarchie zu bilden. Gleichgeordnete Elemente dürfen sich nicht überlappen.  
  
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
 [in] Der Offset in Bytes, der ersten Anweisung im lexikalischen Gültigkeitsbereich ab dem Anfang der Methode.  
  
 `endOffset`  
 [in] Der Offset in Bytes, der die letzte Anweisung im lexikalischen Gültigkeitsbereich ab dem Anfang der Methode.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="remarks"></a>Hinweise  
 [ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) gibt einen nicht transparenter Bezeichner, die mit verwendet werden kann `ISymUnmanagedWriter::SetScopeRange` zum Definieren eines Bereichs den Anfangs- und Endoffset zu einem späteren Zeitpunkt. In diesem Fall das an die Offsets `ISymUnmanagedWriter::OpenScope` und [ISymUnmanagedWriter:: CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) werden ignoriert. Bereichsbezeichnern sind nur in der aktuellen Methode gültig.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
