---
title: Struktur von Visual Basic-Programmen
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], Visual Basic
- program structure [Visual Basic], Visual Basic
- procedures [Visual Basic], structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
ms.openlocfilehash: 5c45cc8982a03d5bdd974434164187b03529ae05
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654829"
---
# <a name="structure-of-a-visual-basic-program"></a>Struktur von Visual Basic-Programmen
Visual Basic-Programm ist aus Standardbausteinen erstellt. Ein *Lösung* umfasst eine oder mehrere Projekte. Ein *Projekt* wiederum können eine oder mehrere Assemblys enthalten. Jede *Assembly* , die über eine oder mehrere Quelldateien kompiliert wird. Ein *Quelldatei* enthält die Definition und Implementierung von Klassen, Strukturen, Module und Schnittstellen, die letztendlich den gesamten Code enthalten.  
  
 Weitere Informationen über diese Bausteine eines Visual Basic-Programms finden Sie unter [Projektmappen und Projekten](/visualstudio/ide/solutions-and-projects-in-visual-studio) und [Assemblys und dem globalen Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).  
  
## <a name="file-level-programming-elements"></a>Programmierelemente auf Dateiebene  
 Wenn Sie ein Projekt oder eine Datei starten und im Code-Editor zu öffnen, sehen Sie einige Code bereits an Ort und in der richtigen Reihenfolge. Jeglicher Code, den Sie schreiben, sollte die folgende Sequenz folgen:  
  
1.  `Option` Anweisungen  
  
2.  `Imports` Anweisungen  
  
3.  `Namespace` Anweisungen und Namespace-Level-Elementen  
  
 Wenn Sie die Anweisungen in einer anderen Reihenfolge eingeben, können Kompilierungsfehler führen.  
  
 Ein Programm kann auch Anweisungen für die bedingte Kompilierung enthalten. Sie können diese in der Quelldatei zwischen der Anweisungen von der oben dargestellten Reihenfolge einzufügen.  
  
### <a name="option-statements"></a>Optionsanweisungen  
 `Option` Anweisungen richten Grundregeln bei nachfolgenden Code hilft zu verhindern, dass die Syntax und logische Fehler. Die [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md) wird sichergestellt, dass alle Variablen deklariert und richtig geschrieben Debuggen Zeit verringert wird. Die [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md) hilft Ihnen bei der logischen Fehlern und Datenverlust zu minimieren, die auftreten können, wenn Sie zwischen Variablen mit unterschiedlichen Datentypen arbeiten. Die [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md) gibt an, wie Zeichenfolgen verglichen werden, miteinander, basierend auf deren `Binary` oder `Text` Werte.  
  
### <a name="imports-statements"></a>Imports-Anweisungen  
 Sie können einschließen, eine [Imports-Anweisung (.NET Namespace und Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) zum Importieren von Namen, die außerhalb des Projekts definiert. Ein `Imports` -Anweisung können Sie den Code zum Verweisen auf Klassen und anderen Typen in den importierten Namespaces definiert wird, ohne sie zu qualifizieren. Sie können beliebig viele `Imports` Anweisungen nach Bedarf. Weitere Informationen finden Sie unter [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).  
  
### <a name="namespace-statements"></a>Namespace-Anweisungen  
 Namespaces können, die Sie verwalten und Klassifizieren von Programmierelementen zur Vereinfachung der Gruppierung von und Zugreifen auf. Verwenden Sie die [Namespace-Anweisung](../../../visual-basic/language-reference/statements/namespace-statement.md) die folgenden Anweisungen in einem bestimmten Namespace zu klassifizieren. Weitere Informationen finden Sie unter [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
### <a name="conditional-compilation-statements"></a>Anweisungen für die bedingte Kompilierung  
 Anweisungen für die bedingte Kompilierung können nahezu überall in der Quelldatei angezeigt. Sie bewirken, dass Teile des Codes eingeschlossen bzw. zum Zeitpunkt der Kompilierung je nachdem, wie bestimmte ausgeschlossen werden sollen. Sie können auch sie verwenden zum Debuggen der Anwendung, da bedingter Code im Debugmodus befindet, nur ausgeführt wird. Weitere Informationen finden Sie unter [bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).  
  
## <a name="namespace-level-programming-elements"></a>Namespace-Ebene Programmierelemente  
 Klassen, Strukturen und Module enthalten den Code für die in der Quelldatei. Sie sind *Namespaceebene* -Elemente, die in einem Namespace oder auf der Ebene der Quelldatei angezeigt werden können. Sie enthalten die Deklarationen der anderen Programmierungselementen. Schnittstellen, die Elementsignaturen definieren, aber keine Implementierung bereitstellen, werden auch auf Modulebene angezeigt. Weitere Informationen zu den Elementen auf Modulebene finden Sie hier:  
  
-   [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 Datenelemente auf Namespaceebene sind Enumerationen und Delegaten.  
  
## <a name="module-level-programming-elements"></a>Programmierelemente auf Modulebene  
 Prozeduren, Operatoren, Eigenschaften und Ereignisse sind der einzige Programmierelemente, die ausführbaren Code (Anweisungen, die Aktionen zur Laufzeit) enthalten können. Sie sind der *auf Modulebene* Elemente Ihres Programms. Weitere Informationen zu Elementen auf Prozedurebene finden Sie hier:  
  
-   [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 Datenelemente auf Modulebene sind Variablen, Konstanten, Enumerationen und Delegaten.  
  
## <a name="procedure-level-programming-elements"></a>Programmierelemente auf Prozedurebene  
 Die meisten der Inhalte *auf Prozedurebene* Elemente sind ausführbare Anweisungen, die den Code zur Laufzeit des Programms zu bilden. Alle ausführbarer Code muss in einer Prozedur (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`). Weitere Informationen finden Sie unter [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md).  
  
 Datenelemente auf Prozedurebene sind auf lokale Variablen und Konstanten beschränkt.  
  
## <a name="the-main-procedure"></a>Die Main-Prozedur  
 Die `Main` Prozedur ist der erste Code ausführen, wenn die Anwendung geladen wurde. `Main` Dient als Ausgangspunkt und gesamtsteuerung für Ihre Anwendung. Es gibt vier Arten von `Main`:  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 Die am häufigsten verwendete Vielfalt an dieses Verfahren ist `Sub Main()`. Weitere Informationen finden Sie unter [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [Beschränkungen in Visual Basic](../../../visual-basic/programming-guide/program-structure/limitations.md)
