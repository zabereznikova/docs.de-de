---
title: "Troubleshooting Arrays (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "troubleshooting arrays"
  - "arrays [Visual Basic], initialization errors"
  - "troubleshooting Visual Basic, arrays"
  - "arrays [Visual Basic], compilation errors"
  - "arrays [Visual Basic], declaration errors"
  - "arrays [Visual Basic], troubleshooting"
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Troubleshooting Arrays (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Auf dieser Seite werden einige allgemeine Probleme aufgeführt, die beim Arbeiten mit Array auftreten können.  
  
## Kompilierungsfehler beim Deklarieren und Initialisieren eines Arrays  
 Kompilierungsfehler können aufgrund eines unzureichenden Verständnisses der Regeln zum Deklarieren, Erstellen und Initialisieren von Arrays auftreten.  Die häufigsten Ursachen von Fehlern sind folgende:  
  
-   Angeben einer [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md)\-Klausel nach der Angabe der Dimensionslängen in der Arrayvariablendeklaration.  In den folgenden Codezeilen werden ungültige Deklarationen dieses Typs dargestellt.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   Angeben von Dimensionslängen für mehrere Arrays der obersten Ebene eines verzweigten Arrays.  In der folgenden Codezeile wird eine ungültige Deklaration dieses Typs dargestellt.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   Auslassen des `New`\-Schlüsselworts beim Angeben der Elementwerte.  In der folgenden Codezeile wird eine ungültige Deklaration dieses Typs dargestellt.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   Angeben einer `New`\-Klausel ohne geschweifte Klammern \(`{}`\).  In den folgenden Codezeilen werden ungültige Deklarationen dieses Typs dargestellt.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## Zugreifen auf ein Array außerhalb der zulässigen Grenzen  
 Beim Initialisieren eines Arrays wird jeder Dimension eine Obergrenze und eine Untergrenze zugewiesen.  Bei jedem Zugriff auf ein Element des Arrays muss für jede Dimension ein gültiger Index, auch als Feldindex bezeichnet, angegeben werden.  Wenn ein Index niedriger als die Untergrenze oder höher als die Obergrenze ist, wird eine <xref:System.IndexOutOfRangeException>\-Ausnahme ausgelöst.  Der Compiler kann einen solchen Fehler nicht erkennen, daher tritt zur Laufzeit ein Fehler auf.  
  
### Bestimmen von Grenzen  
 Wenn eine andere Komponente ein Array, z. B. als ein Prozedurargument, an Code übergibt, kennen Sie weder die Größe dieses Arrays noch die Länge seiner Dimensionen.  Bestimmen Sie immer für jede Dimension eines Arrays die Obergrenze, bevor Sie auf Elemente zuzugreifen versuchen.  Wenn das Array nicht mit der `New`\-Klausel von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] erstellt wurde, weist die Untergrenze möglicherweise einen anderen Wert als 0 \(null\) auf, und zur Sicherheit empfiehlt es sich, die Untergrenze ebenfalls zu bestimmen.  
  
### Angeben der Dimension  
 Wenn Sie die Grenzen eines mehrdimensionalen Arrays bestimmen, achten Sie darauf, wie Sie die Dimension angeben.  Die `dimension`\-Parameter der <xref:System.Array.GetLowerBound%2A>\-Methode und der <xref:System.Array.GetUpperBound%2A>\-Methode sind nullbasiert, während die `Rank`\-Parameter der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Information.LBound%2A>\-Funktion und der <xref:Microsoft.VisualBasic.Information.UBound%2A>\-Funktion 1\-basiert sind.  
  
## Siehe auch  
 [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)