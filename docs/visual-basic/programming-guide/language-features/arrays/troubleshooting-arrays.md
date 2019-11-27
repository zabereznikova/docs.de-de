---
title: Problembehandlung bei Arrays
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 3c50c68c2a39aa04cff2dd43b5dfde709aec290f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349067"
---
# <a name="troubleshooting-arrays-visual-basic"></a>Problembehandlung bei Arrays (Visual Basic)
Auf dieser Seite werden einige allgemeine Probleme aufgelistet, die beim Arbeiten mit Arrays auftreten können.  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a>Kompilierungsfehler beim Deklarieren und Initialisieren eines Arrays  
 Kompilierungsfehler können aus einem Missverständnis der Regeln zum deklarieren, erstellen und Initialisieren von Arrays entstehen. Die häufigsten Fehlerursache sind folgende:  
  
- Bereitstellen einer [neuen Operator](../../../../visual-basic/language-reference/operators/new-operator.md) Klausel nach Angabe von Dimensions Längen in der Deklaration der Array Variablen. Die folgenden Codezeilen zeigen ungültige Deklarationen dieses Typs an.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
- Angeben von Dimensions Längen für mehr als das Array einer Jagged Array auf oberster Ebene. In der folgenden Codezeile wird eine ungültige Deklaration dieses Typs angezeigt.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
- Beim Angeben der Element Werte wird das `New` Schlüsselwort weggelassen. In der folgenden Codezeile wird eine ungültige Deklaration dieses Typs angezeigt.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
- Bereitstellen einer `New`-Klausel ohne geschweifte Klammern (`{}`). Die folgenden Codezeilen zeigen ungültige Deklarationen dieses Typs an.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a>Zugreifen auf ein Array außerhalb der Grenzen  
 Der Prozess der Initialisierung eines Arrays weist jeder Dimension eine obere Grenze und eine untere Grenze zu. Bei jedem Zugriff auf ein Element des Arrays muss ein gültiger Index oder ein Index für jede Dimension angegeben werden. Wenn ein Index unterhalb seiner unteren Grenze oder über der oberen Grenze liegt, ergibt sich eine <xref:System.IndexOutOfRangeException> Ausnahme. Der Compiler kann einen solchen Fehler nicht erkennen, weshalb zur Laufzeit ein Fehler auftritt.  
  
### <a name="determining-bounds"></a>Bestimmen von Begrenzungen  
 Wenn eine andere Komponente ein Array an Ihren Code übergibt, z. b. als Prozedur Argument, kennen Sie die Größe des Arrays oder die Längen seiner Dimensionen nicht. Sie sollten immer die obere Grenze für jede Dimension eines Arrays ermitteln, bevor Sie versuchen, auf Elemente zuzugreifen. Wenn das Array mit einer anderen Methode als einer Visual Basic `New`-Klausel erstellt wurde, ist die untere Grenze möglicherweise etwas anderes als 0 (null), und es ist am sichersten, dass auch die untere Grenze bestimmt wird.  
  
### <a name="specifying-the-dimension"></a>Angeben der Dimension  
 Wenn Sie die Begrenzungen eines mehrdimensionalen Arrays ermitteln, achten Sie darauf, wie Sie die Dimension angeben. Die `dimension` Parameter der Methoden <xref:System.Array.GetLowerBound%2A> und <xref:System.Array.GetUpperBound%2A> sind 0-basiert, während die `Rank` Parameter der Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A>-und <xref:Microsoft.VisualBasic.Information.UBound%2A>-Funktionen 1-basiert sind.  
  
## <a name="see-also"></a>Siehe auch

- [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md) (Gewusst wie: Initialisieren einer Arrayvariable in Visual Basic)
