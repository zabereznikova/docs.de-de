---
title: Codekonventionen für C# – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
ms.openlocfilehash: 77b173a420f26834855e0bdca3c8d04406ac65d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398376"
---
# <a name="c-coding-conventions-c-programming-guide"></a>Codekonventionen für C# (C#-Programmierhandbuch)

Codierungskonventionen dienen den folgenden Zwecken:  
  
- Sie kreieren ein konsistentes Erscheinungsbild des Codes, sodass Leser sich auf den Inhalt und nicht auf das Layout konzentrieren können.  
  
- Sie ermöglichen es den Lesern, Code schneller zu verstehen, da Rückschlüsse basierend auf den bisherigen Erfahrungen gezogen werden können.  
  
- Sie erleichtern das Kopieren, Ändern und Pflegen des Codes.  
  
- Sie zeigen die Best Practices für C#.  

Die Leitlinien in diesem Artikel werden von Microsoft befolgt, um Beispiele und Dokumentation zu entwickeln.  
  
## <a name="naming-conventions"></a>Namenskonventionen  
  
- Verwenden Sie Namespacequalifizierungen in kurzen Beispielen, die keine [using-Anweisungen](../../language-reference/keywords/using-directive.md) umfassen. Wenn Sie wissen, dass ein Namespace standardmäßig in ein Projekt importiert wird, müssen Sie den Namen aus diesem Namespace nicht voll qualifizieren. Qualifizierte Namen können nach einem Punkt (.) unterbrochen werden, wenn sie für eine einzelne Zeile zu lang sind, wie im folgenden Beispiel gezeigt.  
  
     [!code-csharp[csProgGuideCodingConventions#1](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#1)]  
  
- Sie müssen nicht die Namen der Objekte ändern, die mit den Designertools von Visual Studio erstellt wurden, um sie an andere Richtlinien anzupassen.  
  
## <a name="layout-conventions"></a>Layoutkonventionen  

Ein gutes Layout verwendet Formatierungen, um die Struktur des Codes hervorzuheben und um den Code verständlicher zu gestalten. Microsoft-Beispiele entsprechen den folgenden Konventionen:  
  
- Verwenden Sie die Code-Editor-Standardeinstellungen (Intelligenter Einzug, vierstelliger Einzug, als Leerzeichen gespeicherte Tabulatoren). Weitere Informationen finden Sie unter [Optionen, Text-Editor, C#, Formatierung](/visualstudio/ide/reference/options-text-editor-csharp-formatting).  
  
- Schreiben Sie pro Zeile nur eine Anweisung.  
  
- Schreiben Sie pro Zeile nur eine Deklaration.  
  
- Wenn Fortsetzungszeilen nicht automatisch eingezogen werden, rücken Sie diese um einen Tabstopp (vier Leerzeichen) ein.  
  
- Fügen Sie zwischen Methoden- und Eigenschaftsdefinitionen mindestens eine Leerzeile ein.  
  
- Verwenden Sie Klammern, um Klauseln in einem Ausdruck zu kennzeichnen, wie im folgenden Code gezeigt.  
  
     [!code-csharp[csProgGuideCodingConventions#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#2)]  
  
## <a name="commenting-conventions"></a>Konventionen für Kommentare  
  
- Fügen Sie den Kommentar in einer eigenen Zeile und nicht am Ende einer Codezeile ein.  
  
- Beginnen Sie Kommentartext mit einem Großbuchstaben.  
  
- Beenden Sie den Kommentartext mit einem Punkt.  
  
- Fügen Sie ein Leerzeichen zwischen dem Kommentartrennzeichen (//) und dem Kommentartext ein, wie im folgenden Beispiel gezeigt.  
  
     [!code-csharp[csProgGuideCodingConventions#3](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#3)]  
  
- Erstellen Sie keine formatierten Blöcke mit Sternchen um Kommentare.  
  
## <a name="language-guidelines"></a>Sprachrichtlinien  

In den folgenden Abschnitten werden die Vorgehensweisen beschrieben, denen das C#-Team folgt, um Codebeispiele zu erstellen.  
  
### <a name="string-data-type"></a>String-Datentyp  
  
- Verwenden Sie die [Zeichenfolgeninterpolation](../../language-reference/tokens/interpolated.md), um wie im folgenden Code gezeigt kurze Zeichenfolgen zu verketten.  
  
     [!code-csharp[csProgGuideCodingConventions#6](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#6)]  
  
- Verwenden Sie ein <xref:System.Text.StringBuilder>-Objekt, um Zeichenfolgen in Schleifen anzufügen, besonders bei der Arbeit mit großen Textmengen.  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  
  
### <a name="implicitly-typed-local-variables"></a>Implizit typisierte lokale Variablen  
  
- Verwenden Sie die [implizite Typisierung](../classes-and-structs/implicitly-typed-local-variables.md) für lokale Variablen, wenn der Typ der Variablen auf der rechten Seite der Zuweisung offensichtlich ist oder wenn der genaue Typ nicht von Bedeutung ist.  
  
     [!code-csharp[csProgGuideCodingConventions#8](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#8)]  
  
- Verwenden Sie nicht [var](../../language-reference/keywords/var.md), wenn der Typ nicht von der rechten Seite der Zuweisung offensichtlich ist.  
  
     [!code-csharp[csProgGuideCodingConventions#9](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#9)]  
  
- Verlassen Sie sich nicht auf den Variablennamen, um den Typ der Variable anzugeben. Er ist unter Umständen nicht korrekt.  
  
     [!code-csharp[csProgGuideCodingConventions#10](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#10)]  
  
- Vermeiden Sie den Einsatz von `var` anstelle von [dynamic](../../language-reference/builtin-types/reference-types.md).  
  
- Verwenden Sie die implizite Typisierung, um den Typ der Schleifenvariablen in [for](../../language-reference/keywords/for.md)-Schleifen zu bestimmen.  
  
     Im folgenden Beispiel wird die implizite Typisierung in einer `for`-Anweisung verwendet.  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  

- Verwenden Sie nicht die implizite Typisierung, um den Typ der Schleifenvariablen in [foreach](../../language-reference/keywords/foreach-in.md)-Schleifen zu bestimmen.

     Im folgenden Beispiel wird die explizite Typisierung in einer `foreach`-Anweisung verwendet.

     [!code-csharp[csProgGuideCodingConventions#12](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#12)]

     > [!NOTE]
     > Achten Sie darauf, nicht versehentlich den Typ eines Elements in der Iterable-Sammlung zu ändern. Beispielsweise ist es einfach, in einer <xref:System.Linq.IQueryable?displayProperty=nameWithType>-Anweisung von <xref:System.Collections.IEnumerable?displayProperty=nameWithType> zu `foreach` zu wechseln, was die Ausführung einer Abfrage ändert.

### <a name="unsigned-data-type"></a>Datentyp ohne Vorzeichen  
  
Verwenden Sie im Allgemeinen `int` anstelle von Typen ohne Vorzeichen. Die Verwendung von `int` ist in C# üblich; durch den Einsatz von `int` wird die Interaktion mit anderen Bibliotheken vereinfacht.  
  
### <a name="arrays"></a>Arrays  
  
Verwenden Sie die präzise Syntax, wenn Sie Arrays in der Deklarationszeile initialisieren.  
  
[!code-csharp[csProgGuideCodingConventions#13](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#13)]  
  
### <a name="delegates"></a>Delegaten  
  
Verwenden Sie die präzise Syntax, um Instanzen eines Delegattyps zu erstellen.  
  
[!code-csharp[csProgGuideCodingConventions#14](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#14)]  
  
[!code-csharp[csProgGuideCodingConventions#15](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#15)]  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a>try-catch- und using-Anweisungen in der Ausnahmebehandlung  
  
- Verwenden Sie eine [try-catch](../../language-reference/keywords/try-catch.md)-Anweisung für die meisten Ausnahmebehandlungen.  
  
     [!code-csharp[csProgGuideCodingConventions#16](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#16)]  
  
- Vereinfachen Sie den Code mithilfe der C#-Anweisung [using](../../language-reference/keywords/using-statement.md). Verwenden Sie bei einer [try-finally](../../language-reference/keywords/try-finally.md)-Anweisung, in der der einzige Code im `finally`-Block ein Aufruf der <xref:System.IDisposable.Dispose%2A>-Methode ist, stattdessen eine `using`-Anweisung.  
  
     [!code-csharp[csProgGuideCodingConventions#17](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#17)]  
  
### <a name="-and-124124-operators"></a>&&- und &#124;&#124;-Operatoren  
  
Vermeiden Sie Ausnahmen und erhöhen Sie die Leistung durch Überspringen von unnötigen Vergleichen, indem Sie [&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-) anstelle von [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-) und [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-) anstelle von [&#124;](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-) bei Vergleichen verwenden, wie im folgenden Beispiel gezeigt.  
  
[!code-csharp[csProgGuideCodingConventions#18](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#18)]  
  
### <a name="new-operator"></a>New-Operator  
  
- Verwenden Sie die präzise Form der Objektinstanziierung mit impliziter Typisierung, wie in der folgenden Deklaration dargestellt.  
  
     [!code-csharp[csProgGuideCodingConventions#19](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#19)]  
  
     Die vorherige Zeile entspricht der folgenden Deklaration.  
  
     [!code-csharp[csProgGuideCodingConventions#20](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#20)]  
  
- Verwenden Sie Objektinitialisierer, um die Objekterstellung zu vereinfachen.  
  
     [!code-csharp[csProgGuideCodingConventions#21](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#21)]  
  
### <a name="event-handling"></a>Ereignisbehandlung  
  
Wenn Sie einen Ereignishandler definieren, den Sie später nicht entfernen müssen, verwenden Sie einen Lambdaausdruck.  
  
[!code-csharp[csProgGuideCodingConventions#22](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#22)]  
  
[!code-csharp[csProgGuideCodingConventions#23](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#23)]  
  
### <a name="static-members"></a>Statische Member  
  
Rufen Sie [statische](../../language-reference/keywords/static.md) Member über den Klassennamen *ClassName.StaticMember* auf. Durch diese Empfehlung ist der Code besser lesbar, da der statische Zugriff eindeutig ist.  Qualifizieren Sie keinen statischen Member, der in einer Basisklasse mit dem Namen einer abgeleiteten Klasse definiert ist.  Während dieser Code kompiliert wird, ist die Lesbarkeit des Codes irreführend, und der Code kann später beschädigt werden, wenn Sie der abgeleiteten Klasse einen statischen Member mit dem gleichen Namen hinzufügen.  
  
### <a name="linq-queries"></a>LINQ-Abfragen  
  
- Verwenden Sie aussagekräftige Namen für Abfragevariablen. Im folgenden Beispiel wird `seattleCustomers` für Kunden in Seattle verwendet.  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- Verwenden Sie Aliase, um mithilfe der Pascal-Schreibweise sicherzustellen, dass die korrekte Großschreibung von Eigenschaftennamen anonymer Typen verwendet wird.  
  
     [!code-csharp[csProgGuideCodingConventions#26](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#26)]  
  
- Benennen Sie Eigenschaften um, wenn die Eigenschaftennamen im Ergebnis nicht eindeutig sind. Wenn die Abfrage beispielsweise einen Kundennamen und eine Händler-ID zurückgibt, anstatt sie als `Name` und `ID` im Ergebnis beizubehalten, benennen Sie sie um, um zu verdeutlichen, dass `Name` der Name eines Kunden und `ID` die ID eines Händlers ist.  
  
     [!code-csharp[csProgGuideCodingConventions#27](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#27)]  
  
- Verwenden Sie die implizierte Typisierung in der Deklaration von Abfragevariablen und Bereichsvariablen.  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- Richten Sie Abfrageklauseln unter der [from](../../language-reference/keywords/from-clause.md)-Klausel aus, wie in den vorherigen Beispielen gezeigt.  
  
- Verwenden Sie vor anderen Abfrageklauseln [where](../../language-reference/keywords/where-clause.md)-Klauseln, um sicherzustellen, dass nachfolgende Abfrageklauseln für den reduzierten, gefilterten Datensatz ausgeführt werden.  
  
     [!code-csharp[csProgGuideCodingConventions#29](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#29)]  
  
- Verwenden Sie mehrere `from`-Klauseln anstelle einer [join](../../language-reference/keywords/join-clause.md)-Klausel, um auf die inneren Auflistungen zuzugreifen. Eine Auflistung von `Student`-Objekten kann beispielsweise jeweils eine Auflistung von Testergebnissen enthalten. Wenn die folgende Abfrage ausgeführt wird, wird jedes Ergebnis über 90 zusammen mit dem Nachnamen des Studenten zurückgegeben, der das Testergebnis erzielt hat.  
  
     [!code-csharp[csProgGuideCodingConventions#30](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#30)]  
  
## <a name="security"></a>Sicherheit  

Befolgen Sie die Richtlinien in [Richtlinien für das Schreiben von sicherem Code](../../../standard/security/secure-coding-guidelines.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Visual Basic-Codierungskonventionen](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)
- [Richtlinien für das Schreiben von sicherem Code](../../../standard/security/secure-coding-guidelines.md)
