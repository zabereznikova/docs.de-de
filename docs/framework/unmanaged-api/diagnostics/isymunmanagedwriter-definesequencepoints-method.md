---
title: ISymUnmanagedWriter::DefineSequencePoints-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedWriter.DefineSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineSequencePoints
helpviewer_keywords:
- DefineSequencePoints method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineSequencePoints method [.NET Framework debugging]
ms.assetid: 64202baf-be6b-40ba-8162-8cc6c0c9b8e1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2e1dcc427a6d034ce108ca66f71cc24b1050a72f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a>ISymUnmanagedWriter::DefineSequencePoints-Methode
Definiert eine Gruppe von Sequenzpunkten in der aktuellen Methode. Jede Anfangszeile und die Anfangsspalte definieren den Start einer Anweisung innerhalb einer Methode. Jede Zeile endet und Endspalte definieren eine Anweisung innerhalb einer Methode. Die Arrays müssen in aufsteigender Reihenfolge der Offsets sortiert werden. Der Offset wird immer vom Anfang der Methode in Byte gemessen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `document`  
 [in] Das Dokumentobjekt, für das die Sequenzpunkte definiert werden.  
  
 `spCount`  
 [in] Ein `ULONG32` an, die die Größe der einzelnen gibt die `offsets`, `lines`, `columns`, `endLines`, und `endColumns` Puffer.  
  
 `offsets`  
 [in] Der Offset der Sequenzpunkte gemessen vom Anfang der Methode.  
  
 `lines`  
 [in] Die Anfangszeilennummern der Sequenzpunkte.  
  
 `columns`  
 [in] Die ersten Spaltennummern der Sequenzpunkte.  
  
 `endLines`  
 [in] Die Endzeilennummern der Sequenzpunkte. Dieser Parameter ist optional.  
  
 `endColumns`  
 [in] Die Endadresse Spaltennummern der Sequenzpunkte. Dieser Parameter ist optional.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
