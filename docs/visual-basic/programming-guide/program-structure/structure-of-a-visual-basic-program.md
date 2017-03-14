---
title: "Structure of a Visual Basic Program | Microsoft Docs"
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
  - "conditional compilation, Visual Basic"
  - "program structure, Visual Basic"
  - "procedures, structure"
  - "Visual Basic code, program structure"
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Structure of a Visual Basic Program
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Ein [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Programm besteht aus Standardbausteinen.  Eine *Projektmappe* umfasst ein oder mehrere Projekte.  Ein *Projekt* wiederum kann eine oder mehrere Assemblys enthalten.  Jede *Assembly* wird aus einer oder mehreren Quelldateien kompiliert.  Eine *Quelldatei* stellt die Definition und Implementierung von Klassen, Strukturen, Modulen und Schnittstellen bereit, die schließlich den gesamten Code enthalten.  
  
 Weitere Informationen über diese Bausteine eines [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Programms finden Sie unter [Projektmappen und Projekte](/visual-studio/ide/solutions-and-projects-in-visual-studio) und [Assemblys und der globale Assemblycache](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Programmierelemente auf Dateiebene  
 Wenn Sie ein Projekt oder eine Datei starten und den Code\-Editor öffnen, wird bereits ein Teil des Codes an der richtigen Stelle und in der richtigen Reihenfolge angezeigt.  Beim Schreiben von Code sollten Sie prinzipiell die folgende Reihenfolge beachten:  
  
1.  `Option`\-Anweisungen  
  
2.  `Imports`\-Anweisungen  
  
3.  `Namespace`\-Anweisungen und Elemente auf Namespaceebene  
  
 Wenn Sie Anweisungen in einer anderen Reihenfolge angeben, können Kompilierungsfehler auftreten.  
  
 Ein Programm kann auch Anweisungen für die bedingte Kompilierung enthalten.  Sie können diese in der Quelldatei zwischen den Anweisungen einfügen, die in der oben dargestellten Reihenfolge angeordnet sind.  
  
### Option\-Anweisungen  
 `Option`\-Anweisungen geben die grundlegenden Regeln für nachfolgenden Code vor und helfen so, syntaktische und logische Fehler zu vermeiden.  Die [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) stellt sicher, dass alle Variablen ordnungsgemäß deklariert sind und die richtige Schreibweise aufweisen, sodass die Debugzeit verringert wird.  Die [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) trägt zur Verringerung von logischen Fehlern und Datenverlust bei, die beim Arbeiten mit Variablen unterschiedlichen Typs auftreten können.  Die [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) gibt die Art des Zeichenfolgenvergleichs an, die von ihrem `Binary`\-Wert bzw. `Text`\-Wert abhängt.  
  
### Imports\-Anweisungen  
 Sie können eine [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) einfügen, um außerhalb des Projekts definierte Namen zu importieren.  Mit einer `Imports`\-Anweisung kann Code auf Klassen und andere Typen verweisen, die in den importierten Namespaces definiert sind, ohne sie qualifizieren zu müssen.  Sie können so viele `Imports`\-Anweisungen wie erforderlich verwenden.  Weitere Informationen finden Sie unter [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).  
  
### Namespace\-Anweisungen  
 Mit Namespaces können Sie die Programmierelemente ordnen und klassifizieren, um die Gruppierung und den Zugriff zu erleichtern  Mit der [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md) klassifizieren Sie die folgenden Anweisungen in einem bestimmten Namespace.  Weitere Informationen finden Sie unter [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
### Anweisungen für die bedingte Kompilierung  
 Anweisungen für die bedingte Kompilierung können an nahezu jeder Position in der Quelldatei vorhanden sein.  Sie bewirken, dass Teile von Code zur Kompilierzeit unter bestimmten Bedingungen ein\- oder ausgeschlossen werden.  Sie können Anweisungen für die bedingte Kompilierung auch zum Debuggen einer Anwendung verwenden, da bedingter Code nur im Debugmodus ausgeführt wird.  Weitere Informationen finden Sie unter [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).  
  
## Programmierelemente auf Namespaceebene  
 Klassen, Strukturen und Module enthalten den gesamten Code der Quelldatei.  Sie sind Elemente auf *Namespaceebene*, die in einem Namespace oder auf der Ebene der Quelldatei angegeben werden können.  Sie enthalten die Deklarationen aller anderen Programmierelemente.  Schnittstellen, die Elementsignaturen definieren, doch keine Implementierung bereitstellen, werden ebenfalls auf Modulebene angegeben.  Weitere Informationen über die Elemente auf Modulebenene finden Sie in den folgenden Themen:  
  
-   [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 Datenelemente auf Namespaceebene sind Enumerationen und Delegaten.  
  
## Programmierelemente auf Modulebene  
 Prozeduren, Operatoren, Eigenschaften und Ereignisse sind die einzigen Programmierelemente, die ausführbaren Code \(Anweisungen, die zur Laufzeit Aktionen ausführen\) enthalten können.  Sie sind die Elemente des Programms auf *Modulebene*.  Weitere Informationen über die Elemente auf Prozedurebenene finden Sie in den folgenden Themen:  
  
-   [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 Datenelemente auf Modulebene sind Variablen, Konstanten, Enumerationen und Delegaten.  
  
## Programmierelemente auf Prozedurebene  
 Beim Großteil des Inhalts von Elementen auf *Prozedurebene* handelt es sich um ausführbare Anweisungen, aus denen der Laufzeitcode des Programms besteht.  Ausführbarer Code muss immer in einer Prozedur \(`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`\) enthalten sein.  Weitere Informationen finden Sie unter [Statements](../../../visual-basic/programming-guide/language-features/statements.md).  
  
 Datenelemente auf Prozedurebene sind auf lokale Variablen und Konstanten beschränkt.  
  
## Main\-Prozedur  
 Die `Main`\-Prozedur ist der erste Code, der nach dem Laden der Anwendung ausgeführt werden muss.  `Main` fungiert als Ausgangspunkt und Gesamtsteuerung für die Anwendung.  Es gibt vier Varianten von `Main`:  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 Die häufigste Variante dieser Prozedur ist `Sub Main()`.  Weitere Informationen finden Sie unter [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).  
  
## Siehe auch  
 [NIB: Visual Basic Version of Hello, World](http://msdn.microsoft.com/de-de/9d030b60-e148-4366-a462-69532f02294c)   
 [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)   
 [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [Visual Basic Limitations](../../../visual-basic/programming-guide/program-structure/limitations.md)