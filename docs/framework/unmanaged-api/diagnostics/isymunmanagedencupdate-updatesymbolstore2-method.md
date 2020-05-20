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
ms.openlocfilehash: f363bed8e7002bf898755b434c919f8722dea3fb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614499"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a>ISymUnmanagedENCUpdate::UpdateSymbolStore2-Methode
Ermöglicht einem Compiler das Weglassen von Funktionen, die nicht aus dem Datenstrom der Programmdatenbank (PDB) geändert wurden, vorausgesetzt, die Zeilen Informationen erfüllen die Anforderungen. Die richtigen Zeilen Informationen können mit den alten PDB-Zeilen Informationen und einem Delta für alle Zeilen in der Funktion bestimmt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
## <a name="parameters"></a>Parameter  
 `pIStream`  
 in Ein Zeiger auf einen [IStream](/windows/desktop/api/objidl/nn-objidl-istream) , der die Zeilen Informationen enthält.  
  
 `pDeltaLines`  
 in Ein Zeiger auf eine [SYMLINEDELTA](symlinedelta-structure.md) -Struktur, die die geänderten Zeilen enthält.  
  
 `cDeltaLines`  
 in Eine `ULONG` , die die Anzahl der geänderten Zeilen darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedENCUpdate-Schnittstelle](isymunmanagedencupdate-interface.md)
