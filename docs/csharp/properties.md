---
title: Eigenschaften
description: Eigenschaften
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 6950d25a-bba1-4744-b7c7-a3cc90438c55
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 871beb36f9801a0456eec1501fdbf07375c9b418
ms.lasthandoff: 03/13/2017

---

# <a name="properties"></a>Eigenschaften

Eigenschaften sind Bürger erster Klasse in C#. Die Sprache definiert die Syntax, mit der Entwickler Code schreiben können, der genau ihre Entwurfsabsicht ausdrückt.

Eigenschaften verhalten sich wie Felder, wenn darauf zugegriffen wird.
Jedoch sind Eigenschaften im Gegensatz zu Feldern mit Accessoren implementiert, die die ausgeführten Anweisungen definieren, wenn auf eine Eigenschaft zugegriffen oder sie zugewiesen wird.

## <a name="property-syntax"></a>Eigenschaftssyntax
Die Syntax für Eigenschaften ist eine natürliche Erweiterung von Feldern. Ein Feld definiert einen Speicherort:

```csharp
public class Person
{
    public string FirstName;
    // remaining implementation removed from listing
}
```

Eine Eigenschaftendefinition enthält Deklarationen für einen `get`- und `set`-Accessor, der den Wert dieser Eigenschaft abruft oder zuweist:

```csharp
public class Person
{
    public string FirstName
    {
        get;
        set;
    }
    // remaining implementation removed from listing
}
```

Die oben dargestellte Syntax ist die *Auto-Eigenschaft*-Syntax. Der Compiler generiert den Speicherort für das Feld, das die Eigenschaft sichert. Der Compiler implementiert außerdem den Text der `get`- und `set`-Accessoren.
Sie können den Speicher auch selbst definieren, wie unten dargestellt:

```csharp
public class Person
{
    public string FirstName
    {
        get { return firstName; }
        set { firstName = value; }
    }
    private string firstName;
    // remaining implementation removed from listing
}
```
 
Die oben gezeigte Eigenschaftendefinition ist eine Schreib-Lese-Eigenschaft. Beachten Sie das Schlüsselwort `value` im set-Accessor. Der `set`-Accessor verfügt immer über einen einzelnen Parameter namens `value`. Der `get`-Accessor muss einen Wert zurückgeben, der in den Typ der Eigenschaft konvertiert werden kann (`string` in diesem Beispiel).
 
Das sind die Grundlagen der Syntax. Es gibt viele verschiedene Varianten, die eine Vielzahl von verschiedenen Entwürfen unterstützen. Lassen Sie uns diese erforschen, und lernen Sie die Syntaxoptionen für jede kennen. 

## <a name="scenarios"></a>Szenarien

In den Beispielen oben wurde eine der einfachsten Fälle von Eigenschaftendefinition gezeigt: eine Schreib-Lese-Eigenschaft ohne Überprüfung. Durch das Schreiben des Codes, den Sie in den `get`- und `set`-Accessoren möchten, können Sie viele verschiedene Szenarios erstellen.  

### <a name="validation"></a>Validierung

Sie können Code im `set`-Accessor schreiben, um sicherzustellen, dass die durch eine Eigenschaft dargestellten Werte immer gültig sind. Angenommen, eine Regel für die `Person`-Klasse ist z.B., dass der Name nicht leer oder kein Leerzeichen sein kann. Sie würden das wie folgt schreiben:

```csharp
public class Person
{
    public string FirstName
    {
        get { return firstName; }
        set
        {
            if (string.IsNullOrWhiteSpace(value))
                throw new ArgumentException("First name must not be blank");
            firstName = value;
        }
    }
    private string firstName;
    // remaining implementation removed from listing
}
```

Das obige Beispiel erzwingt die Regel, dass der erste Name nicht leer oder kein Leerzeichen sein darf. Wenn ein Entwickler schreibt
```csharp
hero.FirstName = "";
```
Die Zuweisung löst eine `ArgumentException` aus. Da der set-Accessor einen void-Rückgabetyp aufweisen muss, melden Sie Fehler im set-Accessor durch Auslösen einer Ausnahme.

Das ist ein einfacher Fall der Überprüfung. Sie können die gleiche Syntax auf alles andere in Ihrem Szenario erweitern, was benötigt wird. Sie können die Beziehungen zwischen unterschiedlichen Eigenschaften oder gegen externe Bedingungen überprüfen. Gültige C#-Anweisungen sind in einem Eigenschaftenaccessor gültig.

