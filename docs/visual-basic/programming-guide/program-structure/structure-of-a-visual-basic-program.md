---
title: Struktur von Visual Basic-Programmen
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], Visual Basic
- program structure [Visual Basic], Visual Basic
- procedures [Visual Basic], structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
ms.openlocfilehash: 4f4136a2c8fb7ca98ff22aa6a5fc676f30cd1c5d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624303"
---
# <a name="structure-of-a-visual-basic-program"></a>Struktur von Visual Basic-Programmen
Visual Basic-Programms wird von den Standardbausteinen entwickelt. Ein *Lösung* besteht aus einem oder mehreren Projekten. Ein *Projekt* wiederum können eine oder mehrere Assemblys enthalten. Jede *Assembly* aus ein oder mehrere Quelldateien kompiliert wird. Ein *Quelldatei* enthält die Definition und Implementierung von Klassen, Strukturen, Module und Schnittstellen, die letzten Endes den gesamten Code enthalten.  
  
 Weitere Informationen zu diesen Bausteinen von Visual Basic-Programmen, finden Sie unter [Projektmappen und Projekte](/visualstudio/ide/solutions-and-projects-in-visual-studio) und [Assemblys in .NET](../../../standard/assembly/index.md).  
  
## <a name="file-level-programming-elements"></a>Laufwerkssicherungen auf Dateiebene Programmierelemente  
 Wenn Sie, ein Projekt oder eine Datei beginnen und den Code-Editor zu öffnen, sehen Sie etwas Code bereits an Ort und in der richtigen Reihenfolge. Code, den Sie schreiben, sollten die folgende Sequenz beachten:  
  
1. `Option` Anweisungen  
  
2. `Imports` Anweisungen  
  
3. `Namespace` Anweisungen und Namespace-Level-Elementen  
  
 Wenn Sie die Anweisungen in einer anderen Reihenfolge eingeben, können Kompilierungsfehler führen.  
  
 Ein Programm kann auch Anweisungen für die bedingte Kompilierung enthalten. Sie können diese in der Quelldatei für die Anweisungen eines der oben dargestellten Reihenfolge hier und da.  
  
### <a name="option-statements"></a>Optionsanweisungen  
 `Option` Anweisungen richten Grundregeln für nachfolgende Code hilft zu verhindern, dass die Syntax und Logikfehler. Die [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md) wird sichergestellt, dass alle Variablen deklariert und richtig geschrieben debuggingzeit verringert wird. Die [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md) Logik Kopierfehlern und Datenverlust zu minimieren, die auftreten können, wenn Sie zwischen Variablen verschiedener Datentypen arbeiten können. Die [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md) gibt an, die Art des Zeichenfolgenvergleichs an, die auf Basis ihrer `Binary` oder `Text` Werte.  
  
### <a name="imports-statements"></a>Imports-Anweisungen  
 Sie können einschließen einer [Imports-Anweisung (.NET-Namespace und Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) zum Importieren von Namen, die außerhalb des Projekts definiert. Ein `Imports` -Anweisung können Sie Ihren Code zum Verweisen auf Klassen und anderen Typen, die in der importierten Namespaces definiert werden, ohne sie zu qualifizieren. Sie können beliebig viele `Imports` Anweisungen nach Bedarf. Weitere Informationen finden Sie unter [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).  
  
### <a name="namespace-statements"></a>Namespace-Anweisungen  
 Namespaces können, die Sie verwalten und klassifizieren Ihre Programmierelemente zur Vereinfachung der Gruppierung und den Zugriff auf. Sie verwenden die [Namespace-Anweisung](../../../visual-basic/language-reference/statements/namespace-statement.md) klassifizieren Sie die folgenden Anweisungen in einem bestimmten Namespace. Weitere Informationen finden Sie unter [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
### <a name="conditional-compilation-statements"></a>Anweisungen für die bedingte Kompilierung  
 Anweisungen für die bedingte Kompilierung können fast überall in der Quelldatei angezeigt. Sie führen die Teile des Codes eingeschlossen bzw. zum Zeitpunkt der Kompilierung basierend auf bestimmten Bedingungen ausgeschlossen werden sollen. Sie können auch sie verwenden zum Debuggen der Anwendung, da der bedingter Code ausgeführt wird, im Debugmodus befindet, nur. Weitere Informationen finden Sie unter [für die bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).  
  
## <a name="namespace-level-programming-elements"></a>Namespace-Ebene Programmierelemente  
 Klassen, Strukturen und -Module enthalten alle den Code in der Quelldatei. Sie sind *auf Namespace-Ebene* -Elemente, die in einem Namespace oder auf der Ebene der Quelldatei angezeigt werden können. Sie enthalten die Deklarationen der anderen Programmierungselementen. Schnittstellen, die Elementsignaturen zu definieren, aber keine Implementierung bereitstellen, werden auch auf Modulebene angezeigt. Weitere Informationen zu den Elementen auf Modulebene finden Sie in der folgenden:  
  
- [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
  
- [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
- [Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md)  
  
- [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 Datenelemente auf Namespaceebene sind Enumerationen und Delegaten.  
  
## <a name="module-level-programming-elements"></a>Auf Modulebene Programmierelemente  
 Prozeduren, Operatoren, Eigenschaften und Ereignisse sind die einzige Programmierelemente, die ausführbaren Code (Anweisungen, die Aktionen zur Laufzeit ausführen) enthalten können. Sie sind der *auf Modulebene* Elemente Ihres Programms. Weitere Informationen zu den Elementen auf Prozedurebene finden Sie hier:  
  
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
- [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
- [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
- [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 Datenelemente auf Modulebene sind Variablen, Konstanten, Enumerationen und Delegaten.  
  
## <a name="procedure-level-programming-elements"></a>Auf Prozedurebene Programmierelemente  
 Die meisten der Inhalte *auf Prozedurebene* Elemente sind ausführbare Anweisungen, die der Laufzeitcode des Programms zu bilden. Der gesamte ausführbarer Code muss in einer Prozedur (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`). Weitere Informationen finden Sie unter [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md).  
  
 Datenelemente auf Prozedurebene sind auf lokale Variablen und Konstanten beschränkt.  
  
## <a name="the-main-procedure"></a>Die Main-Prozedur  
 Die `Main` Verfahren ist der erste Code, der ausgeführt werden, wenn die Anwendung geladen wurde. `Main` Dient als Ausgangspunkt und gesamtsteuerung für Ihre Anwendung. Es gibt vier Arten von `Main`:  
  
- `Sub Main()`  
  
- `Sub Main(ByVal cmdArgs() As String)`  
  
- `Function Main() As Integer`  
  
- `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 Die am häufigsten verwendete Variante dieses Verfahrens ist `Sub Main()`. Weitere Informationen finden Sie unter [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).  
  
## <a name="see-also"></a>Siehe auch

- [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
- [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Beschränkungen in Visual Basic](../../../visual-basic/programming-guide/program-structure/limitations.md)
