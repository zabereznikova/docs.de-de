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
ms.openlocfilehash: 54c8c7f5c3ba6b4afd4ff352a8afb947a92e2d61
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441876"
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
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
