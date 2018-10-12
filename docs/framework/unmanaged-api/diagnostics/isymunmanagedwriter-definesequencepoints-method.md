---
title: ISymUnmanagedWriter::DefineSequencePoints-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5825f0425947f109ed834879684357fef7b70959
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123773"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a>ISymUnmanagedWriter::DefineSequencePoints-Methode
Definiert eine Gruppe von Sequenzpunkten in der aktuellen Methode. Jede Startzeile und die Anfangsspalte definieren den Start einer Anweisung innerhalb einer Methode. Jede Zeile endet und die Endspalte definieren eine Anweisung innerhalb einer Methode. Die Arrays sollten in aufsteigender Reihenfolge der Offsets sortiert werden. Der Offset wird immer vom Anfang der Methode, in Byte gemessen.  
  
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
 [in] Das Document-Objekt, das für das Sequenzpunkte definiert werden.  
  
 `spCount`  
 [in] Ein `ULONG32` , der angibt, dass der Größe der einzelnen der `offsets`, `lines`, `columns`, `endLines`, und `endColumns` Puffer.  
  
 `offsets`  
 [in] Der Offset der Sequenzpunkte gemessen vom Anfang der Methode.  
  
 `lines`  
 [in] Die Anfangszeile Zahlen der Sequenzpunkte.  
  
 `columns`  
 [in] Die die Nummern der Anfangsspalten der Sequenzpunkte.  
  
 `endLines`  
 [in] Die Nummern der Endzeilen der Sequenzpunkte. Dieser Parameter ist optional.  
  
 `endColumns`  
 [in] Die Nummern der Endspalten der Sequenzpunkte. Dieser Parameter ist optional.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
