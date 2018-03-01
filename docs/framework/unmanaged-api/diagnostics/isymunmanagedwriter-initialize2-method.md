---
title: ISymUnmanagedWriter::Initialize2-Methode
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 015c7d43a856990251b3e67febe685759cc4e5fb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterinitialize2-method"></a>ISymUnmanagedWriter::Initialize2-Methode
Legt die Metadatenemitter-Schnittstelle mit der dieser Writer zugewiesen werden soll, und den Namen der Ausgabedatei, den die Debugsymbole geschrieben werden. Dieser Methode können auch den endgültigen Speicherort der Programmdatenbankdatei (PDB) festgelegt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
#### <a name="parameters"></a>Parameter  
 `emitter`  
 [in] Ein Zeiger auf die Metadatenemitter-Schnittstelle.  
  
 `tempfilename`  
 [in] Ein Zeiger auf eine `WCHAR` , enthält der Dateiname, der in die die Debugsymbole geschrieben werden. Wenn für einen Writer, der keine Dateinamen verwendet, ein Dateiname angegeben ist, wird dieser Parameter ignoriert.  
  
 `pIStream`  
 [in] Wenn angegeben, gibt der Symbolwriter die Symbole in der angegebenen <xref:System.Runtime.InteropServices.ComTypes.IStream> anstatt in die angegebene Datei der `filename` Parameter. Der Parameter `pIStream` ist optional.  
  
 `fFullBuild`  
 [in] `true` ist dies eine vollständige Neuerstellung; `false` ist dies eine inkrementelle Kompilierung.  
  
 `finalfilename`  
 [in] Ein Zeiger auf eine `WCHAR` also die Pfadzeichenfolge an den endgültigen Speicherort der PDB-Datei.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [Initialize-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)
