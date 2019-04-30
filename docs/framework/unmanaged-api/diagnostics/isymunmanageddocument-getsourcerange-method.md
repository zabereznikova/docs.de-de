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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 59420cfd29c3228aece9fc5ae02b950db6099ea0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939855"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a>ISymUnmanagedDocument::GetSourceRange-Methode
Gibt den angegebenen Bereich der eingebetteten Quelle in den angegebenen Puffer zurück. Der Puffer muss groß genug für die Quelle sein.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 [in] Die Anfangszeile im aktuellen Dokument.  
  
 `startColumn`  
 [in] Die Anfangsspalte im aktuellen Dokument.  
  
 `endLine`  
 [in] Die letzte Zeile im aktuellen Dokument.  
  
 `endColumn`  
 [in] Die letzte Spalte im aktuellen Dokument.  
  
 `cSourceBytes`  
 [in] Die Größe der Quelle, in Bytes.  
  
 `pcSourceBytes`  
 [out] Ein Zeiger auf eine Variable, die Größe der Datenquelle empfängt.  
  
 `source`  
 [out] Die Größe und die Länge des angegebenen Bereichs des Quelldokuments, in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist.  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedDocument-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
