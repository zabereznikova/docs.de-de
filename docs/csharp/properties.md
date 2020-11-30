---
title: Eigenschaften
description: Erfahren Sie mehr über C#-Eigenschaften, die Funktionen für die Validierung, berechnete Werte, die verzögerte Auswertung und Benachrichtigungen für Eigenschaftsänderungen umfassen.
ms.technology: csharp-fundamentals
ms.date: 04/25/2018
ms.openlocfilehash: 28050a77e1f7b0ac148bba6112aa79ef4d46b710
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "89358907"
---
# <a name="properties"></a>Eigenschaften

Eigenschaften sind Bürger erster Klasse in C#. Die Sprache definiert die Syntax, mit der Entwickler Code schreiben können, der genau ihre Entwurfsabsicht ausdrückt.

Eigenschaften verhalten sich wie Felder, wenn darauf zugegriffen wird.
Jedoch sind Eigenschaften im Gegensatz zu Feldern mit Accessoren implementiert, die die ausgeführten Anweisungen definieren, wenn auf eine Eigenschaft zugegriffen oder sie zugewiesen wird.

## <a name="property-syntax"></a>Eigenschaftssyntax

Die Syntax für Eigenschaften ist eine natürliche Erweiterung von Feldern. Ein Feld definiert einen Speicherort:

