---
title: Struktur eines Visual Basic-Programms | Microsoft-Dokumentation
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
- conditional compilation, Visual Basic
- program structure, Visual Basic
- procedures, structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 64aab045538461d86946c870fa428bf8ad4ec15e
ms.lasthandoff: 03/13/2017

---
# <a name="structure-of-a-visual-basic-program"></a>Struktur von Visual Basic-Programmen
Ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Programm aus Standardbausteinen erstellt wird. Ein *Lösung* umfasst eine oder mehrere Projekte. Ein *Projekt* wiederum kann eine oder mehrere Assemblys enthalten. Jede *Assembly* aus einer oder mehreren Quelldateien kompiliert wird. Ein *Quelldatei* enthält die Definition und Implementierung von Klassen, Strukturen, Module und Schnittstellen, die schließlich den gesamten Code enthalten.  
  
 Weitere Informationen über diese Bausteine einer [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programmieren, finden Sie unter [Projektmappen und Projekte](https://docs.microsoft.com/visualstudio/ide/solutions-and-projects-in-visual-studio) und [Assemblys und dem globalen Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).  
  
## <a name="file-level-programming-elements"></a>Programmierelemente auf Dateiebene  
 Wenn Sie ein Projekt oder eine Datei starten und Code-Editor zu öffnen, sehen Sie Code bereits an Ort und in der richtigen Reihenfolge. Code, den Sie schreiben sollten Folgendes beachten:  
  
1.  `Option`Anweisungen  
  
2.  `Imports`Anweisungen  
  
3.  `Namespace`Anweisungen und Elemente auf Namespaceebene  
  
 Wenn Sie die Anweisungen in einer anderen Reihenfolge eingeben, können Kompilierungsfehler ergeben.  
  
 Ein Programm kann auch Anweisungen für die bedingte Kompilierung enthalten. Sie können diese in der Quelldatei zwischen der Anweisungen von der oben dargestellten Reihenfolge einzufügen.  
  
### <a name="option-statements"></a>Optionsanweisungen  
 `Option`Anweisungen richten Grundregeln für nachfolgende Code hilft Syntax-und Logikfehler zu verhindern. Die [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md) wird sichergestellt, dass alle Variablen deklariert und richtig ist geschrieben, die verringert wird. Die [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md) trägt dazu bei, logischen Fehlern und Datenverlust zu minimieren, die beim Arbeiten mit Variablen unterschiedlichen Typs auftreten können. Die [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md) gibt die Art des Zeichenfolgenvergleichs an, die basierend auf ihren `Binary` oder `Text` Werte.  
  
### <a name="imports-statements"></a>Imports-Anweisungen  
 Sie können einschließen einer [Imports-Anweisung (.NET Namespace und Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) um außerhalb des Projekts definierte Namen zu importieren. Eine `Imports` -Anweisung kann Code zum Verweisen auf Klassen und anderen Typen in den importierten Namespaces definiert werden, ohne sie qualifizieren zu müssen. Sie können beliebig viele `Imports` Anweisungen nach Bedarf. Weitere Informationen finden Sie unter [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).  
  
### <a name="namespace-statements"></a>Namespace-Anweisung  
 Namespaces können, die Sie verwalten und klassifizieren Programmierelemente Gruppierung und den Zugriff zu vereinfachen. Verwenden Sie die [Namespace-Anweisung](../../../visual-basic/language-reference/statements/namespace-statement.md) zum Klassifizieren von der folgenden Anweisungen in einem bestimmten Namespace. Weitere Informationen finden Sie unter [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
### <a name="conditional-compilation-statements"></a>Anweisungen für die bedingte Kompilierung  
 Anweisungen für die bedingte Kompilierung können praktisch von überall in der Quelldatei angezeigt. Sie bewirken, dass Teile des Codes enthalten oder zur Kompilierzeit je nach Umständen ausgeschlossen werden. Auch können diese zum Debuggen Ihrer Anwendung, da bedingter Code im Debugmodus nur ausgeführt wird. Weitere Informationen finden Sie unter [bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).  
  
## <a name="namespace-level-programming-elements"></a>Namespace-Ebene Programmierelemente  
 Klassen, Strukturen und Module enthalten den Code für die in der Quelldatei. Sie sind *auf Namespaceebene* Elemente, die in einem Namespace oder auf der Ebene der Quelldatei angegeben werden können. Sie enthalten die Deklarationen aller anderen Programmierelemente. Schnittstellen, die Elementsignaturen definieren, doch keine Implementierung bereitstellen, werden ebenfalls auf Modulebene. Weitere Informationen zu den Elementen auf Modulebene finden Sie unter den folgenden:  
  
-   [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 Datenelemente auf Namespaceebene sind Enumerationen und Delegaten.  
  
## <a name="module-level-programming-elements"></a>Programmierelemente auf Modulebene  
 Prozeduren, Operatoren, Eigenschaften und Ereignisse sind die einzige Programmierelemente, die ausführbaren Code (Anweisungen, die Aktionen zur Laufzeit) enthalten können. Sie sind der *auf Modulebene* Elemente Ihres Programms. Weitere Informationen zu Elementen auf Prozedurebene finden Sie unter den folgenden:  
  
-   [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 Datenelemente auf Modulebene sind Variablen, Konstanten, Enumerationen und Delegaten.  
  
## <a name="procedure-level-programming-elements"></a>Programmierelemente auf Prozedurebene  
 Die meisten der Inhalte *auf Prozedurebene* Elemente sind ausführbare Anweisungen, die den Code zur Laufzeit des Programms zu bilden. Der gesamte ausführbare Code muss in einer Prozedur (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`). Weitere Informationen finden Sie unter [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md).  
  
 Datenelemente auf Prozedurebene sind auf lokale Variablen und Konstanten beschränkt.  
  
## <a name="the-main-procedure"></a>Die Main-Prozedur  
 Die `Main` -Prozedur ist der erste Code ausgeführt wird, wenn die Anwendung geladen wurde. `Main`Dient als Ausgangspunkt und gesamtsteuerung für Ihre Anwendung. Es gibt vier Arten von `Main`:  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 Die häufigste Variante dieser Prozedur ist `Sub Main()`. Weitere Informationen finden Sie unter [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Main-Prozedur in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)   
 [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [Beschränkungen in Visual Basic](../../../visual-basic/programming-guide/program-structure/limitations.md)
