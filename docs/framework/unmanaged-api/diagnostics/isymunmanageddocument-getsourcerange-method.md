---
title: ISymUnmanagedDocument::GetSourceRange-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type:
- apiref
ms.openlocfilehash: f5d7df60a7b9c728b73fe6592226a8b6734b1e66
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692149"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a>ISymUnmanagedDocument::GetSourceRange-Methode

Gibt den angegebenen Bereich der eingebetteten Quelle in den angegebenen Puffer zurück. Der Puffer muss groß genug sein, um die Quelle zu speichern.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
## <a name="parameters"></a>Parameter  

 `startLine`  
 in Die Anfangs Zeile im aktuellen Dokument.  
  
 `startColumn`  
 in Die Anfangs Spalte im aktuellen Dokument.  
  
 `endLine`  
 in Die letzte Zeile im aktuellen Dokument.  
  
 `endColumn`  
 in Die letzte Spalte im aktuellen Dokument.  
  
 `cSourceBytes`  
 in Die Größe der Quelle in Bytes.  
  
 `pcSourceBytes`  
 vorgenommen Ein Zeiger auf eine Variable, die die Quellgröße empfängt.  
  
 `source`  
 vorgenommen Die Größe und die Länge des angegebenen Bereichs des Quelldokuments in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedDocument-Schnittstelle](isymunmanageddocument-interface.md)
