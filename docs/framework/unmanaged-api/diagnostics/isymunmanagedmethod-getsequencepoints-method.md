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
ms.openlocfilehash: 75d477af7395a9b7d3328b2a5787f810733f3749
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448876"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a>ISymUnmanagedMethod::GetSequencePoints-Methode
Ruft alle Sequenz Punkte innerhalb dieser Methode ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
  
## <a name="parameters"></a>Parameter  
 `cPoints`  
 in Eine `ULONG32`, die die Größe der Arrays `offsets`, `documents`, `lines`, `columns`, `endLines`und `endColumns` empfängt.  
  
 `pcPoints`  
 vorgenommen Ein Zeiger auf einen `ULONG32`, der die Länge des Puffers empfängt, der zum enthalten der Sequenz Punkte benötigt wird.  
  
 `offsets`  
 in Ein Array, in dem die MSIL-Offsets (Microsoft Intermediate Language) vom Anfang der Methode für die Sequenz Punkte gespeichert werden sollen.  
  
 `documents`  
 in Ein Array, in dem die Dokumente gespeichert werden sollen, in denen sich die Sequenz Punkte befinden.  
  
 `lines`  
 in Ein Array, in dem die Zeilen in den Dokumenten gespeichert werden sollen, in denen sich die Sequenz Punkte befinden.  
  
 `columns`  
 in Ein Array, in dem die Spalten in den Dokumenten gespeichert werden sollen, in denen sich die Sequenz Punkte befinden.  
  
 `endLines`  
 in Das Array von Zeilen in den Dokumenten, in denen die Sequenz Punkte enden.  
  
 `endColumns`  
 in Das Array von Spalten in den Dokumenten, in denen die Sequenz Punkte enden.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
