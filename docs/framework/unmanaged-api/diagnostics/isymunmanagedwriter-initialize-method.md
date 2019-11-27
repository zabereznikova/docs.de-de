---
title: ISymUnmanagedWriter::Initialize-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type:
- apiref
ms.openlocfilehash: 6e9ab623d5fe9fcfda2305df078e988a561afdc5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427978"
---
# <a name="isymunmanagedwriterinitialize-method"></a>ISymUnmanagedWriter::Initialize-Methode
Legt die Metadatenemitter-Schnittstelle fest, der dieser Writer zugeordnet wird, und legt den Namen der Ausgabedatei fest, in die die Debugsymbole geschrieben werden.  
  
 Diese Methode kann nur einmal aufgerufen werden und muss vor allen anderen Writer-Methoden aufgerufen werden. Einige Writer benötigen möglicherweise einen Dateinamen. Allerdings können Sie immer einen Dateinamen an diese Methode übergeben, ohne dass Sie negative Auswirkungen auf Writer haben, die den Dateinamen nicht verwenden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a>Parameter  
 `emitter`  
 in Ein Zeiger auf die Metadatenemitter-Schnittstelle.  
  
 `filename`  
 in Der Name der Datei, in die die Debugsymbole geschrieben werden. Wenn für einen Writer, der keine Dateinamen verwendet, ein Dateiname angegeben ist, wird dieser Parameter ignoriert.  
  
 `pIStream`  
 in Wenn angegeben, gibt der Symbolwriter die Symbole in die angegebene <xref:System.Runtime.InteropServices.ComTypes.IStream> und nicht in die Datei aus, die im `filename`-Parameter angegeben wird. Der Parameter `pIStream` ist optional.  
  
 `fFullBuild`  
 [in] `true`, wenn dies eine vollständige Neuerstellung ist. `false` wenn dies eine inkrementelle Kompilierung ist.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [Initialize2-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
