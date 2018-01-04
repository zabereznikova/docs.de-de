---
title: ISymUnmanagedWriter::CloseScope-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.CloseScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d47be1d220729ed32fcf77a77e611003085c15d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterclosescope-method"></a>ISymUnmanagedWriter::CloseScope-Methode
Schließt den aktuellen lexikalischen Gültigkeitsbereich.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
#### <a name="parameters"></a>Parameter  
 `endOffset`  
 [in] Der Offset vom Anfang der Methode von den Punkt am Ende der letzten Anweisung im lexikalischen Gültigkeitsbereich, in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="remarks"></a>Hinweise  
 Nachdem ein Bereich geschlossen wurde, können keine weitere Variablen darin definiert werden.  
  
 [ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) gibt einen nicht transparenter Bezeichner, die mit verwendet werden kann [ISymUnmanagedWriter:: SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) zum später definieren eines Bereichs den Anfangs- und der Endoffset. In diesem Fall werden die an `ISymUnmanagedWriter::OpenScope` und `ISymUnmanagedWriter::CloseScope` übergebenen Offsets ignoriert. Bereichsbezeichnern sind nur in der aktuellen Methode gültig.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
