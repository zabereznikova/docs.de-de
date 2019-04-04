---
title: C#-Referenz
ms.date: 02/14/2017
helpviewer_keywords:
- Visual C#, language reference
- language reference [C#]
- Programmer's Reference for C#
- C# language, reference
- reference, C# language
ms.assetid: 06de3167-c16c-4e1a-b3c5-c27841d4569a
ms.openlocfilehash: 6862ae72b235653d4576915605f14c9e4de92bce
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57845417"
---
# <a name="c-reference"></a>C#-Referenz
Dieser Abschnitt enthält Referenzmaterial zu Schlüsselwörtern, Operatoren, Sonderzeichen, Präprozessordirektiven, Compileroptionen sowie Compilerfehlern und -warnmeldungen von C#.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [C#-Schlüsselwörter](../../csharp/language-reference/keywords/index.md)  
 Enthält Links zu Informationen über C#-Schlüsselwörtern und zur Syntax.  
  
 [C#-Operatoren](../../csharp/language-reference/operators/index.md)  
 Enthält Links zu Informationen über C#-Operatoren und zur Syntax.  

 [C#-Sonderzeichen](../../csharp/language-reference/tokens/index.md)  
 Enthält Links zu Informationen über kontextbezogene Sonderzeichen in C# und deren Verwendung.  

 [C#-Präprozessoranweisungen](../../csharp/language-reference/preprocessor-directives/index.md)  
 Enthält Links zu Informationen über die Compilerbefehle zum Einbetten in C#-Quellcode.  
  
 [C#-Compileroptionen](../../csharp/language-reference/compiler-options/index.md)  
 Enthält Informationen über Compileroptionen und ihre Verwendung.  
  
 [C#-Compilerfehler](../../csharp/language-reference/compiler-messages/index.md)  
 Enthält Codeausschnitte, die die Ursache und Korrektur der C#-Compilerfehler und -warnungen veranschaulichen.  
  
 [C#-Programmiersprachenspezifikation](../../../_csharplang/spec/introduction.md)  
 Die C# 6.0-Sprachspezifikation. Dies ist ein Entwurfsvorschlag für die C# 6.0-Sprache. Version 5.0 wurde im Dezember 2017 als Dokument [Standard ECMA-334, 5. Edition](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf) veröffentlicht.

Die Features, die in C#-Versionen nach 6.0 implementiert wurden, werden in Sprachspezifikationsvorschlägen dargestellt. Diese Dokumente beschreiben die Deltas der Sprachspezifikation, um diese neuen Features hinzuzufügen. 

 [C# 7.0-Sprachvorschläge](../../../_csharplang/proposals/csharp-7.0/pattern-matching.md)  
 Es gibt eine Reihe neuer Features, die in C# 7.0 implementiert wurden. Dazu gehören der Musterabgleich, lokale Funktionen, out-Variablendeklarationen, throw-Ausdrücke, binäre Literale und Zahlentrennzeichen. Dieser Ordner enthält die Spezifikationen für jedes dieser Features.
  
 [C# 7.1-Sprachvorschläge](../../../_csharplang/proposals/csharp-7.1/async-main.md)  
 In C# 7.1 wurden neue Features hinzugefügt. Erstens können Sie eine `Main`-Methode schreiben, die `Task` oder `Task<int>` zurückgibt. Dadurch können Sie den `async`-Modifizierer `Main` hinzufügen. Der `default`-Ausdruck kann ohne Typ an Stellen verwendet werden, an denen der Typ abgeleitet werden kann. Darüber hinaus können Tupelmembernamen abgeleitet werden. Schließlich kann Mustervergleich mit Generics verwendet werden.

 [C# 7.2-Sprachvorschläge](../../../_csharplang/proposals/csharp-7.2/readonly-ref.md)  
 C# 7.2 hat eine Reihe von kleinen Features hinzugefügt. Sie können Argumente durch einen schreibgeschützten Verweis mit dem Schlüsselwort `in` übergeben. Es gibt eine Reihe von Low-Level-Änderungen, die die Sicherheit zur Kompilierzeit für `Span` und verwandte Typen unterstützen. Sie können benannte Argumente verwenden, bei denen spätere Argumente in einigen Situationen positional sind. Mit dem `private protected`-Zugriffsmodifizierer können Sie festlegen, dass Aufrufer auf abgeleitete Typen beschränkt sind, die in derselben Assembly implementiert sind. Der `?:`-Operator kann in einen Verweis auf eine Variable aufgelöst werden. Sie können auch hexadezimale und binäre Zahlen mit einem führenden Zifferntrennzeichen formatieren.   

 [C# 7.3-Sprachvorschläge](../../../_csharplang/proposals/csharp-7.3/blittable.md)  
 C# 7.3 ist eine weitere Unterversion, die mehrere kleine Aktualisierungen enthält. Sie können neue Einschränkungen für generische Typparameter verwenden. Weitere Änderungen erleichtern das Arbeiten mit `fixed`-Feldern, einschließlich der Verwendung von [`stackalloc`](./keywords/stackalloc.md)-Zuordnungen. Lokale Variablen, die mit dem Schlüsselwort `ref` deklariert wurden, können neu zugewiesen werden, um sich auf neuen Speicher zu beziehen. Sie können Attribute für automatisch implementierte Eigenschaften festlegen, die auf das vom Compiler generierte Sicherungsfeld abzielen. Ausdrucksvariablen können in Initialisierern verwendet werden. Tupel können hinsichtlich ihrer Gleichheit (oder Ungleichheit) verglichen werden. Außerdem wurden einige Verbesserungen an der Überladungsauflösung vorgenommen.
  
 [C# 8.0-Sprachvorschläge](../../../_csharplang/proposals/csharp-8.0/nullable-reference-types.md) C# 8.0 ist in der Vorschau verfügbar. Die folgenden Vorschläge sind die aktuellen Versionen der Spezifikationen für diese Features. Einige sind vollständiger, an anderen wird noch gearbeitet. Zu den Features, die in Vorschauversionen enthalten sind, gehören Nullable-Verweistypen, rekursiver Musterabgleich, asynchrone Streams, Bereiche und Indizes, musterbasiertes using und using-Deklarationen sowie NULL-Zusammenfügungszuordnungen.
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Leitfaden für C#](../../csharp/index.md)  
 Enthält ein Portal für die Visual C#-Dokumentation.  
  
 [Verwenden der Visual Studio-Entwicklungsumgebung für C#](/visualstudio/csharp-ide/using-the-visual-studio-development-environment-for-csharp)  
 Enthält Links zu konzeptionellen und aufgabenspezifischen Themen, in denen IDE und Editor beschrieben werden.  
  
 [C#-Programmierhandbuch](../../csharp/programming-guide/index.md)  
 Enthält Informationen zur Verwendung der C#-Programmiersprache.
