---
title: ISymUnmanagedENCUpdate::UpdateSymbolStore2-Methode
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a366047530f3433ab1bfbb5f30d4b9b54c5bdb08
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a>ISymUnmanagedENCUpdate::UpdateSymbolStore2-Methode
Ermöglicht es einen Compiler, um Funktionen, die aus dem Programm Programmdatenbankdatei (PDB)-Stream nicht geändert wurden zu unterdrücken, sofern die Daten die Anforderungen erfüllt. Die richtige Zeileninformationen kann mit den alten PDB-Zeileninformationen und einem Delta für alle Zeilen in der Funktion bestimmt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pIStream`  
 [in] Ein Zeiger auf eine <xref:IStream> , die die Zeileninformationen enthält.  
  
 `pDeltaLines`  
 [in] Ein Zeiger auf eine [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) -Struktur, die die Zeilen enthält, die geändert wurden.  
  
 `cDeltaLines`  
 [in] Ein `ULONG` stellt die Anzahl von Zeilen, die geändert wurden.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedENCUpdate-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
