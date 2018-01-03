---
title: ISymUnmanagedDocument::GetSourceRange-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetSourceRange
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dcddebbca74bb94bd2411038a02b900b2f64f2d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
  
#### <a name="parameters"></a>Parameter  
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
 [out] Ein Zeiger auf eine Variable, die Größe der Quelle empfängt.  
  
 `source`  
 [out] Die Größe und die Länge des angegebenen Bereichs des Quelldokuments, in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist.  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedDocument-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
