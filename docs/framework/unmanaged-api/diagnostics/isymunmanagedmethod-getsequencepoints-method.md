---
title: ISymUnmanagedMethod::GetSequencePoints-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePoints
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePoints method [.NET Framework debugging]
- GetSequencePoints method [.NET Framework debugging]
ms.assetid: f909ac48-3d8f-49fb-a369-e3d9959151cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9a35f35d7aea34c0ef08c30415fde75fe71e645
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426049"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a>ISymUnmanagedMethod::GetSequencePoints-Methode
Ruft die Sequenzpunkte innerhalb dieser Methode ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetSequencePoints(  
    [in]  ULONG32  cPoints,  
    [out] ULONG32  *pcPoints,  
    [in, size_is(cPoints)] ULONG32  offsets[],  
    [in, size_is(cPoints)] ISymUnmanagedDocument* documents[],  
    [in, size_is(cPoints)] ULONG32  lines[],  
    [in, size_is(cPoints)] ULONG32  columns[],  
    [in, size_is(cPoints)] ULONG32  endLines[],  
    [in, size_is(cPoints)] ULONG32  endColumns[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cPoints`  
 [in] Ein `ULONG32` , empfängt die Größe der `offsets`, `documents`, `lines`, `columns`, `endLines`, und `endColumns` Arrays.  
  
 `pcPoints`  
 [out] Ein Zeiger auf eine `ULONG32` , empfängt die Länge des Puffers benötigt, um die Sequenzpunkte aufzunehmen.  
  
 `offsets`  
 [in] Ein Array zum Speichern der Microsoft intermediate Language (MSIL)-vom Anfang der Methode für die Sequenzpunkte Offsets.  
  
 `documents`  
 [in] Ein Array zum Speichern der Dokumente, in denen sich die Sequenzpunkte befinden.  
  
 `lines`  
 [in] Ein Array, in dem die Zeilen in den Dokumenten gespeichert, in denen sich die Sequenzpunkte befinden.  
  
 `columns`  
 [in] Ein Array zum Speichern der Spalten in den Dokumenten, in denen sich die Sequenzpunkte befinden.  
  
 `endLines`  
 [in] Das Array von Zeilen in den Dokumenten, in denen die Sequenzpunkte enden.  
  
 `endColumns`  
 [in] Das Array von Spalten in den Dokumenten, in denen die Sequenzpunkte enden.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
