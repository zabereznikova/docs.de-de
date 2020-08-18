---
title: Konzepte und Terminologie (funktionale Transformation) (C#)
description: Funktionale Programmierfunktionen vereinfachen die Transformation von XML. Hier erfahren Sie mehr über die Konzepte und die Terminologie von reinen Funktionstransformationen in C#.
ms.date: 07/20/2015
ms.assetid: 03defb3a-7e17-4ab1-8efa-4dd66621e860
ms.openlocfilehash: ca05a914f6156730e773d1effebfc72626b16507
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063275"
---
# <a name="concepts-and-terminology-functional-transformation-c"></a>Konzepte und Terminologie (funktionale Transformation) (C#)

Dieses Thema führt Sie in die Konzepte und Begriffe ein, die im Zusammenhang mit reinen funktionalen Transformationen verwendet werden. Bei Verwendung der funktionalen Transformation zum Transformieren von Daten erhalten Sie Code, der häufig schneller programmiert werden kann, ausdrucksstärker ist und einfacher von Fehlern bereinigt und verwaltet werden kann als Code, der auf die herkömmliche imperative Methode zurückzuführen ist.

Beachten Sie, dass die Themen in diesem Abschnitt keine vollständige Erläuterung der funktionalen Programmierung darstellen. In diesen Themen werden vielmehr einige der Funktionen zur funktionalen Programmierung beschrieben, die das Transformieren von XML von einer Form in eine andere erleichtern.

## <a name="what-is-pure-functional-transformation"></a>Was ist die reine funktionale Transformation?

Bei der *reinen funktionalen Transformation* definiert ein Satz von Funktionen, die sogenannten *reinen Funktionen*, wie ein Satz strukturierter Daten aus ihrer Originalform in eine andere Form transformiert werden soll. Das Wort „rein“ bedeutet dabei, dass die Funktionen *zusammensetzbar* sind. Dazu müssen sie die folgenden Voraussetzungen erfüllen:

- Sie müssen *eigenständig* sein, damit sie frei und ohne jede Verflechtungen oder Abhängigkeiten vom Rest des Programms geordnet und umgeordnet werden können. Reine Transformationen existieren komplett unabhängig von ihrer Umgebung und beeinflussen diese auch nicht. Damit haben die in der Transformation verwendeten Funktionen keinerlei *Nebenwirkungen*.

- Sie müssen *zustandslos* sein, damit das Ausführen ein und derselben Funktion oder eines bestimmten Satzes von Funktionen bei ein und derselben Eingabe auch immer zur selben Ausgabe führt. Reine Transformationen besitzen keine „Erinnerung“ an ihre vorherige Verwendung.

> [!IMPORTANT]
> Im übrigen Teil dieses Lernprogramms wird der Begriff „reine Funktion“ allgemein als Bezeichnung für einen Programmieransatz und nicht als Bezeichnung für eine bestimmte Sprachfunktion verwendet.
>
> Beachten Sie, dass reine Funktionen in C# als Methoden implementiert werden müssen.
>
> Verwechseln Sie bitte auch nicht die reinen Funktionen mit den reinen virtuellen Methoden in C++. Die reinen virtuellen Methoden in C++ geben an, dass die enthaltene Klasse abstrakt ist und dass kein Methodentext angegeben wird.

### <a name="functional-programming"></a>Funktionale Programmierung

Die *funktionale Programmierung* (FP) ist ein Programmieransatz, der die reine funktionale Transformation direkt unterstützt.

In der Vergangenheit standen Allzwecksprachen zur funktionalen Programmierung, wie ML, Scheme, Haskell und F#, im Mittelpunkt des wissenschaftlichen Interesses. Es war zwar immer möglich, in C# reine funktionale Transformationen zu schreiben, die damit verbundenen Schwierigkeiten ließen aber die meisten Programmierer davor zurückschrecken. In neueren Versionen von C# stehen jedoch neue Sprachkonstrukte, z.B. Lambdaausdrücke und Typableitung, zur Verfügung, mit denen die funktionale Programmierung wesentlich einfacher und produktiver wurde.

Weitere Informationen zum funktionalen Programmieren finden Sie unter [Funktionale Programmierung und Imperative Programmierung (C#)](./functional-programming-vs-imperative-programming.md)

#### <a name="domain-specific-fp-languages"></a>Domänenspezifische FP-Sprachen

Während allgemeine FP-Sprachen keine große Verbreitung gefunden haben, konnten sich bestimmte domänenspezifische FP-Sprachen durchsetzen. So wird z. B. das Aussehen vieler Internetseiten durch Cascading Style Sheets (CSS) gesteuert, während für die Bearbeitung von XML-Daten häufig XSLT-Stylesheets (Extensible Stylesheet Language Transformations) verwendet werden. Weitere Informationen zu XSLT finden Sie unter [XSLT-Transformationen](../../../../standard/data/xml/xslt-transformations.md).

## <a name="terminology"></a>Terminologie

Im Folgenden finden Sie Definitionen für eine Reihe von Begriffen, die im Zusammenhang mit der funktionalen Transformation verwendet werden:

Funktion höherer Ordnung (Funktion erster Ordnung) \
Funktion, die als programmgesteuertes Objekt behandelt werden kann. So kann eine Funktion höherer Ordnung z. B. an andere Funktionen übergeben oder von anderen Funktionen zurückgegeben werden. Zu den Sprachfunktionen in C#, die Funktionen höherer Ordnung unterstützen, gehören Delegate und Lambdaausdrücke. Beim Schreiben einer Funktion höherer Ordnung deklarieren Sie für mindestens ein Argument, das diese Delegate akzeptiert, und beim Aufrufen einer solchen Funktion verwenden Sie häufig Lambdaausdrücke. Viele der Standardabfrageoperatoren sind Funktionen höherer Ordnung.

Weitere Informationen finden Sie unter [Übersicht über Standardabfrageoperatoren (C#)](./standard-query-operators-overview.md).

Lambdaausdruck \
Im Wesentlichen eine anonyme Inlinefunktion, die überall dort verwendet werden kann, wo ein Delegattyp erwartet wird. Dies ist zwar eine vereinfachte Definition für Lambdaausdrücke, im Rahmen dieses Lernprogramms reicht sie aber aus.

Weitere Informationen dazu finden Sie unter [Lambdaausdrücke](../../../language-reference/operators/lambda-expressions.md).

Sammlung \
Strukturierter Satz von Daten, die in der Regel alle denselben Typ haben. Zur Gewährleistung der Kompatibilität mit LINQ muss eine Auflistung die <xref:System.Collections.IEnumerable>-Schnittstelle oder die <xref:System.Linq.IQueryable>-Schnittstelle (oder eines ihrer generischen Gegenstücke, <xref:System.Collections.Generic.IEnumerator%601> bzw. <xref:System.Linq.IQueryable%601>) implementieren.

Tupel (anonyme Typen) \
Begriff aus der Mathematik, der eine endliche Abfolge von Objekten bezeichnet, die jeweils einen bestimmten Typ haben. Ein Tupel wird auch als geordnete Zusammenstellung bezeichnet. Dieses Konzept ist in Programmiersprachen als anonymer Typ implementiert, der es ermöglicht, einen nicht benannten Klassentyp zu deklarieren und gleichzeitig ein Objekt desselben Typs zu instanziieren.

Weitere Informationen finden Sie unter [Anonyme Typen](../../classes-and-structs/anonymous-types.md).

Typrückschluss (implizite Typisierung) \
Fähigkeit eines Compilers, den Typ einer Variablen in Abwesenheit einer expliziten Typdeklaration zu bestimmen.

Weitere Informationen zu finden Sie unter [Implizit typisierte lokale Variablen](../../classes-and-structs/implicitly-typed-local-variables.md).

Verzögerte Ausführung und verzögerte Auswertung \
Bei der verzögerten Auswertung (Lazy Evaluation) eines Ausdrucks wird mit der Auswertung so lange gewartet, bis der aufgelöste Wert tatsächlich benötigt wird. Die verzögerte Ausführung (Deferred Execution) wird in Auflistungen unterstützt.

Weitere Informationen finden Sie unter [Einführung in LINQ-Abfragen (C#)](./introduction-to-linq-queries.md) und [Deferred Execution and Lazy Evaluation in LINQ to XML (C#) (Verzögerte Ausführung und Auswertung in LINQ to XML (C#))](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).

Diese Sprachfunktionen werden in Codebeispielen im gesamten Abschnitt verwendet.

## <a name="see-also"></a>Siehe auch

- [Introduction to Pure Functional Transformations (C#) (Einführung in reine funktionale Transformationen (c#))](./introduction-to-pure-functional-transformations.md)
- [Funktionale Programmierung und Imperative Programmierung (C#)](./functional-programming-vs-imperative-programming.md)
