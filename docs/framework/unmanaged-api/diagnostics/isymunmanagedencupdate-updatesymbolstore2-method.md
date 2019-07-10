---
title: ISymUnmanagedENCUpdate::UpdateSymbolStore2-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d2c641f011c55ee726e319cb581705e334c840d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774674"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a>ISymUnmanagedENCUpdate::UpdateSymbolStore2-Methode
Ermöglicht es einen Compiler, um Funktionen, die nicht aus dem Stream Programm Programmdatenbankdatei (PDB) geändert wurden zu unterdrücken, sofern die Zeileninformationen die Anforderungen erfüllt. Die richtige Zeileninformationen kann mit der alten Zeileninformationen für die PDB-Datei und einem Delta für alle Zeilen in der Funktion bestimmt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
## <a name="parameters"></a>Parameter  
 `pIStream`  
 [in] Ein Zeiger auf ein [IStream](/windows/desktop/api/objidl/nn-objidl-istream) , das die Zeileninformationen enthält.  
  
 `pDeltaLines`  
 [in] Ein Zeiger auf eine [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) Struktur, die die Zeilen enthält, die geändert wurden.  
  
 `cDeltaLines`  
 [in] Ein `ULONG` , die die Anzahl der Zeilen, die geändert wurden.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedENCUpdate-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
