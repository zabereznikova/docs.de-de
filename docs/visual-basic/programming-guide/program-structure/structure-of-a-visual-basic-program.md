---
title: Struktur von Visual Basic-Programmen
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], Visual Basic
- program structure [Visual Basic], Visual Basic
- procedures [Visual Basic], structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
ms.openlocfilehash: 90bc1fd62a05f670424e1fac368376401d1030c0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097773"
---
# <a name="structure-of-a-visual-basic-program"></a>Struktur von Visual Basic-Programmen

Ein Visual Basic Programm ist aus Standard Bausteinen aufgebaut. Eine Projekt *Mappe besteht aus einem oder* mehreren Projekten. Ein *Projekt* kann wiederum eine oder mehrere Assemblys enthalten. Jede *Assembly* wird aus einer oder mehreren Quelldateien kompiliert. Eine *Quelldatei* stellt die Definition und Implementierung von Klassen, Strukturen, Modulen und Schnittstellen bereit, die letztendlich den gesamten Code enthalten.  
  
 Weitere Informationen zu diesen Bausteinen eines Visual Basic Programms finden Sie Unterprojekt Mappen [und Projekte](/visualstudio/ide/solutions-and-projects-in-visual-studio) und Assemblys [in .net](../../../standard/assembly/index.md).  
  
## <a name="file-level-programming-elements"></a>Programmier Elemente auf Dateiebene  

 Wenn Sie ein Projekt oder eine Datei starten und den Code-Editor öffnen, sehen Sie, dass Code bereits vorhanden und in der richtigen Reihenfolge vorhanden ist. Jeder Code, den Sie schreiben, sollte der folgenden Reihenfolge folgen:  
  
1. `Option` Äußerungen  
  
2. `Imports` Äußerungen  
  
3. `Namespace` -Anweisungen und Elemente auf Namespace Ebene  
  
 Wenn Sie-Anweisungen in einer anderen Reihenfolge eingeben, können Kompilierungsfehler auftreten.  
  
 Ein Programm kann auch bedingte Kompilierungs Anweisungen enthalten. Sie können diese in der Quelldatei mit den Anweisungen der vorangehenden Sequenz interagieren.  
  
### <a name="option-statements"></a>Options Anweisungen  

 `Option` -Anweisungen richten Grundregeln für nachfolgenden Code ein, um Syntax-und Logikfehler zu vermeiden. Mit der [Option explizite-Anweisung](../../language-reference/statements/option-explicit-statement.md) wird sichergestellt, dass alle Variablen deklariert und richtig geschrieben werden, wodurch die Debugzeit verringert wird. Mit der [Option Strict-Anweisung](../../language-reference/statements/option-strict-statement.md) können Sie logische Fehler und Datenverluste minimieren, die auftreten können, wenn Sie zwischen Variablen verschiedener Datentypen arbeiten. Die [Option Compare-Anweisung](../../language-reference/statements/option-compare-statement.md) gibt an, wie Zeichen folgen miteinander verglichen werden, basierend auf Ihren- `Binary` oder- `Text` Werten.  
  
### <a name="imports-statements"></a>Imports-Anweisungen  

 Sie können eine [Imports-Anweisung (.NET-Namespace und-Typ)](../../language-reference/statements/imports-statement-net-namespace-and-type.md) einschließen, um Namen zu importieren, die außerhalb des Projekts definiert sind. Mit einer- `Imports` Anweisung kann Ihr Code auf Klassen und andere Typen verweisen, die im importierten Namespace definiert sind, ohne Sie qualifizieren zu müssen. Sie können beliebig viele- `Imports` Anweisungen verwenden. Weitere Informationen finden Sie unter [Verweise und die Imports-Anweisung](references-and-the-imports-statement.md).  
  
### <a name="namespace-statements"></a>Namespace-Anweisungen  

 Namespaces helfen Ihnen beim organisieren und klassifizieren ihrer Programmier Elemente, um die Gruppierung und den Zugriff zu vereinfachen. Mit der [Namespace-Anweisung](../../language-reference/statements/namespace-statement.md) können Sie die folgenden Anweisungen in einem bestimmten Namespace klassifizieren. Weitere Informationen finden Sie unter [Namespaces in Visual Basic](namespaces.md).  
  
