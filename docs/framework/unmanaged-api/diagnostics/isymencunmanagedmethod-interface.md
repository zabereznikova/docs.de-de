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
ms.openlocfilehash: acb8d48ed6314756e2c1a10fff314a303799fb24
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707281"
---
# <a name="isymencunmanagedmethod-interface"></a>ISymENCUnmanagedMethod-Schnittstelle

Enthält Informationen für das Feature "Bearbeiten und Fortfahren".  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetDocumentsForMethod-Methode](isymencunmanagedmethod-getdocumentsformethod-method.md)|Ruft die Dokumente ab, in denen diese Methode Zeilen aufweist.|  
|[GetDocumentsForMethodCount-Methode](isymencunmanagedmethod-getdocumentsformethodcount-method.md)|Ruft die Anzahl der Dokumente ab, in denen diese Methode Zeilen aufweist.|  
|[GetFileNameFromOffset-Methode](isymencunmanagedmethod-getfilenamefromoffset-method.md)|Ruft den Dateinamen für die Zeile ab, die einem Offset zugeordnet ist.|  
|[GetLineFromOffset-Methode](isymencunmanagedmethod-getlinefromoffset-method.md)|Ruft die einem Offset zugeordneten Zeilen Informationen ab.|  
|[GetSourceExtentInDocument-Methode](isymencunmanagedmethod-getsourceextentindocument-method.md)|Ruft die kleinste anfangs Linie und die größte Endzeile für die Methode in einem bestimmten Dokument ab.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