### <a name="read-only"></a>Schreibgeschützt

Bis zu diesem Zeitpunkt sind alle Eigenschaftsdefinitionen, die Sie gesehen haben Lese-/Schreibeigenschaften mit öffentlichen Accessoren. Dies sind nicht die einzige gültigen Eingabehilfen für Eigenschaften.
Sie können schreibgeschützte Eigenschaften erstellen, oder den set- und get-Accessoren verschiedene Eingabehilfen geben. Angenommen, Ihre `Person`-Klasse sollte nur die Änderung des Werts der `FirstName`-Eigenschaft von anderen Methoden in dieser Klasse ermöglichen. Sie konnten dem set-Accessor `private`-Eingabehilfen anstelle von `public` geben:

```csharp
public class Person
{
    public string FirstName
    {
        get;
        private set;
    }
    // remaining implementation removed from listing
}
```

Nun, kann auf die `FirstName`-Eigenschaft von einem beliebigen Code zugegriffen werden, aber es kann nur von einem anderem Code in der `Person`-Klasse zugewiesen werden.
Sie können einen restriktiven Zugriffsmodifizierer zum set- oder get-Accessor hinzufügen. Jeder Zugriffsmodifizierer, den Sie auf den einzelnen Accessor platzieren, muss eingeschränkter sein als der Zugriffsmodifizierer für die Eigenschaftsdefinition. Das Obige ist zulässig, da die `FirstName`-Eigenschaft `public` ist, aber der set-Accessor ist `private`. Sie können keine `private`-Eigenschaft mit einem `public`-Accessor deklarieren. Eigenschaftendeklarationen können ebenfalls als `protected`, `internal`, `protected internal` oder sogar `private` deklariert werden.   

Es ist auch zulässig, den restriktiveren Modifizierer auf dem `get`-Accessor zu platzieren. Sie verfügen z.B. über eine `public`-Eigenschaft, schränken jedoch den `get`-Accessor auf `private` ein. Dieses Szenario wird in der Praxis nur selten ausgeführt.
 
### <a name="computed-properties"></a>Berechnete Eigenschaften

Eine Eigenschaft muss nicht einfach den Wert eines Memberfelds zurückgeben. Sie können Eigenschaften erstellen, die einen berechneten Wert zurückgeben. Lassen Sie uns das `Person`-Objekt so erweitern, dass es den vollständigen Namen zurückgibt, berechnet durch die Verkettung des ersten und letzten Namens:

```csharp
public class Person
{
    public string FirstName
    {
        get;
        set;
    }

    public string LastName
    {
        get;
        set;
    }

    public string FullName
    {
        get
        {
            return $"{FirstName} {LastName}";
        }
    }
}
```

Im Beispiel oben wird die Syntax *Zeichenfolgeninterpolation* verwendet, um die formatierte Zeichenfolge für den vollständigen Namen zu erstellen.

Sie können auch *Ausdruckskörpermember* verwenden, das eine kompaktere Möglichkeit zum Erstellen der berechneten `FullName`-Eigenschaft bietet:

```csharp
public class Person
{
    public string FirstName
    {
        get;
        set;
    }

    public string LastName
    {
        get;
        set;
    }

    public string FullName =>  $"{FirstName} {LastName}";
}
```
 
*Ausdruckskörpermember* verwenden die Syntax *Lambda-Ausdruck* zum Definieren einer Methode, die einen einzelnen Ausdruck enthält. Hier gibt dieser Ausdruck den vollständigen Namen für das Person-Objekt zurück.

### <a name="lazy-evaluated-properties"></a>Verzögert ausgewertete Eigenschaften

Sie können das Konzept einer berechneten Eigenschaft mit dem Speicher mischen und eine *verzögert ausgewertete Eigenschaft* erstellen.  Sie können z.B. die `FullName`-Eigenschaft so aktualisieren, dass die Zeichenfolgenformatierung nur beim ersten Zugriff umgesetzt wird:

```csharp
public class Person
{
    public string FirstName
    {
        get;
        set;
    }

    public string LastName
    {
        get;
        set;
    }

    private string fullName;
    public string FullName
    {
        get
        {
            if (fullName == null)
                fullName = $"{FirstName} {LastName}";
            return fullName;
        }
    }
}
```

