---
title: Programmstruktur und Codekonventionen (Visual Basic) | Microsoft-Dokumentation
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
- coding conventions
- Visual Basic code, coding conventions
- coding conventions, Visual Basic
- programs, structure
- program structure
- naming conventions, Visual Basic
- best practices, coding conventions
- conventions, Visual Basic coding
- Visual Basic code
- programming, Visual Basic coding conventions
ms.assetid: dd9be76f-6944-4e78-ad72-0b6084a3fc13
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cd25d99d74bf1e4d416c9da63758f6ad04027258
ms.lasthandoff: 03/13/2017

---
# <a name="program-structure-and-code-conventions-visual-basic"></a>Programmstruktur und Codekonventionen (Visual Basic)
In diesem Abschnitt werden die typische [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Programmstruktur eingeführt, das einfache [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Programm "Hello, World" vorgestellt und die Codekonventionen von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] erörtert. Codekonventionen sind Vorschläge, die sich nicht auf die Logik eines Programms, sondern auf seine physische Struktur und sein Erscheinungsbild konzentrieren. Wenn Sie diese Konventionen einhalten, ist Programmcode besser lesbar, leichter verständlich und einfacher zu verwalten. Codekonventionen umfassen u. a.:  
  
-   Standardisierte Formate für Bezeichnungen und Kommentare im Code.  
  
-   Richtlinien für die Verwendung von Leerzeichen, Formatierungen und Einzügen beim Code.  
  
-   Benennungskonventionen für Objekte, Variablen und Prozeduren.  
  
 Die folgenden Themen enthalten eine Reihe von Programmierungsrichtlinien für [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Programme und Beispiele für die richtige Verwendung.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Struktur eines Visual Basic-Programms](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 Bietet eine Übersicht über die Elemente, aus denen ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Programm besteht.  
  
 [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 Erörtert die Prozedur, die als Ausgangspunkt und Gesamtsteuerung für die Anwendung fungiert.  
  
 [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 Erläutert, wie auf Objekte in anderen Assemblys verwiesen wird.  
  
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 Beschreibt, wie Namespaces Objekte innerhalb von Assemblys organisieren.  
  
 [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 Umfasst allgemeine Richtlinien für die Benennung von Prozeduren, Konstanten, Variablen, Argumenten und Objekten.  
  
 [Visual Basic-Codierungskonventionen](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 Erläutert die Richtlinien, die beim Entwickeln der Beispiele in dieser Dokumentation verwendet werden.  
  
 [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 Beschreibt die selektive Kompilierung bestimmter Codeblöcke, indem der Compiler angewiesen wird, andere Blöcke zu ignorieren.  
  
 [Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 Zeigt, wie lange Anweisungen in mehrere Zeilen aufgeteilt und kurze Anweisungen zu einer Zeile zusammengefasst werden können.  
  
 [Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 Erläutert das Reduzieren und Ausblenden von Codeabschnitten im Code-Editor von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 [Gewusst wie: Bezeichnen von Anweisungen](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 Veranschaulicht, wie Codezeilen für die Verwendung mit Anweisungen, z. B. `On Error Goto`, gekennzeichnet werden.  
  
 [Sonderzeichen in Code](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 Zeigt, wie und an welcher Stelle nicht numerische und nicht alphabetische Zeichen verwendet werden.  
  
 [Kommentare in Code](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 Beschreibt, wie dem Code beschreibende Kommentare hinzugefügt werden können.  
  
 [Schlüsselwörter als Elementnamen in Code](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 Beschreibt, wie Variablennamen, die gleichzeitig `[]`-Schlüsselwörter sind, mithilfe von eckigen Klammern ([!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]) begrenzt werden.  
  
 [Me, My, MyBase und MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 Beschreibt verschiedene Möglichkeiten, auf Elemente eines [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Programms zu verweisen.  
  
 [Beschränkungen in Visual Basic](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 Erläutert die Entfernung bekannter Codierungsbeschränkungen in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Typografische und Codekonventionen](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 Enthält Standardcodierungskonventionen für [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 [Schreiben von Code](https://docs.microsoft.com/visualstudio/ide/writing-code-in-the-code-and-text-editor)  
 Beschreibt Funktionen, die Ihnen das Schreiben und Verwalten von Code erleichtern.
