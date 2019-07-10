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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4087bdd82041152a9946a576e0eb96bf63f177c7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777273"
---
# <a name="isymunmanagedwriterinitialize2-method"></a>ISymUnmanagedWriter::Initialize2-Methode
Legt die Metadatenemitter-Schnittstelle mit der dieser Writer zugewiesen werden soll, und den Namen der Ausgabedatei, die Debugsymbole geschrieben werden. Mit dieser Methode können auch den endgültigen Speicherort, der die Programmdatenbankdatei (PDB) festgelegt.  
  
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
 [in] Ein Zeiger auf die Metadatenemitter-Schnittstelle.  
  
 `tempfilename`  
 [in] Ein Zeiger auf eine `WCHAR` , enthält der Dateiname, der die Debugsymbole geschrieben werden. Wenn für einen Writer, der keine Dateinamen verwendet, ein Dateiname angegeben ist, wird dieser Parameter ignoriert.  
  
 `pIStream`  
 [in] Wenn angegeben, gibt der Symbolwriter die Symbole in der angegebenen <xref:System.Runtime.InteropServices.ComTypes.IStream> statt in der Datei angegeben, der `filename` Parameter. Der Parameter `pIStream` ist optional.  
  
 `fFullBuild`  
 [in] `true` ist dies eine vollständige Neuerstellung `false` ist dies eine inkrementelle Kompilierung.  
  
 `finalfilename`  
 [in] Ein Zeiger auf eine `WCHAR` d. h. die Pfadzeichenfolge, um den endgültigen Speicherort der PDB-Datei.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [Initialize-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)
