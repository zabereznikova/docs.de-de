---
title: "Codekonventionen für C# (C#-Programmierhandbuch) | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cc3a51c6778127c7d2faf9a10b799875308d2850
ms.lasthandoff: 03/13/2017

---
# <a name="c-coding-conventions-c-programming-guide"></a>Codekonventionen für C# (C#-Programmierhandbuch)
Die [C#-Sprachspezifikation](http://go.microsoft.com/fwlink/?LinkId=199552) definiert keinen Codierungsstandard. Die Richtlinien in diesem Thema werden jedoch von Microsoft verwendet, um Beispiele und die Dokumentation zu entwickeln.  
  
 Codierungskonventionen dienen den folgenden Zwecken:  
  
-   Sie kreieren ein konsistentes Erscheinungsbild des Codes, sodass Leser sich auf den Inhalt und nicht auf das Layout konzentrieren können.  
  
-   Sie ermöglichen es den Lesern, Code schneller zu verstehen, da Rückschlüsse basierend auf den bisherigen Erfahrungen gezogen werden können.  
  
-   Sie erleichtern das Kopieren, Ändern und Pflegen des Codes.  
  
-   Sie zeigen die Best Practices für C#.  
  
## <a name="naming-conventions"></a>Namenskonventionen  
  
-   Verwenden Sie Namespacequalifizierungen in kurzen Beispielen, die keine [using-Anweisungen](../../../csharp/language-reference/keywords/using-directive.md) umfassen. Wenn Sie wissen, dass ein Namespace standardmäßig in ein Projekt importiert wird, müssen Sie den Namen aus diesem Namespace nicht voll qualifizieren. Qualifizierte Namen können nach einem Punkt (.) unterbrochen werden, wenn sie für eine einzelne Zeile zu lang sind, wie im folgenden Beispiel gezeigt.  
  
     [!code-cs[csProgGuideCodingConventions#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_1.cs)]  
  
-   Sie müssen nicht die Namen der Objekte ändern, die mit den Designertools von Visual Studio erstellt wurden, um sie an andere Richtlinien anzupassen.  
  
## <a name="layout-conventions"></a>Layoutkonventionen  
 Ein gutes Layout verwendet Formatierungen, um die Struktur des Codes hervorzuheben und um den Code verständlicher zu gestalten. Microsoft-Beispiele entsprechen den folgenden Konventionen:  
  
-   Verwenden Sie die Code-Editor-Standardeinstellungen (Intelligenter Einzug, vierstelliger Einzug, als Leerzeichen gespeicherte Tabulatoren). Weitere Informationen finden Sie unter [Optionen, Text-Editor, C#, Formatierung](https://docs.microsoft.com/visualstudio/ide/reference/options-text-editor-csharp-formatting).  
  
-   Schreiben Sie pro Zeile nur eine Anweisung.  
  
-   Schreiben Sie pro Zeile nur eine Deklaration.  
  
-   Wenn Fortsetzungszeilen nicht automatisch eingezogen werden, rücken Sie diese um einen Tabstopp (vier Leerzeichen) ein.  
  
-   Fügen Sie zwischen Methoden- und Eigenschaftsdefinitionen mindestens eine Leerzeile ein.  
  
-   Verwenden Sie Klammern, um Klauseln in einem Ausdruck zu kennzeichnen, wie im folgenden Code gezeigt.  
  
     [!code-cs[csProgGuideCodingConventions#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_2.cs)]  
  
## <a name="commenting-conventions"></a>Konventionen für Kommentare  
  
-   Fügen Sie den Kommentar in einer eigenen Zeile und nicht am Ende einer Codezeile ein.  
  
-   Beginnen Sie Kommentartext mit einem Großbuchstaben.  
  
-   Beenden Sie den Kommentartext mit einem Punkt.  
  
-   Fügen Sie ein Leerzeichen zwischen dem Kommentartrennzeichen (//) und dem Kommentartext ein, wie im folgenden Beispiel gezeigt.  
  
     [!code-cs[csProgGuideCodingConventions#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_3.cs)]  
  
-   Erstellen Sie keine formatierten Blöcke mit Sternchen um Kommentare.  
  
## <a name="language-guidelines"></a>Sprachrichtlinien  
 In den folgenden Abschnitten werden die Vorgehensweisen beschrieben, denen das C#-Team folgt, um Codebeispiele zu erstellen.  
  
### <a name="string-data-type"></a>String-Datentyp  
  
-   Verwenden Sie den `+`-Operator, um kurze Zeichenfolgen zu verketten, wie im folgenden Code gezeigt.  
  
     [!code-cs[csProgGuideCodingConventions#6](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_4.cs)]  
  
-   Verwenden Sie ein <xref:System.Text.StringBuilder>-Objekt, um Zeichenfolgen in Schleifen anzufügen, besonders bei der Arbeit mit großen Textmengen.  
  
     [!code-cs[csProgGuideCodingConventions#7](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_5.cs)]  
  
### <a name="implicitly-typed-local-variables"></a>Implizit typisierte lokale Variablen  
  
-   Verwenden Sie die [implizite Typisierung](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) für lokale Variablen, wenn der Typ der Variablen auf der rechten Seite der Zuweisung offensichtlich ist oder wenn der genaue Typ nicht von Bedeutung ist.  
  
     [!code-cs[csProgGuideCodingConventions#8](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_6.cs)]  
  
-   Verwenden Sie nicht [var](../../../csharp/language-reference/keywords/var.md), wenn der Typ nicht von der rechten Seite der Zuweisung offensichtlich ist.  
  
     [!code-cs[csProgGuideCodingConventions#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_7.cs)]  
  
-   Verlassen Sie sich nicht auf den Variablennamen, um den Typ der Variable anzugeben. Er ist unter Umständen nicht korrekt.  
  
     [!code-cs[csProgGuideCodingConventions#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_8.cs)]  
  
-   Vermeiden Sie den Einsatz von `var` anstelle von [dynamic](../../../csharp/language-reference/keywords/dynamic.md).  
  
-   Verwenden Sie die implizite Typisierung, um den Typ der Schleifenvariablen in [for](../../../csharp/language-reference/keywords/for.md)- und [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Schleifen zu bestimmen.  
  
     Im folgenden Beispiel wird die implizite Typisierung in einer `for`-Anweisung verwendet.  
  
     [!code-cs[csProgGuideCodingConventions#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_9.cs)]  
  
     Im folgenden Beispiel wird die implizite Typisierung in einer `foreach`-Anweisung verwendet.  
  
     [!code-cs[csProgGuideCodingConventions#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_10.cs)]  
  
### <a name="unsigned-data-type"></a>Datentyp ohne Vorzeichen  
  
-   Verwenden Sie im Allgemeinen `int` anstelle von Typen ohne Vorzeichen. Die Verwendung von `int` ist in C# üblich; durch den Einsatz von `int` wird die Interaktion mit anderen Bibliotheken vereinfacht.  
  
### <a name="arrays"></a>Arrays  
  
-   Verwenden Sie die präzise Syntax, wenn Sie Arrays in der Deklarationszeile initialisieren.  
  
     [!code-cs[csProgGuideCodingConventions#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_11.cs)]  
  
### <a name="delegates"></a>Delegaten  
  
-   Verwenden Sie die präzise Syntax, um Instanzen eines Delegattyps zu erstellen.  
  
     [!code-cs[csProgGuideCodingConventions#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_12.cs)]  
  
     [!code-cs[csProgGuideCodingConventions#15](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_13.cs)]  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a>try-catch- und using-Anweisungen in der Ausnahmebehandlung  
  
-   Verwenden Sie eine [try-catch](../../../csharp/language-reference/keywords/try-catch.md)-Anweisung für die meisten Ausnahmebehandlungen.  
  
     [!code-cs[csProgGuideCodingConventions#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_14.cs)]  
  
-   Vereinfachen Sie den Code mithilfe der C#-Anweisung [using](../../../csharp/language-reference/keywords/using-statement.md). Verwenden Sie bei einer [try-finally](../../../csharp/language-reference/keywords/try-finally.md)-Anweisung, in der der einzige Code im `finally`-Block ein Aufruf der <xref:System.IDisposable.Dispose%2A>-Methode ist, stattdessen eine `using`-Anweisung.  
  
     [!code-cs[csProgGuideCodingConventions#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_15.cs)]  
  
### <a name="-and-124124-operators"></a>&&- und &#124;&#124;-Operatoren  
  
-   Vermeiden Sie Ausnahmen und erhöhen Sie die Leistung durch Überspringen von unnötigen Vergleichen, indem Sie [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) anstelle von [&](../../../csharp/language-reference/operators/and-operator.md) und [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) anstelle von [&#124;](../../../csharp/language-reference/operators/or-operator.md) bei Vergleichen verwenden, wie im folgenden Beispiel gezeigt.  
  
     [!code-cs[csProgGuideCodingConventions#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_16.cs)]  
  
### <a name="new-operator"></a>New-Operator  
  
-   Verwenden Sie die präzise Form der Objektinstanziierung mit impliziter Typisierung, wie in der folgenden Deklaration dargestellt.  
  
     [!code-cs[csProgGuideCodingConventions#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_17.cs)]  
  
     Die vorherige Zeile entspricht der folgenden Deklaration.  
  
     [!code-cs[csProgGuideCodingConventions#20](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_18.cs)]  
  
-   Verwenden Sie Objektinitialisierer, um die Objekterstellung zu vereinfachen.  
  
     [!code-cs[csProgGuideCodingConventions#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_19.cs)]  
  
### <a name="event-handling"></a>Ereignisbehandlung  
  
-   Wenn Sie einen Ereignishandler definieren, den Sie später nicht entfernen müssen, verwenden Sie einen Lambdaausdruck.  
  
     [!code-cs[csProgGuideCodingConventions#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_20.cs)]  
  
     [!code-cs[csProgGuideCodingConventions#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_21.cs)]  
  
### <a name="static-members"></a>Statische Member  
  
-   Rufen Sie [statische](../../../csharp/language-reference/keywords/static.md) Member über den Klassennamen *ClassName.StaticMember* auf. Durch diese Empfehlung ist der Code besser lesbar, da der statische Zugriff eindeutig ist.  Qualifizieren Sie keinen statischen Member, der in einer Basisklasse mit dem Namen einer abgeleiteten Klasse definiert ist.  Während dieser Code kompiliert wird, ist die Lesbarkeit des Codes irreführend, und der Code kann später beschädigt werden, wenn Sie der abgeleiteten Klasse einen statischen Member mit dem gleichen Namen hinzufügen.  
  
### <a name="linq-queries"></a>LINQ-Abfragen  
  
-   Verwenden Sie aussagekräftige Namen für Abfragevariablen. Im folgenden Beispiel wird `seattleCustomers` für Kunden in Seattle verwendet.  
  
     [!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]  
  
-   Verwenden Sie Aliase, um mithilfe der Pascal-Schreibweise sicherzustellen, dass die korrekte Großschreibung von Eigenschaftennamen anonymer Typen verwendet wird.  
  
     [!code-cs[csProgGuideCodingConventions#26](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_23.cs)]  
  
-   Benennen Sie Eigenschaften um, wenn die Eigenschaftennamen im Ergebnis nicht eindeutig sind. Wenn die Abfrage beispielsweise einen Kundennamen und eine Händler-ID zurückgibt, anstatt sie als `Name` und `ID` im Ergebnis beizubehalten, benennen Sie sie um, um zu verdeutlichen, dass `Name` der Name eines Kunden und `ID` die ID eines Händlers ist.  
  
     [!code-cs[csProgGuideCodingConventions#27](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_24.cs)]  
  
-   Verwenden Sie die implizierte Typisierung in der Deklaration von Abfragevariablen und Bereichsvariablen.  
  
     [!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]  
  
-   Richten Sie Abfrageklauseln unter der [from](../../../csharp/language-reference/keywords/from-clause.md)-Klausel aus, wie in den vorherigen Beispielen gezeigt.  
  
-   Verwenden Sie vor anderen Abfrageklauseln [where](../../../csharp/language-reference/keywords/where-clause.md)-Klauseln, um sicherzustellen, dass nachfolgende Abfrageklauseln für den reduzierten, gefilterten Datensatz ausgeführt werden.  
  
     [!code-cs[csProgGuideCodingConventions#29](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_25.cs)]  
  
-   Verwenden Sie mehrere `from`-Klauseln anstelle einer [join](../../../csharp/language-reference/keywords/join-clause.md)-Klausel, um auf die inneren Auflistungen zuzugreifen. Eine Auflistung von `Student`-Objekten kann beispielsweise jeweils eine Auflistung von Testergebnissen enthalten. Wenn die folgende Abfrage ausgeführt wird, wird jedes Ergebnis über 90 zusammen mit dem Nachnamen des Studenten zurückgegeben, der das Testergebnis erzielt hat.  
  
     [!code-cs[csProgGuideCodingConventions#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_26.cs)]  
  
## <a name="security"></a>Sicherheit  
 Befolgen Sie die Richtlinien in [Richtlinien für das Schreiben von sicherem Code](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177).  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Codierungskonventionen](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)   
 [Richtlinien für das Schreiben von sicherem Code](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)
