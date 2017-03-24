---
title: Problembehandlung bei Arrays (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: db38c0c2a4f8b74a6b862f86f426b4d8837f4424
ms.lasthandoff: 03/13/2017

---
# <a name="troubleshooting-arrays-visual-basic"></a>Problembehandlung bei Arrays (Visual Basic)
Diese Seite listet einige der häufigsten Probleme, die beim Arbeiten mit Arrays auftreten können.  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a>Kompilierungsfehler beim Deklarieren und Initialisieren eines Arrays  
 Kompilierungsfehler können aufgrund eines unzureichenden Verständnisses der Regeln zum Deklarieren, erstellen und Initialisieren von Arrays auftreten. Die häufigsten Ursachen von Fehlern sind folgende:  
  
-   Bereitstellen einer [Operator New](../../../../visual-basic/language-reference/operators/new-operator.md) -Klausel nach der Angabe der Längen der Dimension in der Deklaration der Arrayvariablen. Die folgenden Codezeilen werden ungültige Deklarationen dieses Typs.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   Längen der Dimension für mehr als Arrays der obersten Ebene eines verzweigten Arrays angeben. Die folgende Codezeile zeigt eine ungültige Deklaration dieses Typs.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   Das Weglassen der `New` Schlüsselwort beim Angeben der Elementwerte. Die folgende Codezeile zeigt eine ungültige Deklaration dieses Typs.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   Bereitstellen einer `New` -Klausel ohne geschweifte Klammern (`{}`). Die folgenden Codezeilen werden ungültige Deklarationen dieses Typs.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a>Zugreifen auf ein Array außerhalb des gültigen Bereichs  
 Der Prozess der Initialisierung ein Array weist eine Obergrenze und eine Untergrenze für jede Dimension. Bei jedem Zugriff auf ein Element des Arrays muss ein gültiger Index oder Feldindex, für eine Dimension angeben. Wenn ein Index niedriger als die Untergrenze oder höher als die Obergrenze ist ein <xref:System.IndexOutOfRangeException>Ausnahmeergebnisse.</xref:System.IndexOutOfRangeException> Der Compiler kann einen derartigen Fehler nicht erkennen, sodass zur Laufzeit ein Fehler auftritt.  
  
### <a name="determining-bounds"></a>Bestimmen von Grenzen  
 Wenn eine andere Komponente ein Array an den Code übergeben, wissen z. B. als Prozedurarguments, Sie nicht die Größe des Arrays oder die Länge der Dimensionen. Sie sollten immer die Obergrenze für jede Dimension eines Arrays bestimmen, bevor Sie versuchen, Zugriff auf alle Elemente. Wenn das Array als Weise erstellt wurde eine [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `New` -Klausel, die Untergrenze möglicherweise etwas anderes als 0, und es ist am sichersten, die Untergrenze ebenfalls zu bestimmen.  
  
### <a name="specifying-the-dimension"></a>Angeben der Dimension  
 Wenn Sie die Grenzen eines mehrdimensionalen Arrays bestimmen, achten Sie wie Sie die Dimension angeben. Die `dimension` Parameter der <xref:System.Array.GetLowerBound%2A>und <xref:System.Array.GetUpperBound%2A>Methoden sind 0-basiert, während die `Rank` Parameter von der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Information.LBound%2A>und <xref:Microsoft.VisualBasic.Information.UBound%2A>Funktionen sind 1-basiert.</xref:Microsoft.VisualBasic.Information.UBound%2A> </xref:Microsoft.VisualBasic.Information.LBound%2A> </xref:System.Array.GetUpperBound%2A> </xref:System.Array.GetLowerBound%2A>  
  
## <a name="see-also"></a>Siehe auch  
 [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Gewusst wie: Initialisieren einer Arrayvariablen in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