[!code-csharp[Person class with public fields](../../samples/snippets/csharp/properties/Person.cs#1)]

Eine Eigenschaftendefinition enthält Deklarationen für einen `get`- und `set`-Accessor, der den Wert dieser Eigenschaft abruft oder zuweist:

[!code-csharp[Person class with public properties](../../samples/snippets/csharp/properties/Person.cs#2)]

Die oben dargestellte Syntax ist die *Auto-Eigenschaft*-Syntax. Der Compiler generiert den Speicherort für das Feld, das die Eigenschaft sichert. Der Compiler implementiert außerdem den Text der `get`- und `set`-Accessoren.

In einigen Fällen müssen Sie eine Eigenschaft auf einen anderen Wert als den Standardwert für seinen Datentyp initialisieren.  C# ermöglicht dies, indem nach der schließenden Klammer für die Eigenschaft ein Wert festgelegt wird. Möglicherweise bevorzugen Sie den Anfangswert für die Eigenschaft `FirstName` als leere Zeichenfolge und nicht `null`. Sie würden dies wie unten dargestellt angeben:

[!code-csharp[Person class with properties and initializer](../../samples/snippets/csharp/properties/Person.cs#3)]

Die bestimmte Initialisierung eignet sich am besten für schreibgeschützte Eigenschaften, wie Sie später in diesem Artikel sehen werden.

Sie können den Speicher auch selbst definieren, wie unten dargestellt:

[!code-csharp[Person class with properties and backing field](../../samples/snippets/csharp/properties/Person.cs#4)]

Wenn die Implementierung einer Eigenschaft ein einzelner Ausdruck ist, können Sie *Ausdruckskörpermember* für die Getter oder Setter verwenden:

[!code-csharp[Person class with properties and expression bodied getters and setters](../../samples/snippets/csharp/properties/Person.cs#5)]

Diese vereinfachte Syntax wird in diesem Artikel immer dann verwendet, wenn es sich anbietet.

Die oben gezeigte Eigenschaftendefinition ist eine Schreib-Lese-Eigenschaft. Beachten Sie das Schlüsselwort `value` im set-Accessor. Der `set`-Accessor verfügt immer über einen einzelnen Parameter namens `value`. Der `get`-Accessor muss einen Wert zurückgeben, der in den Typ der Eigenschaft konvertiert werden kann (`string` in diesem Beispiel).

Das sind die Grundlagen der Syntax. Es gibt viele verschiedene Varianten, die eine Vielzahl von verschiedenen Entwürfen unterstützen. Lassen Sie uns diese erforschen, und lernen Sie die Syntaxoptionen für jede kennen.

## <a name="scenarios"></a>Szenarien

In den Beispielen oben wurde eine der einfachsten Fälle von Eigenschaftendefinition gezeigt: eine Schreib-Lese-Eigenschaft ohne Überprüfung. Durch das Schreiben des Codes, den Sie in den `get`- und `set`-Accessoren möchten, können Sie viele verschiedene Szenarios erstellen.

### <a name="validation"></a>Validierung

Sie können Code im `set`-Accessor schreiben, um sicherzustellen, dass die durch eine Eigenschaft dargestellten Werte immer gültig sind. Angenommen, eine Regel für die `Person`-Klasse besagt, dass der Name nicht leer sein und keinen Leerraum enthalten darf. Sie würden das wie folgt schreiben:

[!code-csharp[Validating property setters](../../samples/snippets/csharp/properties/Person.cs#6)]

Das vorausgehende Beispiel kann unter Verwendung eines `throw`-Ausdrucks als Teil der Validierung des Eigenschaftensetters vereinfacht werden:

[!code-csharp[Validating property setters](../../samples/snippets/csharp/properties/Person.cs#7)]

Das obige Beispiel erzwingt die Regel, dass der Vorname nicht leer sein und keinen Leerraum enthalten darf. Wenn ein Entwickler schreibt

```csharp
hero.FirstName = "";
```

Die Zuweisung löst eine `ArgumentException` aus. Da der set-Accessor einen void-Rückgabetyp aufweisen muss, melden Sie Fehler im set-Accessor durch Auslösen einer Ausnahme.

Sie können die gleiche Syntax auf alles andere in Ihrem Szenario erweitern, was benötigt wird. Sie können die Beziehungen zwischen unterschiedlichen Eigenschaften oder gegen externe Bedingungen überprüfen. Gültige C#-Anweisungen sind in einem Eigenschaftenaccessor gültig.

### <a name="read-only"></a>Schreibgeschützt

Bis zu diesem Zeitpunkt sind alle Eigenschaftsdefinitionen, die Sie gesehen haben Lese-/Schreibeigenschaften mit öffentlichen Accessoren. Dies sind nicht die einzige gültigen Eingabehilfen für Eigenschaften.
Sie können schreibgeschützte Eigenschaften erstellen, oder den set- und get-Accessoren verschiedene Eingabehilfen geben. Angenommen, Ihre `Person`-Klasse sollte nur die Änderung des Werts der `FirstName`-Eigenschaft von anderen Methoden in dieser Klasse ermöglichen. Sie konnten dem set-Accessor `private`-Eingabehilfen anstelle von `public` geben:

[!code-csharp[Using a private setter for a publicly readonly property](../../samples/snippets/csharp/properties/Person.cs#8)]

Nun, kann auf die `FirstName`-Eigenschaft von einem beliebigen Code zugegriffen werden, aber es kann nur von einem anderem Code in der `Person`-Klasse zugewiesen werden.

Sie können einen restriktiven Zugriffsmodifizierer zum set- oder get-Accessor hinzufügen. Jeder Zugriffsmodifizierer, den Sie auf den einzelnen Accessor platzieren, muss eingeschränkter sein als der Zugriffsmodifizierer für die Eigenschaftsdefinition. Das Obige ist zulässig, da die `FirstName`-Eigenschaft `public` ist, aber der set-Accessor ist `private`. Sie können keine `private`-Eigenschaft mit einem `public`-Accessor deklarieren. Eigenschaftendeklarationen können ebenfalls als `protected`, `internal`, `protected internal` oder sogar `private` deklariert werden.

Es ist auch zulässig, den restriktiveren Modifizierer auf dem `get`-Accessor zu platzieren. Sie verfügen z.B. über eine `public`-Eigenschaft, schränken jedoch den `get`-Accessor auf `private` ein. Dieses Szenario wird in der Praxis nur selten ausgeführt.

Sie können auch Änderungen an einer Eigenschaft beschränken, sodass sie nur in einem Konstruktor oder einem Eigenschafteninitialisierer festgelegt werden kann. Sie können die `Person`-Klasse daher wie folgt ändern:

[!code-csharp[A readonly auto implemented property](../../samples/snippets/csharp/properties/Person.cs#9)]

Diese Funktion wird am häufigsten für die Initialisierung von Auflistungen verwendet, die als schreibgeschützte Eigenschaften verfügbar gemacht werden:

```csharp
public class Measurements
{
    public ICollection<DataPoint> points { get; } = new List<DataPoint>();
}
```

### <a name="computed-properties"></a>Berechnete Eigenschaften

Eine Eigenschaft muss nicht einfach den Wert eines Memberfelds zurückgeben. Sie können Eigenschaften erstellen, die einen berechneten Wert zurückgeben. Lassen Sie uns das `Person`-Objekt so erweitern, dass es den vollständigen Namen zurückgibt, berechnet durch die Verkettung des ersten und letzten Namens:

[!code-csharp[A computed property](../../samples/snippets/csharp/properties/Person.cs#10)]

Im Beispiel oben wird das Feature [Zeichenfolgeninterpolation](./language-reference/tokens/interpolated.md) verwendet, um die formatierte Zeichenfolge für den vollständigen Namen zu erstellen.

Sie können auch einen *Ausdruckskörpermember* verwenden, was eine kompaktere Möglichkeit zum Erstellen der berechneten `FullName`-Eigenschaft darstellt:

[!code-csharp[A computed property using an expression bodied member](../../samples/snippets/csharp/properties/Person.cs#11)]

*Ausdruckskörpermember* verwenden die Syntax von *Lambdaausdrücken* zum Definieren einer Methode, die einen einzelnen Ausdruck enthält. Hier gibt dieser Ausdruck den vollständigen Namen für das Person-Objekt zurück.

### <a name="cached-evaluated-properties"></a>Zwischengespeicherte ausgewertete Eigenschaften

Sie können das Konzept einer berechneten Eigenschaft mit dem Speicher mischen und eine *zwischengespeicherte ausgewertete Eigenschaft* erstellen.  Sie können z.B. die `FullName`-Eigenschaft so aktualisieren, dass die Zeichenfolgenformatierung nur beim ersten Zugriff umgesetzt wird:

[!code-csharp[Caching the value of a computed property](../../samples/snippets/csharp/properties/Person.cs#12)]

Der obige Code enthält jedoch einen Fehler. Wenn der Code den Wert der `FirstName`- oder `LastName`-Eigenschaft aktualisiert, ist das zuvor ausgewertete `fullName`-Feld ungültig. Sie müssen die `set`-Accessoren der `FirstName`- und `LastName`-Eigenschaft aktualisieren, damit das `fullName`-Feld erneut berechnet wird:

[!code-csharp[Invalidating the cache correctly](../../samples/snippets/csharp/properties/Person.cs#13)]

Diese endgültige Version wertet die `FullName`-Eigenschaft nur bei Bedarf aus.
Wenn die zuvor berechnete Version gültig ist, wird sie verwendet. Wenn eine andere Änderung des Zustands die zuvor berechnete Version ungültig macht, wird sie neu berechnet. Entwickler, die diese Klasse verwenden, müssen die Details der Implementierung nicht kennen. Keine dieser interne Änderungen hat Einfluss auf die Verwendung des Person-Objekts. Das ist der Hauptgrund für die Verwendung von Eigenschaften, um Datenmember eines Objekts verfügbar zu machen.

### <a name="attaching-attributes-to-auto-implemented-properties"></a>Anfügen von Attributen an automatisch implementierte Eigenschaften

Ab C# 7.3 können Feldattribute an das vom Compiler generierte Unterstützungsfeld in den automatisch implementierten Eigenschaften angefügt werden. Sie sollten z.B. eine Überarbeitung der `Person`-Klasse hinzufügen, die eine eindeutige Eigenschaft des Integers `Id` hinzufügt.
Schreiben Sie die `Id`-Eigenschaft unter Verwendung einer automatisch implementierten Eigenschaft. Für Ihren Entwurf ist es jedoch nicht erforderlich, die `Id`-Eigenschaft zu speichern. Das <xref:System.NonSerializedAttribute>-Attribut kann nur an Felder, aber nicht an Eigenschaften angefügt werden. Sie können wie im folgenden Beispiel dargestellt das <xref:System.NonSerializedAttribute>-Attribut für die `Id`-Eigenschaft an das Unterstützungsfeld unter Verwendung des `field:`-Spezifizierers des Attributs anfügen:

[!code-csharp[Attaching attributes to a backing field](../../samples/snippets/csharp/properties/Person.cs#14)]

Diese Technik funktioniert für jedes beliebige Attribut, das Sie an das Unterstützungsfeld für die automatisch implementierte Eigenschaft anfügen.

### <a name="implementing-inotifypropertychanged"></a>Implementiert INotifyPropertyChanged

Ein abschließendes Szenario, in dem Sie Code in einem Eigenschaftenaccessor schreiben müssen, ist zur Unterstützung der <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle, die verwendet wird, um Clients mit Datenbindung zu benachrichtigen, dass ein Wert geändert wurde. Wenn sich der Wert einer Eigenschaft ändert, löst das Objekt das <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged?displayProperty=nameWithType>-Ereignis aus, um die Änderung anzuzeigen. Die Bibliotheken mit Datenbindung wiederum aktualisieren die auf dieser Änderung basierenden Anzeigeelemente. Der folgende Code zeigt, wie Sie `INotifyPropertyChanged` für die `FirstName`-Eigenschaft dieser Person-Klasse implementieren würden.

[!code-csharp[invalidating the cache correctly](../../samples/snippets/csharp/properties/Person.cs#15)]

Der Operator `?.` wird *bedingter NULL-Operator* genannt. Es sucht vor der Auswertung der rechten Seite des Operators nach einem NULL-Verweis. Das Endergebnis bedeutet, dass, wenn sich keine Abonnenten im `PropertyChanged`-Ereignis befinden, der Code zum Auslösen des Ereignisses nicht ausgeführt wird. Er würde eine `NullReferenceException` auslösen, ohne diese in diesem Fall zu überprüfen. Weitere Informationen finden Sie unter [`events`](events-overview.md). In diesem Beispiel wird auch der neue `nameof`-Operator verwendet, um vom Symbol des Eigenschaftennamen in die Textdarstellung zu konvertieren.
Mithilfe von `nameof` können Fehler reduziert werden, bei denen Sie den Namen der Eigenschaft falsch eingegeben haben.

Erneut ist die Implementierung von <xref:System.ComponentModel.INotifyPropertyChanged> ein Beispiel für einen Fall, in dem Sie Code in Ihren Accessoren schreiben können, um die benötigten Szenarios zu unterstützen.

## <a name="summing-up"></a>Zusammenfassung

Eigenschaften sind eine Form intelligenter Felder in einer Klasse oder einem Objekt. Außerhalb des Objekts wirken diese wie Felder in dem Objekt. Eigenschaften können jedoch mithilfe der vollständigen Palette der C#-Funktionalität implementiert werden.
Sie können Überprüfung, verschiedene Eingabehilfen, verzögerte Auswertung oder alle Anforderungen, die Ihre Szenarios benötigen, bereitstellen.
