---
description: C#-Referenz
title: C#-Referenz
ms.date: 01/13/2021
ms.custom: updateeachrelease
f1_keywords:
- _CSharpKeyword
helpviewer_keywords:
- Visual C#, language reference
- language reference [C#]
- Programmer's Reference for C#
- C# language, reference
- reference, C# language
ms.assetid: 06de3167-c16c-4e1a-b3c5-c27841d4569a
ms.openlocfilehash: 663d08921b1fb6c5013ce8dddb044ba12ead8409
ms.sourcegitcommit: 4f5f1855849cb02c3b610c7006ac21d7429f3348
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "98235234"
---
# <a name="c-reference"></a>C#-Referenz

Dieser Abschnitt enthält Referenzmaterial zu Schlüsselwörtern, Operatoren, Sonderzeichen, Präprozessordirektiven, Compileroptionen sowie Compilerfehlern und -warnmeldungen von C#.  
  
## <a name="in-this-section"></a>In diesem Abschnitt

 [C#-Schlüsselwörter](./keywords/index.md)  
 Enthält Links zu Informationen über C#-Schlüsselwörtern und zur Syntax.  
  
 [C#-Operatoren](./operators/index.md)  
 Enthält Links zu Informationen über C#-Operatoren und zur Syntax.  

 [C#-Sonderzeichen](./tokens/index.md)  
 Enthält Links zu Informationen über kontextbezogene Sonderzeichen in C# und deren Verwendung.  

 [C#-Präprozessoranweisungen](./preprocessor-directives/index.md)  
 Enthält Links zu Informationen über die Compilerbefehle zum Einbetten in C#-Quellcode.  
  
 [C#-Compileroptionen](./compiler-options/index.md)  
 Enthält Informationen über Compileroptionen und ihre Verwendung.  
  
 [C#-Compilerfehler](./compiler-messages/index.md)  
 Enthält Codeausschnitte, die die Ursache und Korrektur der C#-Compilerfehler und -warnungen veranschaulichen.  
  
 [C#-Programmiersprachenspezifikation](../../../_csharplang/spec/introduction.md)  
 Die C# 6.0-Sprachspezifikation. Dies ist ein Entwurfsvorschlag für die C# 6.0-Sprache. Dieses Dokument wird durch die Zusammenarbeit mit dem Ecma International-Ausschuss für C#-Standards weiterentwickelt. Version 5.0 wurde im Dezember 2017 als Dokument [Standard ECMA-334, 5. Edition](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf) veröffentlicht.

Die Features, die in C#-Versionen nach 6.0 implementiert wurden, werden in Sprachspezifikationsvorschlägen dargestellt. Diese Dokumente beschreiben die Deltas der Sprachspezifikation, um diese neuen Features hinzuzufügen. Sie liegen in Entwurfsform vor. Diese Spezifikationen werden weiterentwickelt und zur formellen Prüfung und Implementierung in eine zukünftige Version des C#-Standards an den Ecma International-Normungsausschuss weitergeleitet.

 [Vorschläge für die C# 7.0-Spezifikation](../../../_csharplang/proposals/csharp-7.0/pattern-matching.md)  
 Es gibt eine Reihe neuer Features, die in C# 7.0 implementiert wurden. Dazu gehören der Musterabgleich, lokale Funktionen, out-Variablendeklarationen, throw-Ausdrücke, binäre Literale und Zahlentrennzeichen. Dieser Ordner enthält die Spezifikationen für jedes dieser Features.
  
 [Vorschläge für die C# 7.1-Spezifikation](../../../_csharplang/proposals/csharp-7.1/async-main.md)  
 In C# 7.1 wurden neue Features hinzugefügt. Erstens können Sie eine `Main`-Methode schreiben, die `Task` oder `Task<int>` zurückgibt. Dadurch können Sie den `async`-Modifizierer `Main` hinzufügen. Der `default`-Ausdruck kann ohne Typ an Stellen verwendet werden, an denen der Typ abgeleitet werden kann. Darüber hinaus können Tupelmembernamen abgeleitet werden. Schließlich kann Mustervergleich mit Generics verwendet werden.

 [Vorschläge für die C# 7.2-Spezifikation](../../../_csharplang/proposals/csharp-7.2/readonly-ref.md)  
 C# 7.2 hat eine Reihe von kleinen Features hinzugefügt. Sie können Argumente durch einen schreibgeschützten Verweis mit dem Schlüsselwort `in` übergeben. Es gibt eine Reihe von Low-Level-Änderungen, die die Sicherheit zur Kompilierzeit für `Span` und verwandte Typen unterstützen. Sie können benannte Argumente verwenden, bei denen spätere Argumente in einigen Situationen positional sind. Mit dem `private protected`-Zugriffsmodifizierer können Sie festlegen, dass Aufrufer auf abgeleitete Typen beschränkt sind, die in derselben Assembly implementiert sind. Der `?:`-Operator kann in einen Verweis auf eine Variable aufgelöst werden. Sie können auch hexadezimale und binäre Zahlen mit einem führenden Zifferntrennzeichen formatieren.

 [Vorschläge für die C# 7.3-Spezifikation](../../../_csharplang/proposals/csharp-7.3/blittable.md)  
 C# 7.3 ist eine weitere Unterversion, die mehrere kleine Aktualisierungen enthält. Sie können neue Einschränkungen für generische Typparameter verwenden. Weitere Änderungen erleichtern das Arbeiten mit `fixed`-Feldern, einschließlich der Verwendung von [`stackalloc`](./operators/stackalloc.md)-Zuordnungen. Lokale Variablen, die mit dem Schlüsselwort `ref` deklariert wurden, können neu zugewiesen werden, um sich auf neuen Speicher zu beziehen. Sie können Attribute für automatisch implementierte Eigenschaften festlegen, die auf das vom Compiler generierte Sicherungsfeld abzielen. Ausdrucksvariablen können in Initialisierern verwendet werden. Tupel können hinsichtlich ihrer Gleichheit (oder Ungleichheit) verglichen werden. Außerdem wurden einige Verbesserungen an der Überladungsauflösung vorgenommen.
  
 [Vorschläge für die C# 8.0-Spezifikation](../../../_csharplang/proposals/csharp-8.0/nullable-reference-types.md)  
 C# 8.0 wird mit .NET Core 3.0 zur Verfügung gestellt. Zu den Features gehören Nullable-Verweistypen, rekursiver Musterabgleich, Standardschnittstellenmethoden, asynchrone Streams, Bereiche und Indizes, musterbasierte using-Anweisung und using-Deklarationen, NULL-Sammelzuweisungen sowie schreibgeschützte Instanzmember.

 [Vorschläge für die C# 9.0-Spezifikation](../../../_csharplang/proposals/csharp-9.0/records.md)  
 C# 9.0 wird mit .NET 5.0 zur Verfügung gestellt. Zu den Features zählen Datensätze, Anweisungen auf oberster Ebene, Erweiterungen zum Musterabgleich, Init-Only-Setter, zieltypisierte neue Ausdrücke, Modulinitialisierer, Erweiterungen für partielle Methoden, statische anonyme Funktionen, zieltypisierte bedingte Ausdrücke, kovariante Rückgabetypen, Erweiterungen für GetEnumerator in foreach-Schleifen, Parameter zum Verwerfen von Lambdaausdrücken, Attribute in lokalen Funktionen, Integer mit nativer Größe, Funktionszeiger, die Unterdrückung der Ausgabe des localsinit-Flags und nicht eingeschränkte Typparameteranmerkungen.

## <a name="related-sections"></a>Verwandte Abschnitte  

 [Verwenden der Visual Studio-Entwicklungsumgebung für C#](/visualstudio/get-started/csharp)  
 Enthält Links zu konzeptionellen und aufgabenspezifischen Themen, in denen IDE und Editor beschrieben werden.  
  
 [C#-Programmierhandbuch](../programming-guide/index.md)  
 Enthält Informationen zur Verwendung der C#-Programmiersprache.
