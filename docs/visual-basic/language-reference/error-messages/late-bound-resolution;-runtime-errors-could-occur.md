---
title: Spät gebundene Auflösung. Laufzeitfehler sind möglich.
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: af027b7752fdf13f1540010a8ddb681182c1b23c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588778"
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a>Spät gebundene Auflösung. Laufzeitfehler sind möglich.
Eine Variable deklariert ein Objekt zugewiesen ist die [Object-Datentyp](../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 Wenn Sie eine Variable als deklarieren `Object`, muss der Compiler eine *späte Bindung*, die zur Laufzeit zusätzliche Vorgänge verursacht. Sie setzt die Anwendung zudem möglichen Laufzeitfehlern aus. Angenommen, Sie weisen einen <xref:System.Windows.Forms.Form> auf die `Object` Variable, und wiederholen Sie dann den Zugriff auf die <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> -Eigenschaft, löst die Laufzeit eine <xref:System.MemberAccessException> da der <xref:System.Windows.Forms.Form> Klasse macht keine `NameTable` Eigenschaft.  
  
 Wenn Sie die Variable eines bestimmten Typs deklarieren, kann der Compiler nicht ausführen *frühe Bindung* zum Zeitpunkt der Kompilierung. Dies führt zu einer verbesserten Leistung, kontrollierten Zugriff auf die Elemente des angegebenen Typs und einer besseren Lesbarkeit des Codes.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42017  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn möglich, deklarieren Sie die Variable eines bestimmten Typs sein.  
  
## <a name="see-also"></a>Siehe auch  
 [Frühes und spätes Binden](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 [Deklaration von Objektvariablen](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