Der obige Code enthält jedoch einen Fehler. Wenn der Code den Wert der `FirstName`- oder `LastName`-Eigenschaft aktualisiert, ist das zuvor ausgewertete `fullName`-Feld ungültig. Sie müssen die `set`-Accessoren der `FirstName`- und `LastName`-Eigenschaft aktualisieren, damit das `fullName`-Feld erneut berechnet wird:

```csharp
public class Person
{
    private string firstName;
    public string FirstName
    {
        get { return firstName; }
        set
        {
            firstName = value;
            fullName = null;
        }
    }

    private string lastName;
    public string LastName
    {
        get { return lastName; }
        set
        {
            lastName = value;
            fullName = null;
        }
    }

    private string fullName;
    public string FullName
    {
        get
        {
            if (fullName == null)
                fullName = $"{FirstName} {LastName}";
            return fullName;
        }
    }
}
```

Diese endgültige Version wertet die `FullName`-Eigenschaft nur bei Bedarf aus.
Wenn die zuvor berechnete Version gültig ist, wird sie verwendet. Wenn eine andere Änderung des Zustands die zuvor berechnete Version ungültig macht, wird sie neu berechnet. Entwickler, die diese Klasse verwenden, müssen die Details der Implementierung nicht kennen. Keine dieser interne Änderungen hat Einfluss auf die Verwendung des Person-Objekts. Das ist der Hauptgrund für die Verwendung von Eigenschaften, um Datenmember eines Objekts verfügbar zu machen. 
 
### <a name="inotifypropertychanged"></a>INotifyPropertyChanged

Ein abschließendes Szenario, in dem Sie Code in einem Eigenschaftenaccessor schreiben müssen, ist zur Unterstützung der `INotifyPropertyChanged`-Schnittstelle, die verwendet wird, um Clients mit Datenbindung zu benachrichtigen, dass ein Wert geändert wurde. Wenn sich der Wert einer Eigenschaft ändert, löst das Objekt das `PropertyChanged`-Ereignis aus, um die Änderung anzuzeigen. Die Bibliotheken mit Datenbindung wiederum aktualisieren die auf dieser Änderung basierenden Anzeigeelemente. Der folgende Code zeigt, wie Sie `INotifyPropertyChanged` für die `FirstName`-Eigenschaft dieser Person-Klasse implementieren würden.

```csharp
public class Person : INotifyPropertyChanged
{
    public string FirstName
    {
        get { return firstName; }
        set
        {
            if (string.IsNullOrWhiteSpace(value))
                throw new ArgumentException("First name must not be blank");
            if (value != firstName)
            {
                PropertyChanged?.Invoke(this, 
                    new PropertyChangedEventArgs(nameof(FirstName)));
            }
            firstName = value;
        }
    }
    private string firstName;

    public event PropertyChangedEventHandler PropertyChanged;
    // remaining implementation removed from listing
}
```

Der Operator `?.` wird *bedingter NULL-Operator* genannt. Es sucht vor der Auswertung der rechten Seite des Operators nach einem NULL-Verweis. Das Endergebnis bedeutet, dass, wenn sich keine Abonnenten im `PropertyChanged`-Ereignis befinden, der Code zum Auslösen des Ereignisses nicht ausgeführt wird. Er würde eine `NullReferenceException` auslösen, ohne diese in diesem Fall zu überprüfen. Weitere Informationen finden Sie auf der Seite [`events`](delegates-events.md). In diesem Beispiel wird auch der neue `nameof`-Operator verwendet, um vom Symbol des Eigenschaftennamen in die Textdarstellung zu konvertieren.
Mithilfe von `nameof` können Fehler reduziert werden, bei denen Sie den Namen der Eigenschaft falsch eingegeben haben.

Erneut ist dies ein Beispiel für einen Fall, in dem Sie Code in Ihren Accessoren schreiben können, um die benötigten Szenarios zu unterstützen.

## <a name="summing-up"></a>Schlussbemerkung 

Eigenschaften sind eine Form intelligenter Felder in einer Klasse oder einem Objekt. Außerhalb des Objekts wirken diese wie Felder in dem Objekt. Eigenschaften können jedoch mithilfe der vollständigen Palette der C#-Funktionalität implementiert werden.
Sie können Überprüfung, verschiedene Eingabehilfen, verzögerte Auswertung oder alle Anforderungen, die Ihre Szenarios benötigen, bereitstellen.

