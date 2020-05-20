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
ms.openlocfilehash: 8889c412f414f38d1d18d33ec297e82fd052280d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614798"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a>ISymUnmanagedWriter::DefineSequencePoints-Methode
Definiert eine Gruppe von Sequenzpunkten in der aktuellen Methode. Jede Start-und Start Spalte definiert den Anfang einer Anweisung innerhalb einer Methode. Jede Endzeile und Endspalte definieren das Ende einer Anweisung innerhalb einer Methode. Die Arrays sollten in aufsteigender Reihenfolge der Offsets sortiert werden. Der Offset wird immer vom Anfang der Methode (in Bytes) gemessen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `document`  
 in Das Dokument Objekt, für das die Sequenz Punkte definiert werden.  
  
 `spCount`  
 in Eine `ULONG32` , die die Größe der einzelnen `offsets` `lines` Puffer,,, `columns` und angibt `endLines` `endColumns` .  
  
 `offsets`  
 in Der Offset der Sequenz Punkte, gemessen ab dem Anfang der Methode.  
  
 `lines`  
 in Die Anfangs Zeilennummern der Sequenz Punkte.  
  
 `columns`  
 in Die Nummern der Anfangs Spalten der Sequenz Punkte.  
  
 `endLines`  
 in Die Endzeilennummern der Sequenz Punkte. Dieser Parameter ist optional.  
  
 `endColumns`  
 in Die Nummer der Endspalte der Sequenz Punkte. Dieser Parameter ist optional.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)
