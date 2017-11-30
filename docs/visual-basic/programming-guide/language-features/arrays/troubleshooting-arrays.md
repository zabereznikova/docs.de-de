---
title: Problembehandlung bei Arrays (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0417ae8d37642a65b14cc81ae9dcf3a3c32d63ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-arrays-visual-basic"></a>Problembehandlung bei Arrays (Visual Basic)
Auf dieser Seite sind einige allgemeine Probleme, die beim Arbeiten mit Arrays auftreten können.  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a>Kompilierungsfehler deklarieren und Initialisieren eines Arrays  
 In puncto der Regeln zum Deklarieren, erstellen und Initialisieren von Arrays können Kompilierungsfehler auftreten. Die häufigsten Ursachen von Fehlern sind die folgenden:  
  
-   Angeben einer [New-Operator](../../../../visual-basic/language-reference/operators/new-operator.md) -Klausel nach Längen der Dimension in der Arrayvariablendeklaration angeben. Die folgenden Codezeilen zeigen ungültige Deklarationen dieses Typs.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   Angeben von Längen der Dimension mehr als Arrays der obersten Ebene eines verzweigten Arrays. Die folgende Codezeile wird eine ungültige Deklaration dieses Typs.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   Das Weglassen der `New` -Schlüsselwort, wenn die Elementwerte festlegen. Die folgende Codezeile wird eine ungültige Deklaration dieses Typs.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   Angeben einer `New` -Klausel ohne geschweifte Klammern (`{}`). Die folgenden Codezeilen zeigen ungültige Deklarationen dieses Typs.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a>Zugreifen auf ein Array außerhalb des gültigen Bereichs  
 Der Prozess Initialisieren eines Arrays weist eine Obergrenze und eine Untergrenze für jede Dimension. Jeder Zugriff auf ein Element des Arrays muss einen gültigen Index oder Feldindex, für jede Dimension angeben. Wenn ein Index niedriger als die Untergrenze oder über seine Obergrenze ist ein <xref:System.IndexOutOfRangeException> Ausnahmeergebnisse. Der Compiler kann solche Fehler nicht erkennen, damit zur Laufzeit ein Fehler auftritt.  
  
### <a name="determining-bounds"></a>Bestimmen von Grenzen  
 Wenn ein Array für Ihren Code eine andere Komponente übergeben wird, wissen z. B. wie eines Prozedurarguments Sie nicht die Größe des Arrays oder Größen seiner Dimensionen. Sie sollten immer die obere Grenze für eine Dimension eines Arrays bestimmen, bevor Sie versuchen, Zugriff auf alle Elemente. Wenn das Array außer Weise erstellt wurde eine [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] `New` -Klausel, die untere Grenze kann einen anderen Wert als 0 sein, und es ist am sichersten, sowie die Untergrenze bestimmen.  
  
### <a name="specifying-the-dimension"></a>Angeben der Dimension  
 Wenn die Grenzen eines mehrdimensionalen Arrays bestimmt wird, achten Sie darauf wie Sie die Dimension angeben. Die `dimension` Parameter der <xref:System.Array.GetLowerBound%2A> und <xref:System.Array.GetUpperBound%2A> Methoden sind 0-basiert, während die `Rank` Parameter der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Information.LBound%2A> und <xref:Microsoft.VisualBasic.Information.UBound%2A> Funktionen basieren auf 1.  
  
## <a name="see-also"></a>Siehe auch  
 [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md) (Gewusst wie: Initialisieren einer Arrayvariable in Visual Basic)
