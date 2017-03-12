---
title: "Programmstruktur und Codekonventionen (Visual Basic) | Microsoft Docs"
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
  - "Codekonventionen"
  - "Visual Basic-Code, Codekonventionen"
  - "Codekonventionen, Visual Basic"
  - "Programme, Struktur"
  - "Programmstruktur"
  - "Benennungskonventionen, Visual Basic"
  - "Bewährte Methoden, Codekonventionen"
  - "Konventionen, Visual Basic-Code"
  - "Visual Basic-Code"
  - "Programmierung, Visual Basic-Codierungskonventionen"
ms.assetid: dd9be76f-6944-4e78-ad72-0b6084a3fc13
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Programmstruktur und Codekonventionen (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

In diesem Abschnitt werden die typische [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Programmstruktur eingeführt, das einfache [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Programm "Hello, World" vorgestellt und die Codekonventionen von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] erörtert.  Codekonventionen sind Vorschläge, die sich nicht auf die Logik eines Programms, sondern auf seine physische Struktur und sein Erscheinungsbild konzentrieren.  Wenn Sie diese Konventionen einhalten, ist Programmcode besser lesbar, leichter verständlich und einfacher zu verwalten.  Codekonventionen umfassen u. a.:  
  
-   Standardisierte Formate für Bezeichnungen und Kommentare im Code.  
  
-   Richtlinien für die Verwendung von Leerzeichen, Formatierungen und Einzügen beim Code.  
  
-   Benennungskonventionen für Objekte, Variablen und Prozeduren.  
  
 Die folgenden Themen enthalten eine Reihe von Programmierungsrichtlinien für [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Programme und Beispiele für die richtige Verwendung.  
  
## In diesem Abschnitt  
 [Structure of a Visual Basic Program](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 Bietet eine Übersicht über die Elemente, aus denen ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Programm besteht.  
  
 [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 Erörtert die Prozedur, die als Ausgangspunkt und Gesamtsteuerung für die Anwendung fungiert.  
  
 [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 Erläutert, wie auf Objekte in anderen Assemblys verwiesen wird.  
  
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 Beschreibt, wie Namespaces Objekte innerhalb von Assemblys organisieren.  
  
 [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 Umfasst allgemeine Richtlinien für die Benennung von Prozeduren, Konstanten, Variablen, Argumenten und Objekten.  
  
 [Visual Basic Coding Conventions](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 Erläutert die Richtlinien, die beim Entwickeln der Beispiele in dieser Dokumentation verwendet werden.  
  
 [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 Beschreibt die selektive Kompilierung bestimmter Codeblöcke, indem der Compiler angewiesen wird, andere Blöcke zu ignorieren.  
  
 [Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 Zeigt, wie lange Anweisungen in mehrere Zeilen aufgeteilt und kurze Anweisungen zu einer Zeile zusammengefasst werden können.  
  
 [How to: Collapse and Hide Sections of Code](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 Erläutert das Reduzieren und Ausblenden von Codeabschnitten im Code\-Editor von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 Veranschaulicht, wie Codezeilen für die Verwendung mit Anweisungen, z. B. `On Error Goto`, gekennzeichnet werden.  
  
 [Special Characters in Code](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 Zeigt, wie und an welcher Stelle nicht numerische und nicht alphabetische Zeichen verwendet werden.  
  
 [Comments in Code](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 Beschreibt, wie dem Code beschreibende Kommentare hinzugefügt werden können.  
  
 [Keywords as Element Names in Code](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 Beschreibt, wie Variablennamen, die gleichzeitig [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Schlüsselwörter sind, mithilfe von eckigen Klammern \(`[]`\) begrenzt werden.  
  
 [Me, My, MyBase, and MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 Beschreibt verschiedene Möglichkeiten, auf Elemente eines [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Programms zu verweisen.  
  
 [Visual Basic Limitations](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 Erläutert die Entfernung bekannter Codierungsbeschränkungen in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
## Verwandte Abschnitte  
 [Typographic and Code Conventions](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 Enthält Standardcodierungskonventionen für [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 [Schreiben von Code](/visual-studio/ide/writing-code-in-the-code-and-text-editor)  
 Beschreibt Funktionen, die Ihnen das Schreiben und Verwalten von Code erleichtern.