---
title: ISymUnmanagedWriter::Initialize2-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize2
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize2 method [.NET Framework debugging]
- Initialize2 method [.NET Framework debugging]
ms.assetid: 93de56b6-4ae8-4cca-acdc-25a434623509
topic_type:
- apiref
ms.openlocfilehash: 93a96a5da3342f4beff611de1d448dc199dd39dd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687129"
---
# <a name="isymunmanagedwriterinitialize2-method"></a>ISymUnmanagedWriter::Initialize2-Methode

Legt die Metadatenemitter-Schnittstelle fest, der dieser Writer zugeordnet wird, und legt den Namen der Ausgabedatei fest, in die die Debugsymbole geschrieben werden. Mit dieser Methode können Sie auch den endgültigen Speicherort der Programm Datenbankdatei (PDB-Datei) festlegen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
## <a name="parameters"></a>Parameter  

 `emitter`  
 in Ein Zeiger auf die Metadatenemitter-Schnittstelle.  
  
 `tempfilename`  
 in Ein Zeiger auf einen-Wert `WCHAR` , der den Namen der Datei enthält, in die die Debugsymbole geschrieben werden. Wenn für einen Writer, der keine Dateinamen verwendet, ein Dateiname angegeben ist, wird dieser Parameter ignoriert.  
  
 `pIStream`  
 in Wenn angegeben, gibt der Symbolwriter die Symbole <xref:System.Runtime.InteropServices.ComTypes.IStream> anstelle der Datei, die im-Parameter angegeben ist, in den angegebenen aus `filename` . Das `pIStream` ist optional.  
  
 `fFullBuild`  
 [in] `true` , wenn es sich um eine vollständige Neuerstellung handelt. `false` Wenn dies eine inkrementelle Kompilierung ist.  
  
 `finalfilename`  
 in Ein Zeiger auf einen `WCHAR` , der die Pfad Zeichenfolge zum endgültigen Speicherort der PDB-Datei ist.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)
- [Initialize-Methode](isymunmanagedwriter-initialize-method.md)
