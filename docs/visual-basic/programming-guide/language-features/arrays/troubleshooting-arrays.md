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
ms.openlocfilehash: e633c5a00693f188270b1610abaf2decb656b00a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414594"
---
# <a name="troubleshooting-arrays-visual-basic"></a>Problembehandlung bei Arrays (Visual Basic)
Auf dieser Seite werden einige allgemeine Probleme aufgelistet, die beim Arbeiten mit Arrays auftreten können.  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a>Kompilierungsfehler beim Deklarieren und Initialisieren eines Arrays  
 Kompilierungsfehler können aus einem Missverständnis der Regeln zum deklarieren, erstellen und Initialisieren von Arrays entstehen. Die häufigsten Fehlerursache sind folgende:  
  
- Bereitstellen einer [neuen Operator](../../../language-reference/operators/new-operator.md) Klausel nach Angabe von Dimensions Längen in der Deklaration der Array Variablen. Die folgenden Codezeilen zeigen ungültige Deklarationen dieses Typs an.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
- Angeben von Dimensions Längen für mehr als das Array einer Jagged Array auf oberster Ebene. In der folgenden Codezeile wird eine ungültige Deklaration dieses Typs angezeigt.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
- Das Schlüsselwort wird weggelassen, `New` Wenn die Element Werte angegeben werden. In der folgenden Codezeile wird eine ungültige Deklaration dieses Typs angezeigt.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
- Bereitstellen einer `New` Klausel ohne geschweifte Klammern ( `{}` ). Die folgenden Codezeilen zeigen ungültige Deklarationen dieses Typs an.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a>Zugreifen auf ein Array außerhalb der Grenzen  
 Der Prozess der Initialisierung eines Arrays weist jeder Dimension eine obere Grenze und eine untere Grenze zu. Bei jedem Zugriff auf ein Element des Arrays muss ein gültiger Index oder ein Index für jede Dimension angegeben werden. Wenn ein Index unterhalb seiner unteren Grenze oder oberhalb der oberen Grenze liegt, wird eine <xref:System.IndexOutOfRangeException> Ausnahme ausgelöst. Der Compiler kann einen solchen Fehler nicht erkennen, weshalb zur Laufzeit ein Fehler auftritt.  
  
### <a name="determining-bounds"></a>Bestimmen von Begrenzungen  
 Wenn eine andere Komponente ein Array an Ihren Code übergibt, z. b. als Prozedur Argument, kennen Sie die Größe des Arrays oder die Längen seiner Dimensionen nicht. Sie sollten immer die obere Grenze für jede Dimension eines Arrays ermitteln, bevor Sie versuchen, auf Elemente zuzugreifen. Wenn das Array mit einer anderen Methode als einer Visual Basic-Klausel erstellt wurde `New` , ist die untere Grenze möglicherweise etwas anderes als 0, und es ist am sichersten, dass auch die untere Grenze bestimmt wird.  
  
### <a name="specifying-the-dimension"></a>Angeben der Dimension  
 Wenn Sie die Begrenzungen eines mehrdimensionalen Arrays ermitteln, achten Sie darauf, wie Sie die Dimension angeben. Die `dimension` Parameter der <xref:System.Array.GetLowerBound%2A> <xref:System.Array.GetUpperBound%2A> -Methode und der-Methode sind 0-basiert, während die `Rank` Parameter der Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> <xref:Microsoft.VisualBasic.Information.UBound%2A> -und-Funktionen 1-basiert sind.  
  
## <a name="see-also"></a>Weitere Informationen

- [Arrays](index.md)
- [How to: Initialize an Array Variable in Visual Basic](how-to-initialize-an-array-variable.md) (Gewusst wie: Initialisieren einer Arrayvariable in Visual Basic)
