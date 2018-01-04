---
title: ISymENCUnmanagedMethod-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymENCUnmanagedMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymENCUnmanagedMethod
helpviewer_keywords: ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f7cc1cea74cc632c65c7e3c2aee408e2f9e864d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymencunmanagedmethod-interface"></a>ISymENCUnmanagedMethod-Schnittstelle
Enthält Informationen für die Funktion bearbeiten und fortfahren.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetDocumentsForMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|Ruft die Dokumente, die diese Methode in Zeilen umfasst.|  
|[GetDocumentsForMethodCount-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|Ruft die Anzahl der Dokumente, die diese Methode in Zeilen umfasst.|  
|[GetFileNameFromOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|Ruft den Dateinamen für die Zeile mit einem Versatz verknüpft sind.|  
|[GetLineFromOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|Ruft die Zeileninformationen ein Offset zugeordnet.|  
|[GetSourceExtentInDocument-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|Ruft Starten des kleinsten und größten End Linie für die Methode in einem bestimmten Dokument.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
