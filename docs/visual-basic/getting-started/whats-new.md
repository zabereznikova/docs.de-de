---
title: Neues in Visual Basic | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- VB.StartPage.WhatsNew
dev_langs:
- VB
helpviewer_keywords:
- new features, Visual Basic
- what's new [Visual Basic]
- Visual Basic, what's new
ms.assetid: d7e97396-7f42-4873-a81c-4ebcc4b6ca02
caps.latest.revision: 145
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 55cf69a06a047c12f027007ed7180bf74307f2c9
ms.lasthandoff: 03/13/2017

---
# <a name="whats-new-for-visual-basic"></a>Neues in Visual Basic
Auf dieser Seite sind die Namen der wichtigsten Funktionen für jede Version von Visual Basic mit Beschreibungen der neuen und verbesserten Funktionen in der neuesten Version der Sprache aufgelistet.  
  
## <a name="previous-versions"></a>Frühere Versionen  
 Visual Basic / Visual Studio .NET 2002  
 Erste Version  
  
 Visual Basic / Visual Studio .NET 2003  
 Bitschiebeoperatoren, Deklaration von Schleifenvariablen  
  
 Visual Basic / Visual Studio .NET 2005  
 `My`-Typ und Hilfstypen (Zugriff auf App, Computer, Dateisystem, Netzwerk)  
  
 Visual Basic / Visual Studio .NET 2008  
 Language Integrated Query (LINQ), XML-Literale, lokaler Typrückschluss, Objektinitialisierer, anonyme Typen, Erweiterungsmethoden, lokaler `var`-Typrückschluss, Lambda-Ausdrücke, `if`-Operator, partielle Methoden, auf NULL festlegbare Werttypen  
  
 Visual Basic, Visual Studio .NET 2010  
 Automatisch implementierte Eigenschaften, Auflistungsinitialisierer, implizite Zeilenfortsetzung, dynamische, generische Ko-/Kontravarianz, Zugriff auf globalen Namespace  
  
 Visual Basic / Visual Studio .NET 2012  
 `Async` / `await`, Iteratoren, Aufruferinformationsattribute  
  
 Visual Basic / Visual Studio .NET 2013  
 Technologievorschau von .NET Compiler Platform ("Roslyn")  
  
 Visual Basic / Visual Studio .NET 2015  
 Aktuelle Version, siehe unten   
  
