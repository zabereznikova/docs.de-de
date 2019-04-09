---
title: ISymENCUnmanagedMethod-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod
helpviewer_keywords:
- ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4474269688094ea6c81b06659727acfb9c2ad6c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59095710"
---
# <a name="isymencunmanagedmethod-interface"></a>ISymENCUnmanagedMethod-Schnittstelle
Enthält Informationen für die Funktion bearbeiten und fortfahren.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetDocumentsForMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|Ruft ab, die Dokumente, die diese Methode in Zeilen umfasst.|  
|[GetDocumentsForMethodCount-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|Ruft die Anzahl der Dokumente, die diese Methode in Zeilen umfasst.|  
|[GetFileNameFromOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|Ruft den Dateinamen für die Zeile, die ein Offset zugeordnet.|  
|[GetLineFromOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|Ruft die Zeileninformationen, die ein Offset zugeordnet.|  
|[GetSourceExtentInDocument-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|Ruft Starten des kleinsten und größten End Zeile für die Methode in einem bestimmten Dokument.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