### <a name="conditional-compilation-statements"></a>Bedingte Kompilierungs Anweisungen  

 Bedingte Kompilierungs Anweisungen können fast überall in der Quelldatei vorkommen. Sie bewirken, dass Teile Ihres Codes zur Kompilierzeit in Abhängigkeit von bestimmten Bedingungen eingeschlossen oder ausgeschlossen werden. Sie können Sie auch zum Debuggen Ihrer Anwendung verwenden, da bedingter Code nur im Debugmodus ausgeführt wird. Weitere Informationen finden Sie unter [bedingte Kompilierung](conditional-compilation.md).  
  
## <a name="namespace-level-programming-elements"></a>Programmier Elemente auf Namespace Ebene  

 Klassen, Strukturen und Module enthalten den gesamten Code in der Quelldatei. Sie sind Elemente auf *Namespace Ebene* , die in einem Namespace oder auf der Quelldatei Ebene vorkommen können. Sie enthalten die Deklarationen aller anderen Programmier Elemente. Schnittstellen, die Element Signaturen definieren, aber keine Implementierung bereitstellen, werden auch auf Modulebene angezeigt. Weitere Informationen zu den Elementen auf Modulebene finden Sie hier:  
  
- [Class-Anweisung](../../language-reference/statements/class-statement.md)  
  
- [Structure Statement](../../language-reference/statements/structure-statement.md)  
  
- [Module-Anweisung](../../language-reference/statements/module-statement.md)  
  
- [Interface-Anweisung](../../language-reference/statements/interface-statement.md)  
  
 Datenelemente auf Namespace Ebene sind Enumerationen und Delegaten.  
  
## <a name="module-level-programming-elements"></a>Programmier Elemente auf Modulebene  

 Prozeduren, Operatoren, Eigenschaften und Ereignisse sind die einzigen Programmier Elemente, die ausführbaren Code enthalten können (Anweisungen, die zur Laufzeit Aktionen ausführen). Dabei handelt es sich um die Elemente des Programms auf *Modulebene* . Weitere Informationen zu den Elementen auf Prozedur Ebene finden Sie unter:  
  
- [Function-Anweisung](../../language-reference/statements/function-statement.md)  
  
- [Sub-Anweisung](../../language-reference/statements/sub-statement.md)  
  
- [Declare Statement](../../language-reference/statements/declare-statement.md)  
  
- [Operator Statement](../../language-reference/statements/operator-statement.md)  
  
- [Property Statement](../../language-reference/statements/property-statement.md)  
  
- [Event-Anweisung](../../language-reference/statements/event-statement.md)  
  
 Datenelemente auf Modulebene sind Variablen, Konstanten, Enumerationen und Delegaten.  
  
## <a name="procedure-level-programming-elements"></a>Programmier Elemente auf Prozedur Ebene  

 Die meisten Inhalte von Elementen auf *Prozedur Ebene* sind ausführbare Anweisungen, die den Lauf Zeit Code des Programms bilden. Der gesamte ausführbare Code muss sich in einer Prozedur befinden ( `Function` , `Sub` , `Operator` , `Get` , `Set` , `AddHandler` , `RemoveHandler` , `RaiseEvent` ). Weitere Informationen finden Sie unter [Transact-SQL-Anweisungen](../language-features/statements.md).  
  
 Datenelemente auf Prozedur Ebene sind auf lokale Variablen und Konstanten beschränkt.  
  
## <a name="the-main-procedure"></a>Die Haupt Prozedur  

 Die `Main` Prozedur ist der erste Code, der ausgeführt wird, wenn die Anwendung geladen wurde. `Main` dient als Ausgangspunkt und allgemeine Kontrolle für Ihre Anwendung. Es gibt vier Arten von `Main` :  
  
- `Sub Main()`  
  
- `Sub Main(ByVal cmdArgs() As String)`  
  
- `Function Main() As Integer`  
  
- `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 Die häufigste Auswahl dieser Prozedur ist `Sub Main()` . Weitere Informationen finden Sie unter [Main Procedure in Visual Basic](main-procedure.md).  
  
## <a name="see-also"></a>Siehe auch

- [Main-Prozedur in Visual Basic](main-procedure.md)
- [Benennungskonventionen in Visual Basic](naming-conventions.md)
- [Beschränkungen in Visual Basic](limitations.md)
