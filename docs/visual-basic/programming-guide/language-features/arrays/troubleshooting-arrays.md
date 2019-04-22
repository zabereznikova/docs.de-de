---
title: Problembehandlung bei Arrays (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 2b051d22fe3d331626f2e181c008043e576b7526
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833372"
---
# <a name="troubleshooting-arrays-visual-basic"></a>Problembehandlung bei Arrays (Visual Basic)
Diese Seite listet einige der häufigsten Probleme, die bei der Arbeit mit Arrays auftreten können.  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a>Kompilierungsfehler deklarieren und Initialisieren eines Arrays  
 Kompilierungsfehler können von Missverständnissen Regeln zum Deklarieren, erstellen und Initialisieren von Arrays auftreten. Die häufigsten Ursachen von Fehlern sind die folgenden:  
  
-   Angeben einer [neuer Operator](../../../../visual-basic/language-reference/operators/new-operator.md) -Klausel nach der Angabe der Längen der Dimension in der Deklaration der Arrayvariablen. Die folgenden Codezeilen zeigen ungültige Deklarationen dieses Typs.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   Angeben von Längen der Dimension für mehr als Arrays der obersten Ebene eines verzweigten Arrays. Die folgende Codezeile zeigt eine ungültige Deklaration dieses Typs.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   Das Auslassen der `New` Schlüsselwort, wenn Sie die Elementwerte angeben. Die folgende Codezeile zeigt eine ungültige Deklaration dieses Typs.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   Angeben einer `New` -Klausel ohne geschweifte Klammern (`{}`). Die folgenden Codezeilen zeigen ungültige Deklarationen dieses Typs.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a>Zugreifen auf ein Array außerhalb des gültigen Bereichs  
 Bei der Initialisieren eines Arrays wird eine Obergrenze und einer unteren Grenze für jede Dimension zugewiesen. Jeder Zugriff auf ein Element des Arrays muss einen gültigen Index oder Feldindex, für eine Dimension angeben. Wenn ein Index unter der unteren Grenze oder über die Obergrenze ist ein <xref:System.IndexOutOfRangeException> Ausnahme führt. Der Compiler kann solche Fehler, nicht erkennen, damit zur Laufzeit ein Fehler auftritt.  
  
### <a name="determining-bounds"></a>Bestimmen von Grenzen  
 Wenn ein Array mit Ihrem Code eine andere Komponente übergeben wird, wissen z. B. als Prozedurargument, Sie nicht die Größe des Arrays oder der Länge seiner Dimensionen. Sie sollten immer die obere Grenze jeder Dimension eines Arrays bestimmen, bevor Sie versuchen, den Zugriff auf alle Elemente. Wenn das Array mit der eine Visual Basic erstellt wurde `New` -Klausel, die untere Grenze kann einen anderen Wert als 0 sein, und es ist am sichersten, sowie die Untergrenze bestimmen.  
  
### <a name="specifying-the-dimension"></a>Die Dimension angeben  
 Wenn Sie die Grenzen eines mehrdimensionalen Arrays zu bestimmen, achten Sie wie Sie die Dimension angeben. Die `dimension` Parameter von der <xref:System.Array.GetLowerBound%2A> und <xref:System.Array.GetUpperBound%2A> Methoden sind 0-basiert, während die `Rank` Parameter der Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> und <xref:Microsoft.VisualBasic.Information.UBound%2A> Funktionen sind 1-basiert.  
  
## <a name="see-also"></a>Siehe auch

- [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Vorgehensweise: Initialisieren einer Arrayvariablen in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
