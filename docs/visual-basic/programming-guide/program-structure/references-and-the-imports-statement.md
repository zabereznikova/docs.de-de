---
title: "References and the Imports Statement (Visual Basic) | Microsoft Docs"
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
  - "assemblies [Visual Basic], namespaces"
  - "references, assembly"
  - "namespaces, assemblies"
  - "referencing assemblies"
  - "Imports statement, referencing assemblies"
  - "assemblies [Visual Basic], references"
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# References and the Imports Statement (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Mit dem Befehl **Verweis hinzufügen** aus dem Menü **Projekt** lassen sich externe Objekte in das Projekt einbinden.  Verweise in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] können auf Assemblys zeigen, die mit Typbibliotheken vergleichbar sind, jedoch mehr Informationen enthalten.  
  
## Die Imports\-Anweisung  
 Assemblys umfassen einen oder mehrere Namespaces.  Wenn Sie einen Verweis auf eine Assembly anlegen, können Sie auch eine `Imports`\-Anweisung zu einem Modul hinzufügen, die die Sichtbarkeit der Namespaces innerhalb des Moduls steuert.  Die `Imports`\-Anweisung stellt einen Kontextbereich bereit, in dem Sie gezielt den Teil des Namespaces nutzen können, der zur Erstellung eines eindeutigen Verweises nötig ist.  
  
 Die `Imports`\-Anweisung hat die folgende Syntax:  
  
 `Imports` \[         `|` `Aliasname` \=\] `Namespace`  
  
 `Aliasname` steht für einen kurzen Namen, den Sie innerhalb des Codes verwenden können, um auf einen importierten Namespace zu verweisen.  `Namespace` ist ein Namespace, der entweder durch einen Projektverweis, durch eine Definition innerhalb des Projekts oder durch eine vorangehende `Imports`\-Anweisung verfügbar gemacht wird.  
  
 Ein Modul kann beliebig viele `Imports`\-Anweisungen enthalten.  Wenn vorhanden, müssen sie nach den `Option`\-Anweisungen, aber vor jeglichem anderen Code aufgeführt werden.  
  
> [!NOTE]
>  Verwechseln Sie Projektverweise nicht mit der `Imports`\-Anweisung oder der `Declare`\-Anweisung.  Mit Projektverweisen werden externe Objekte, z. B. Objekte in Assemblys, für [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Projekte verfügbar gemacht.  Die `Imports`\-Anweisung erleichtert zwar den Zugriff auf Projektverweise, stellt jedoch keinen Zugriff auf diese Objekte selbst bereit.  Mit der `Declare`\-Anweisung wird ein Verweis auf eine externe Prozedur in einer Dynamic Link Library \(DLL\) deklariert.  
  
## Verwenden von Aliasen mit der Imports\-Anweisung  
 Die `Imports`\-Anweisung erleichtert den Zugriff auf Methoden in Klassen, denn sie macht die explizite Eingabe des vollgekennzeichneten Namens eines Verweises überflüssig.  Mit Aliasen können Sie bestimmten Teilen des Namespaces einen eingängigeren Namen zuweisen.  So ist z. B. die Sequenz für Wagenrücklauf\/Zeilenvorschub, die die Anzeige eines einzelnen Textelements in mehreren Zeilen bewirkt, Teil der <xref:Microsoft.VisualBasic.ControlChars>\-Klasse im <xref:Microsoft.VisualBasic?displayProperty=fullName>\-Namespace.  Ohne Alias müssten Sie folgenden Code eingeben, um diese Konstante in einem Programm zu verwenden:  
  
 [!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 `Imports`\-Anweisungen müssen in einem Modul immer in den unmittelbar auf die `Option`\-Anweisungen folgenden Zeilen stehen.  Das folgende Codefragment zeigt, wie ein Alias für das <xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName>\-Modul importiert und zugewiesen wird:  
  
 [!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 Zukünftige Verweise auf diesen Namespace fallen dann wesentlich kürzer aus:  
  
 [!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 Wenn eine `Imports`\-Anweisung keinen Aliasnamen enthält, können im importierten Namespace definierte Elemente ohne Angabe des Namespacenamens im Modul verwendet werden.  Wenn ein Aliasname angegeben ist, müssen Namen innerhalb des betreffenden Namespaces mit ihm qualifiziert werden.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.ControlChars>   
 <xref:Microsoft.VisualBasic>   
 [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/de-de/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Assemblys und der globale Assemblycache](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Gewusst wie: Erstellen und Verwenden von Assemblys über die Befehlszeile](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md)   
 [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)