## <a name="current-version"></a>Aktuelle Version  
 [nameof](../../csharp/language-reference/keywords/nameof.md)  
 Sie können den nicht qualifizierten Zeichenfolgennamen eines Typs oder Members zur Verwendung in einer Fehlermeldung ohne Hartcodierung einer Zeichenfolge abrufen.  Dadurch bleibt der Code bei der Umgestaltung korrekt.  Diese Funktion eignet sich auch zum Einbinden von MVC-Links (Model-View-Controller) und das Auslösen von Ereignissen durch geänderte Eigenschaften.  
  
 [Zeichenfolgeninterpolierung](../../csharp/language-reference/keywords/interpolated-strings.md)  
 Sie können Ausdrücke für die Zeichenfolgeninterpolierung zum Erstellen von Zeichenfolgen verwenden.  Ein Ausdruck für eine interpolierte Zeichenfolge sieht wie eine Vorlagenzeichenfolge aus, die Ausdrücke enthält.  Eine interpolierte Zeichenfolge ist in Bezug auf die Argumente leichter zu verstehen als eine [Zusammengesetzte Formatierung](../../standard/base-types/composite-format.md).  
  
 [Null-conditional Member Access and Indexing (Memberzugriff und Indizierung mit 0-Bedingung)](../../csharp/language-reference/operators/null-conditional-operators.md)  
 Sie können eine Prüfung auf null auf sehr einfache syntaktische Weise vornehmen, bevor Sie eine Operation für den Memberzugriff (`?.`) oder die Indizierung (`?[]`) ausführen.  Mithilfe dieser Operatoren müssen Sie für die Prüfung auf null weniger Code schreiben, insbesondere beim tieferen Eindringen in Datenstrukturen.  Wenn der linke Operand oder Objektverweis NULL ist, geben die Operationen NULL zurück.  
  
 [Multi-line String Literals (Mehrzeilige Zeichenfolgenliterale)](../../visual-basic/programming-guide/language-features/strings/string-basics.md)  
 Zeichenfolgenliterale können Zeilenumbruchsequenzen enthalten.  Sie müssen nicht mehr die alte Problemumgehung mit `<xml><![CDATA[...text with newlines...]]></xml>.Value` verwenden.  
  
 Kommentare  
 Sie können Kommentare nach impliziten Zeilenfortsetzungen, innerhalb von Initialisierungsausdrücken und zwischen LINQ-Ausdrücken einfügen.  
  
 Intelligentere Auflösung vollqualifizierter Namen  
 Bei Code wie `Threading.Thread.Sleep(1000)` suchte Visual Basic bisher den Namespace "Threading", stellte fest, dass dieser mit "System.Threading" und "System.Windows.Threading" mehrdeutig war und meldete dann einen Fehler.  Nun berücksichtigt Visual Basic die beiden möglichen Namespaces gemeinsam.  Wenn Sie die Vervollständigungsliste anzeigen, listet der Visual Studio-Editor Member beider Typen in der Vervollständigungsliste auf.  
  
 Datumsliterale mit Jahresangabe am Anfang  
 Datumsliterale im Format jjjj-mm-tt sind möglich, z. B. `#2015-03-17 16:10 PM#`.  
  
 Schreibgeschützte Schnittstelleneigenschaften  
 Sie können mithilfe einer Readwrite-Eigenschaft schreibgeschützte Schnittstelleneigenschaften implementieren.  Die Schnittstelle garantiert Mindestfunktionalität und hindert eine Implementierungsklasse nicht daran, die Festlegung der Eigenschaft zuzulassen.  
  
 [TypeOf \<expr> IsNot \<type>](../../visual-basic/language-reference/operators/typeof-operator.md)  
 Zur besseren Lesbarkeit des Codes können Sie nun `TypeOf` mit `IsNot` verwenden.  
  
 [#Disable Warning\<<ID> und #Enable Warning \<<ID>](../../visual-basic/language-reference/directives/directives.md)  
 Sie können bestimmte Warnungen für Bereiche innerhalb einer Quelldatei deaktivieren und aktivieren.  
  
 Verbesserungen bei XML-Dokumentationskommentaren  
 Beim Schreiben von Dokumentationskommentaren steht intelligente Editor- und Buildunterstützung zum Überprüfen von Parameternamen, ordnungsgemäßer Handhabung von `crefs` (Generika, Operatoren usw.), Farben und Umgestaltung bereit.  
  
 [Partial Module and Interface Definitions (Partielle Modul- und Schnittstellendefinitionen)](../../visual-basic/language-reference/modifiers/partial.md)  
 Zusätzlich zu Klassen und Strukturen können Sie partielle Module und Schnittstellen deklarieren.  
  
 [Partial Module and Interface Definitions (#Region-Direktiven in Methodentexten)](../../visual-basic/language-reference/directives/region-directive.md)  
 Sie können die Begrenzer #Region...#End Region an einer beliebigen Stelle in einer Datei, innerhalb von Funktionen und sogar Funktionsrümpfe übergreifend einfügen.  
  
 [Overrides Definitions are Implicitly Overloads (Überschreibungsdefinitionen sind implizite Überladungen)](../../visual-basic/language-reference/modifiers/overrides.md)  
 Wenn Sie den `Overrides`-Modifizierer zu einer Definition hinzufügen, fügt der Compiler implizit `Overloads` hinzu, sodass Sie in allgemeinen Fällen weniger Code eingeben können.  
  
 CObj in Attributargumenten zulässig  
 Der Compiler gab gewöhnlich eine Fehlermeldung aus, dass CObj(...) bei Verwendung in Attributkonstruktionen keine Konstante war.  
  
 Deklarieren und Verwenden mehrdeutiger Methoden von unterschiedlichen Schnittstellen  
 Zuvor führte der folgende Code zu Fehlern, die Sie daran hinderten, `IMock` zu deklarieren oder `GetDetails` aufzurufen (wenn diese in C# deklariert waren):  
  
```vb  
Interface ICustomer  
  Sub GetDetails(x As Integer)  
End Interface  
  
Interface ITime  
  Sub GetDetails(x As String)  
End Interface  
  
Interface IMock : Inherits ICustomer, ITime  
  Overloads Sub GetDetails(x As Char)  
End Interface  
  
Interface IMock2 : Inherits ICustomer, ITime  
End Interface  
  
```  
  
 Nun verwendet der Compiler normale Regeln zur Überladungsauflösung, um die am besten geeignete `GetDetails`-Methode zum Aufrufen auszuwählen, und Sie können Schnittstellenbeziehungen in Visual Basic deklarieren, wie sie im Beispiel gezeigt sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Neues in Visual Studio 2017](https://docs.microsoft.com/en-us/visualstudio/ide/whats-new-in-visual-studio)
