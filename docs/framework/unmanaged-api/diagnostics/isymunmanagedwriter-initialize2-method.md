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
ms.openlocfilehash: 041df959139a0be77f40d6aa5655ff15f93fb26f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427943"
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
 in Ein Zeiger auf eine `WCHAR`, die den Namen der Datei enthält, in die die Debugsymbole geschrieben werden. Wenn für einen Writer, der keine Dateinamen verwendet, ein Dateiname angegeben ist, wird dieser Parameter ignoriert.  
  
 `pIStream`  
 in Wenn angegeben, gibt der Symbolwriter die Symbole anstelle der im `filename`-Parameter angegebenen Datei in die angegebene <xref:System.Runtime.InteropServices.ComTypes.IStream> aus. Der Parameter `pIStream` ist optional.  
  
 `fFullBuild`  
 [in] `true`, wenn dies eine vollständige Neuerstellung ist. `false` wenn dies eine inkrementelle Kompilierung ist.  
  
 `finalfilename`  
 in Ein Zeiger auf eine `WCHAR`, die die Pfad Zeichenfolge zum endgültigen Speicherort der PDB-Datei ist.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [Initialize-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)
