---
title: Erweiterungsmethoden – C#-Programmierhandbuch
ms.date: 03/19/2020
helpviewer_keywords:
- methods [C#], adding to existing types
- extension methods [C#]
- methods [C#], extension
ms.assetid: 175ce3ff-9bbf-4e64-8421-faeb81a0bb51
ms.openlocfilehash: 5db2797870b6c2e1998f17f1d8e4df8aa3f95c9e
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241408"
---
# <a name="extension-methods-c-programming-guide"></a>Erweiterungsmethoden (C#-Programmierhandbuch)

Mit Erweiterungsmethoden können Sie vorhandenen Typen Methoden hinzufügen, ohne einen neuen abgeleiteten Typ zu erstellen und ohne den ursprünglichen Typ neu kompilieren oder auf andere Weise bearbeiten zu müssen. Erweiterungsmethoden sind statische Methoden, die Sie jedoch wie Instanzmethoden für den erweiterten Typ aufrufen können. Für in C#, F# und Visual Basic geschriebenen Clientcode gibt es keinen sichtbaren Unterschied zwischen dem Aufrufen einer Erweiterungsmethode und den in einem Typ definierten Methoden.

Die häufigsten Erweiterungsmethoden sind die LINQ-Standardabfrageoperatoren, die vorhandenen <xref:System.Collections.IEnumerable?displayProperty=nameWithType>- und <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>-Typen Funktionalität hinzufügen. Um die Standardabfrageoperatoren zu verwenden, müssen Sie sie zuerst mit einer `using System.Linq`-Direktive einbinden. Jeder Typ, der <xref:System.Collections.Generic.IEnumerable%601> implementiert, scheint Instanzmethoden zu haben, wie z. B. <xref:System.Linq.Enumerable.GroupBy%2A>, <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Average%2A>. Sie können diese zusätzlichen Methoden in der IntelliSense-Anweisungsvervollständigung sehen, wenn Sie nach einer Instanz eines <xref:System.Collections.Generic.IEnumerable%601>-Typs, z.B. <xref:System.Collections.Generic.List%601> oder <xref:System.Array>, "dot" eingeben.

### <a name="orderby-example"></a>OrderBy-Beispiel

Das folgende Beispiel zeigt, wie Sie die Standardabfrageoperator-Methode `OrderBy` für ein Ganzzahlarray aufrufen können. Der Ausdruck in Klammern ist ein Lambda-Ausdruck. Viele Standardabfrageoperatoren verwenden Lambda-Ausdrücke als Parameter, dies ist jedoch keine Voraussetzung für Erweiterungsmethoden. Weitere Informationen finden Sie unter [Lambdaausdrücke](../statements-expressions-operators/lambda-expressions.md).

[!code-csharp[csProgGuideExtensionMethods#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#3)]

Erweiterungsmethoden werden als statische Methoden definiert, jedoch mithilfe einer Instanzmethodensyntax aufgerufen. Ihr erster Parameter gibt an, für welchen Typ die Methode aufgerufen wird. Dem Parameter wird der [this](../../language-reference/keywords/this.md)-Modifizierer vorangestellt. Erweiterungsmethoden befinden sich nur dann im Bereich, wenn Sie den Namespace explizit mit einer `using`-Direktive in Ihren Quellcode importieren.

Im folgenden Beispiel wird eine für die <xref:System.String?displayProperty=nameWithType>-Klasse definierte Erweiterungsmethode veranschaulicht. Die Definition erfolgt in einer nicht geschachtelten, nicht generischen statischen Klasse:

[!code-csharp[csProgGuideExtensionMethods#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#4)]

Die `WordCount`-Erweiterungsmethode kann mit dieser `using`-Direktive eingebunden werden:

```csharp
using ExtensionMethods;
```

Sie kann darüber hinaus mit dieser Syntax von einer Anwendung aufgerufen werden:

```csharp
string s = "Hello Extension Methods";
int i = s.WordCount();
```

Sie rufen die Erweiterungsmethode im Code mit Instanzmethodensyntax auf. Die vom Compiler erstellte Intermediate Language (IL) übersetzt Ihren Code in einen Aufruf der statischen Methode. Es wird nicht wirklich gegen das Prinzip der Kapselung verstoßen. Erweiterungsmethoden können nicht auf private Variablen im Typ zugreifen, den sie erweitern.

Weitere Informationen finden Sie unter [Vorgehensweise: Implementieren und Aufrufen einer benutzerdefinierten Erweiterungsmethode](./how-to-implement-and-call-a-custom-extension-method.md).

Im Allgemeinen rufen Sie vermutlich sehr viel häufiger Erweiterungsmethoden auf, als eigene Methoden zu implementieren. Da Erweiterungsmethoden mit der Instanzmethodensyntax aufgerufen werden, sind für ihren Einsatz aus dem Clientcode keine besonderen Kenntnisse erforderlich. Um Erweiterungsmethoden für einen bestimmten Typ zu aktivieren, fügen Sie eine `using`-Direktive für den Namespace, in dem die Methoden definiert werden, hinzu. Um beispielsweise die Standardabfrageoperatoren zu verwenden, fügen Sie diese `using`-Direktive dem Code hinzu:

```csharp
using System.Linq;
```

(Möglicherweise müssen Sie auch einen Verweis auf System.Core.dll hinzufügen.) Wie Sie sehen, werden die Standardabfrageoperatoren in IntelliSense jetzt für die meisten <xref:System.Collections.Generic.IEnumerable%601>-Typen als zusätzliche Methoden angezeigt.

## <a name="binding-extension-methods-at-compile-time"></a>Binden von Erweiterungsmethoden während der Kompilierung

Sie können Erweiterungsmethoden verwenden, um eine Klasse oder eine Schnittstelle zu erweitern, jedoch nicht, um sie zu überschreiben. Eine Erweiterungsmethode mit dem gleichen Namen und der gleichen Signatur wie eine Schnittstellen- oder Klassenmethode wird nie aufgerufen. Bei der Kompilierung verfügen Erweiterungsmethoden immer über niedrigere Priorität als im Typ selbst definierte Instanzmethoden. Das heißt, wenn ein Typ eine Methode mit dem Namen `Process(int i)` hat und Sie über eine Erweiterungsmethode mit der gleichen Signatur verfügen, stellt der Compiler immer eine Bindung mit der Instanzmethode her. Wenn der Compiler einen Methodenaufruf erkennt, sucht er zuerst nach einer Entsprechung in den Instanzmethoden des Typs. Wenn keine Entsprechung gefunden wird, sucht er nach Erweiterungsmethoden, die für den Typ definiert wurden, und stellt eine Bindung mit der ersten gefundenen Erweiterungsmethode her. Im folgenden Beispiel wird veranschaulicht, wie der Compiler bestimmt, mit welcher Erweiterungsmethode oder Instanzmethode die Bindung erfolgen soll.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Regeln, denen der C#-Compiler folgt, um zu bestimmen, ob ein Methodenaufruf an eine Instanzmethode für den Typ oder an eine Erweiterungsmethode gebunden werden soll. Die statische Klasse `Extensions` enthält Erweiterungsmethoden, die für jeden Typ definiert wurden, der `IMyInterface` implementiert. Die Klassen `A`, `B` und `C` implementieren alle die Schnittstelle.

Die `MethodB`-Erweiterungsmethode wird nie aufgerufen, da ihr Name und die Signatur genau mit Methoden übereinstimmen, die bereits von den Klassen implementiert wurden.

Wenn der Compiler keine Instanzmethode mit einer entsprechenden Signatur findet, stellt er eine Bindung mit einer entsprechenden Erweiterungsmethode her (sofern vorhanden).

[!code-csharp[csProgGuideExtensionMethods#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#5)]

## <a name="common-usage-patterns"></a>Gängige Verwendungsmuster

### <a name="collection-functionality"></a>Auflistungsfunktionen

In der Vergangenheit war es üblich, „Sammlungsklassen“ zu erstellen, mit denen die <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>-Schnittstelle für einen bestimmten Typ implementiert und Funktionalität für Sammlungen dieses Typs bereitgestellt wurde. Es ist zwar nichts Falsches daran, diese Art von Sammlungsobjekten zu erstellen, aber die gleiche Funktionalität kann durch eine Erweiterung von <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> erreicht werden. Erweiterungen haben den Vorteil, dass die Funktionalität aus einer beliebigen Sammlung – z. B. <xref:System.Array?displayProperty=nameWithType> oder <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> – aufgerufen werden kann, die <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> für diesen Typ implementiert. Ein entsprechendes Beispiel mit Verwendung eines Int32-Arrays finden Sie [weiter oben in diesem Artikel](#orderby-example).

### <a name="layer-specific-functionality"></a>Ebenenspezifische Funktionalität

Bei Verwendung einer Zwiebelarchitektur oder eines anderen geschichteten Anwendungsdesigns ist es üblich, einen Satz mit Domänenentitäten oder Datenübertragungsobjekten für die Kommunikation über Anwendungsgrenzen hinweg zu verwenden. Diese Objekte umfassen in der Regel keine oder nur minimale Funktionalität, die für alle Ebenen der Anwendung gilt. Erweiterungsmethoden können verwendet werden, um Funktionalität hinzuzufügen, die für jede Anwendungsschicht spezifisch ist, ohne das Objekt mit Methoden zu überladen, die in anderen Ebenen nicht benötigt werden oder unerwünscht sind.

```aspx-csharp
public class DomainEntity
{
    public int Id { get; set; }
    public string FirstName { get; set; }
    public string LastName { get; set; }
}

static class DomainEntityExtensions
{
    static string FullName(this DomainEntity value)
        => $"{value.FirstName} {value.LastName}";
}
```

### <a name="extending-predefined-types"></a>Erweiterung von vordefinierten Typen

Wenn wiederverwendbare Funktionalität erstellt werden muss, kann statt der Erstellung neuer Objekte häufig ein bereits vorhandener Typ erweitert werden, z. B. ein .NET- oder CLR-Typ. Wenn beispielsweise keine Erweiterungsmethoden verwendet werden, könnten wir eine `Engine`- oder `Query`-Klasse zum Ausführen einer Abfrage auf einer SQL Server-Instanz erstellen, die über mehrere Stellen in unserem Code aufgerufen werden kann. Stattdessen können wir jedoch die Klasse <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> mithilfe von Erweiterungsmethoden erweitern, damit diese Abfrage von jedem beliebigen Ort ausgeführt werden kann, an dem eine Verbindung mit einer SQL Server-Instanz vorhanden ist. Weitere Beispiele wären das Hinzufügen gemeinsamer Funktionalität zur Klasse <xref:System.String?displayProperty=nameWithType>, eine Erweiterung der Datenverarbeitungsfunktionalität der Objekte <xref:System.IO.File?displayProperty=nameWithType> und <xref:System.IO.Stream?displayProperty=nameWithType> sowie <xref:System.Exception?displayProperty=nameWithType>-Objekte für eine spezifische Fehlerbehandlungsfunktionalität. Der Verwendung dieser Anwendungsfälle sind praktisch keine Grenzen gesetzt.

Das Erweitern vordefinierter Typen kann bei `struct`-Typen schwierig sein, da sie als Wert an Methoden übergeben werden. Dies bedeutet, dass alle Änderungen an der Struktur an einer Kopie der Struktur vorgenommen werden. Diese Änderungen sind nicht sichtbar, nachdem die Erweiterungsmethode beendet wurde. Ab C# 7.2 können Sie dem ersten Argument einer Erweiterungsmethode den `ref`-Modifizierer hinzufügen. Durch das Hinzufügen des `ref`-Modifizierers wird das erste Argument als Verweis übergeben. Auf diese Weise können Sie Erweiterungsmethoden schreiben, die den Status der erweiterten Struktur ändern.

## <a name="general-guidelines"></a>Allgemeine Richtlinien

Wenngleich es weiterhin vorzuziehen ist, Funktionalität durch Änderung des Codes eines Objekts oder durch Ableitung eines neuen Typs hinzuzufügen – sofern dies sinnvoll und möglich ist –, sind Erweiterungsmethoden zu einer wichtigen Option zum Bereitstellen wiederverwendbarer Funktionalität im gesamten .NET-Ökosystem geworden. In Fällen, in denen die ursprüngliche Quelle nicht Ihrer Kontrolle unterliegt, ein abgeleitetes Objekt ungeeignet ist oder nicht verwendet werden kann oder die Funktionalität nicht über den anwendbaren Bereich hinaus offengelegt werden soll, stellen Erweiterungsmethoden eine ausgezeichnete Wahl dar.

Weitere Informationen zu abgeleiteten Typen finden Sie unter [Vererbung](./inheritance.md).

Wenn Sie eine Erweiterungsmethode zum Erweitern eines Typs verwenden, dessen Quellcode Sie nicht ändern können, laufen Sie Gefahr, dass eine Änderung an der Implementierung des Typs zu einer Beschädigung Ihrer Erweiterungsmethode führt.

Wenn Sie Erweiterungsmethoden für einen gegebenen Typ implementieren, beachten Sie die folgenden Punkte:

- Eine Erweiterungsmethode wird nie aufgerufen, wenn sie die gleiche Signatur wie eine im Typ definierte Methode hat.
- Erweiterungsmethoden werden auf Namespace-Ebene eingebunden. Wenn Sie z. B. über mehrere statische Klassen verfügen, die Erweiterungsmethoden in einem einzelnen Namespace mit dem Namen `Extensions` enthalten, werden sie alle mit der `using Extensions;`-Direktive eingebunden.

Für eine Klassenbibliothek, die Sie implementiert haben, sollten Sie keine Erweiterungsmethoden verwenden, um zu vermeiden, dass die Versionsnummer einer Assembly erhöht wird. Wenn Sie zu einer Bibliothek, deren Quellcode Sie besitzen, wichtige Funktionalität hinzufügen möchten, befolgen Sie die .NET-Richtlinien für Assemblyversionierung. Weitere Informationen dazu finden Sie unter [Assemblyversionen](../../../standard/assembly/versioning.md).

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Parallel Programming Samples (Beispiele für parallele Programmierung (dazu gehören viele Beispielerweiterungsmethoden))](/samples/browse/?products=dotnet-core%2Cdotnet-standard&term=parallel)
- [Lambda-Ausdrücke](../statements-expressions-operators/lambda-expressions.md)
- [Übersicht über Standardabfrageoperatoren](../concepts/linq/standard-query-operators-overview.md)
- [Conversion rules for Instance parameters and their impact (Konvertierungsregeln für Instanzenparameter und ihre Auswirkungen)](https://docs.microsoft.com/archive/blogs/sreekarc/conversion-rules-for-instance-parameters-and-their-impact)
- [Extension methods Interoperability between languages (Erweiterungsmethoden-Interoperabilität zwischen Sprachen)](https://docs.microsoft.com/archive/blogs/sreekarc/extension-methods-interoperability-between-languages)
- [Extension methods and Curried Delegates (Erweiterungsmethoden und Curry-Delegaten)](https://docs.microsoft.com/archive/blogs/sreekarc/extension-methods-and-curried-delegates)
- [Extension method Binding and Error reporting (Binden von Erweiterungsmethoden und Problemberichten)](https://docs.microsoft.com/archive/blogs/sreekarc/extension-method-binding-and-error-reporting)
