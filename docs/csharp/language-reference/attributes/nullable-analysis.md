---
title: 'Reservierte C#-Attribute: Statische Analysen, die NULL-Werte zulassen'
ms.date: 04/14/2020
description: Diese Attribute werden vom Compiler interpretiert, um eine bessere statische Analyse für Nullable- und Non-Nullable-Verweistypen zu liefern.
ms.openlocfilehash: d2405162ece3df209111de65fdef54f70cc86d45
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656306"
---
# <a name="reserved-attributes-contribute-to-the-compilers-null-state-static-analysis"></a>Reservierte Attribute zur Unterstützung der statischen NULL-Zustandsanalyse des Compilers

In einem Nullable-Kontext führt der Compiler eine statische Analyse des Codes durch, um den NULL-Zustand aller Verweistypvariablen zu bestimmen:

- *Nicht NULL*: Die statische Analyse hat ergeben, dass die Variable einem Nicht-NULL-Wert zugewiesen ist.
- *Möglicherweise NULL*: Die statische Analyse kann nicht bestimmen, ob einer Variable ein Nicht-NULL-Wert zugewiesen ist.

Sie können verschiedene Attribute anwenden, die dem Compiler Informationen zur Semantik Ihrer APIs liefern. Diese Informationen unterstützen den Compiler dabei, eine statische Analyse durchzuführen und zu bestimmen, wann eine Variable ungleich NULL ist. Im vorliegenden Artikel werden jedes dieser Attribute und seine Verwendung kurz beschrieben. Alle Beispiele gehen von C# 8.0 oder höher aus, und der Code steht in einem Nullable-Kontext.

Beginnen wir mit einem bekannten Beispiel. Angenommen, Ihre Bibliothek verfügt über die folgende API zum Abrufen einer Ressourcenzeichenfolge:

```csharp
bool TryGetMessage(string key, out string message)
```

Das vorstehende Beispiel folgt dem bekannten `Try*`-Muster in .NET. Es sind zwei Verweisargumente für diese API vorhanden: die Parameter `key` und `message`. Diese API umfasst die folgenden Regeln in Bezug auf die NULL-Zulässigkeit dieser Argumente:

- Aufrufer dürfen nicht `null` als Argument für `key` übergeben.
- Aufrufer können eine Variable übergeben, deren Wert `null` als Argument für `message` lautet.
- Wenn die Methode `TryGetMessage` den Wert `true` zurückgibt, ist der Wert von `message` ungleich NULL. Wenn der Rückgabewert `false,` lautet, ist der Wert von `message` (und der zugehörige NULL-Zustand) NULL.

Die Regel für `key` kann durch den Variablentyp ausgedrückt werden: `key` muss ein Non-Nullable-Verweistyp sein. Der Parameter `message` ist komplexer. Er lässt `null` als Argument zu, aber garantiert bei einem erfolgreichen Vorgang, dass das `out`-Argument nicht NULL ist. Für diese Szenarien ist ein umfangreicheres Vokabular zum Beschreiben der Erwartungen erforderlich.

Es wurden mehrere Attribute hinzugefügt, um zusätzliche Informationen über den NULL-Zustand von Variablen auszudrücken. In jeglichem Code, der vor C# 8.0 und der Einführung von Nullable-Verweistypen geschrieben wurde, wurden *NULL-Werte nicht beachtet*. Dies bedeutet, dass eine Verweistypvariable NULL sein konnte, aber NULL-Überprüfungen nicht erforderlich waren. Sobald Ihr Code *Nullable-fähig* ist, ändern sich diese Regeln. Verweistypen dürfen nie den Wert `null` aufweisen, und Nullable-Verweistypen müssen auf `null` überprüft werden, bevor sie dereferenziert werden können.

Die Regeln für Ihre APIs sind wahrscheinlich komplizierter, wie im `TryGetValue`-API-Szenario deutlich geworden ist. Viele Ihrer APIs umfassen komplexere Regeln in Bezug darauf, wann Variablen den Wert `null` annehmen können oder nicht. In diesen Fällen verwenden Sie eines der folgenden Attribute zum Ausdrücken dieser Regeln:

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): Ein Non-Nullable-Eingabeargument darf NULL sein.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): Ein Nullable-Eingabeargument darf nie NULL sein.
- [MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): Ein Non-Nullable-Rückgabewert darf NULL sein.
- [NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): Ein Nullable-Rückgabetyp ist niemals NULL.
- [MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): Ein Non-Nullable-Eingabeargument darf NULL sein, wenn die Methode den angegebenen `bool`-Wert zurückgibt.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): Ein Nullable-Eingabeargument ist nicht NULL, wenn die Methode den angegebenen `bool`-Wert zurückgibt.
- [NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): Ein Rückgabewert ist nicht NULL, wenn das Argument für den angegebenen Parameter nicht NULL ist.
- [DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute): Die Methode gibt niemals ein Ergebnis zurück. Anders ausgedrückt: Die Methode löst immer eine Ausnahme aus.
- [DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): Die Methode gibt niemals ein Ergebnis zurück, wenn der zugeordnete Parameter `bool` einen angegebenen Wert aufweist.

Die vorherigen Beschreibungen sind eine kurze Referenz zur Funktionsweise jedes Attributs. In den folgenden Abschnitten werden das Verhalten und die Bedeutung der Attribute näher beschrieben.

Durch das Hinzufügen dieser Attribute erhält der Compiler mehr Informationen über die Regeln für Ihre API. Wenn Aufrufcode in einem Nullable-aktivierten Kontext kompiliert wird, warnt der Compiler Aufrufer, wenn sie diese Regeln verletzen. Diese Attribute aktivieren keine zusätzlichen Überprüfungen für Ihre Implementierung.

## <a name="specify-preconditions-allownull-and-disallownull"></a>Angeben von Vorbedingungen: `AllowNull` und `DisallowNull`

Betrachten Sie eine Eigenschaft mit Lese-/Schreibzugriff, die niemals `null` zurückgibt, weil sie einen angemessen Standardwert aufweist. Aufrufer übergeben `null` an die set-Zugriffsmethode, wenn diese auf den Standardwert festgelegt wird. Denken Sie zum Beispiel an ein Messagingsystem, das in einem Livechat nach einem Benutzernamen fragt. Wenn kein Name angegeben wird, erzeugt das System einen zufälligen Namen:

```csharp
public string ScreenName
{
   get => _screenName;
   set => _screenName = value ?? GenerateRandomScreenName();
}
private string _screenName;
```

Wenn Sie den vorstehenden Code in einem Kontext ohne Nullable-Beachtung kompilieren, ist alles in Ordnung. Sobald Sie Nullable-Verweistypen aktivieren, wird die `ScreenName`-Eigenschaft zu einem Non-Nullable-Verweis. Dies ist für die `get`-Zugriffsmethode korrekt: sie gibt nie `null` zurück. Aufrufer müssen die zurückgegebene Eigenschaft für `null` nicht überprüfen. Aber bei Festlegung der Eigenschaft auf `null` wird jetzt eine Warnung generiert. Um diese Art von Code weiterhin zu unterstützen, fügen Sie der Eigenschaft das Attribut <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute?displayProperty=nameWithType> hinzu, wie im folgenden Code gezeigt:

```csharp
[AllowNull]
public string ScreenName
{
   get => _screenName;
   set => _screenName = value ?? GenerateRandomScreenName();
}
private string _screenName = GenerateRandomScreenName();
```

Sie müssen möglicherweise eine `using`-Direktive für <xref:System.Diagnostics.CodeAnalysis> hinzufügen, um diese und weitere Attribute zu verwenden, die in diesem Artikel besprochen werden. Das Attribut wird auf die Eigenschaft angewendet, nicht auf die `set`-Zugriffsmethode. Das `AllowNull`-Attribut gibt *Vorbedingungen* an und wird nur auf Eingaben angewendet. Die `get`-Zugriffsmethode umfasst einen Rückgabewert, aber keine Eingabeargumente. Deshalb gilt das `AllowNull`-Attribut nur für die `set`-Zugriffsmethode.

Das vorangehende Beispiel veranschaulicht, wonach beim Hinzufügen des `AllowNull`-Attributs für ein Argument gesucht werden muss:

1. Der allgemeine Vertrag für diese Variable sieht vor, dass sie nicht `null` sein darf, deshalb wird ein Non-Nullable-Verweistyp benötigt.
1. Es gibt Szenarien, in denen die Eingabevariable den Wert `null` annimmt, obwohl dies nicht häufig der Fall ist.

In den meisten Fällen verwenden Sie dieses Attribut für Eigenschaften oder `in`-, `out`- und `ref`-Argumente. Das `AllowNull`-Attribut stellt die beste Wahl dar, wenn eine Variable typischerweise ungleich NULL ist, Sie aber `null` als Vorbedingung zulassen müssen.

Vergleichen Sie dies mit Szenarien für die Verwendung von `DisallowNull`: Mit diesem Attribut legen Sie fest, dass eine Eingabevariable eines Nullable-Verweistyps nicht `null` sein darf. Nehmen wir als Beispiel eine Eigenschaft, bei der `null` der Standardwert ist und Clients die Eigenschaft nur auf einen Wert ungleich NULL festlegen können. Betrachten Sie folgenden Code:

```csharp
public string ReviewComment
{
    get => _comment;
    set => _comment = value ?? throw new ArgumentNullException(nameof(value), "Cannot set to null");
}
string _comment;
```

Der vorstehende Code ist der beste Weg, um in Ihrem Entwurf auszudrücken, dass `ReviewComment` den Wert `null` annehmen könnte, aber nicht auf `null` festgelegt werden kann. Sobald dieser Code Nullable-fähig ist, können Sie dieses Konzept für Aufrufer mit <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute?displayProperty=nameWithType> klarer ausdrücken:

```csharp
[DisallowNull]
public string? ReviewComment
{
    get => _comment;
    set => _comment = value ?? throw new ArgumentNullException(nameof(value), "Cannot set to null");
}
string? _comment;
```

In einem Nullable-Kontext kann die `get`-Zugriffsmethode von `ReviewComment` den Standardwert `null` zurückgeben. Der Compiler gibt eine Warnung aus, dass vor dem Zugriff eine Überprüfung erforderlich ist. Darüber hinaus werden Aufrufer gewarnt, dass der Wert `null` zwar möglich ist, Aufrufer aber den Wert `null` nicht explizit festlegen sollten. Das `DisallowNull`-Attribut gibt ebenfalls eine *Vorbedingung* an, es hat keine Auswirkung auf die `get`-Zugriffsmethode. Sie verwenden das `DisallowNull`-Attribut, wenn folgende Punkte zutreffen:

1. Die Variable könnte in wichtigen Szenarien den Wert `null` annehmen, häufig bei der ersten Instanziierung.
1. Die Variable darf nicht explizit auf `null` festgelegt werden.

Diese Situationen sind häufig in Code anzutreffen, in dem *NULL-Werte ursprünglich nicht beachtet wurden*. Es kann vorkommen, dass Objekteigenschaften in zwei unterschiedlichen Initialisierungsvorgängen festgelegt werden. Einige Eigenschaften werden nur festgelegt, nachdem einige asynchrone Vorgänge ausgeführt wurden.

Mit den Attributen `AllowNull` und `DisallowNull` können Sie festlegen, dass Vorbedingungen für Variablen nicht den Nullable-Anmerkungen für diese Variablen entsprechen dürfen. Sie liefern zusätzliche Informationen zu den Merkmalen Ihrer API. Diese zusätzlichen Informationen helfen Aufrufern, Ihre API korrekt zu verwenden. Wie bereits erwähnt, geben Sie Vorbedingungen mit den folgenden Attributen an:

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): Ein Non-Nullable-Eingabeargument darf NULL sein.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): Ein Nullable-Eingabeargument darf nie NULL sein.

## <a name="specify-post-conditions-maybenull-and-notnull"></a>Angeben von Nachbedingungen: `MaybeNull` und `NotNull`

Angenommen, Sie verfügen über eine Methode mit der folgenden Signatur:

```csharp
public Customer FindCustomer(string lastName, string firstName)
```

Sie haben wahrscheinlich schon eine Methode wie diese geschrieben, um `null` zurückzugeben, wenn ein gesuchter Name nicht gefunden wurde. Durch den Wert `null` wird klar ausgedrückt, dass der Datensatz nicht gefunden wurde. In diesem Beispiel ändern Sie den Rückgabetyp wahrscheinlich von `Customer` in `Customer?`. Durch das Deklarieren des Rückgabetyps als Nullable-Verweistyp wird die Absicht dieser API klar ausgedrückt.

Aus Gründen, die unter [Generische Definitionen und NULL-Zulässigkeit](../../nullable-migration-strategies.md#generic-definitions-and-nullability) erläutert werden, funktioniert diese Technik nicht bei generischen Methoden. Angenommen, Sie verfügen über eine generische Methode, die einem ähnlichen Muster folgt:

```csharp
public T Find<T>(IEnumerable<T> sequence, Func<T, bool> predicate)
```

Sie können nicht angeben, dass der Rückgabewert `T?` lautet. Die Methode gibt `null` zurück, wenn das gesuchte Element nicht gefunden wird. Da es nicht möglich ist, `T?` als Rückgabetyp zu deklarieren, fügen Sie die `MaybeNull`-Anmerkung zur Methodenrückgabe hinzu:

```csharp
[return: MaybeNull]
public T Find<T>(IEnumerable<T> sequence, Func<T, bool> predicate)
```

Der Code oben informiert Aufrufer darüber, dass der Vertrag einen Non-Nullable-Typ vorsieht, aber der Rückgabewert tatsächlich NULL sein *darf*.  Verwenden Sie das `MaybeNull`-Attribut, wenn Ihre API einen Non-Nullable-Typ verwenden soll – in der Regel einen generischen Typparameter –, aber in bestimmten Fällen `null` zurückgegeben werden kann.

Sie können auch angeben, dass ein Rückgabewert oder ein `out`- oder `ref`-Argument nicht NULL sein darf, obwohl der Typ ein Nullable-Verweistyp ist. Betrachten wir eine Methode, die sicherstellt, dass ein Array lang genug ist, um eine Anzahl von Elementen zu speichern. Wenn das Eingabeargument keine Kapazität aufweist, ordnet die Routine ein neues Array zu und kopiert alle vorhandenen Elemente in das Array. Wenn das Eingabeargument `null` lautet, ordnet die Routine neuen Speicher zu. Ist ausreichend Kapazität vorhanden, hat die Routine keine Auswirkungen:

```csharp
public void EnsureCapacity<T>(ref T[] storage, int size)
```

Sie können diese Routine folgendermaßen aufrufen:

```csharp
// messages has the default value (null) when EnsureCapacity is called:
EnsureCapacity<string>(ref messages, 10);
// messages is not null.
EnsureCapacity<string>(messages, 50);
```

Nach dem Aktivieren von NULL-Verweistypen möchten Sie sicherstellen, dass der vorstehende Code ohne Warnungen kompiliert wird. Wenn die Methode ein Ergebnis zurückgibt, wird garantiert, dass das `storage`-Argument ungleich NULL ist. Es ist jedoch weiterhin zulässig, `EnsureCapacity` mit einem NULL-Verweis aufzurufen. Sie können `storage` als Nullable-Verweistyp festlegen und die Nachbedingung `NotNull` zur Parameterdeklaration hinzufügen:

```csharp
public void EnsureCapacity<T>([NotNull] ref T[]? storage, int size)
```

Der vorangehende Code drückt den vorhanden Vertrag klar aus: Aufrufer können eine Variable mit dem Wert `null` übergeben, aber es wird garantiert, dass der Rückgabewert nie NULL ist. Das `NotNull`-Attribut ist besonders nützlich für `ref`- und `out`-Argumente, bei denen `null` als Argument übergeben werden kann, aber das Argument garantiert ungleich NULL ist, wenn die Methode ein Ergebnis zurückgibt.

Sie geben nicht bedingte Nachbedingungen mit den folgenden Attributen an:

- [MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): Ein Non-Nullable-Rückgabewert darf NULL sein.
- [NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): Ein Nullable-Rückgabetyp ist niemals NULL.

## <a name="specify-conditional-post-conditions-notnullwhen-maybenullwhen-and-notnullifnotnull"></a>Angeben von bedingten Nachbedingungen: `NotNullWhen`, `MaybeNullWhen` und `NotNullIfNotNull`

Ihnen ist die `string`-Methode <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType> wahrscheinlich vertraut. Diese Methode gibt `true` zurück, wenn das Argument NULL oder eine leere Zeichenfolge ist. Die Methode ist eine Form der NULL-Überprüfung: Aufrufer müssen eine NULL-Überprüfung des Arguments durchführen, wenn die Methode `false` zurückgibt. Um eine Methode wie diese NULL-fähig zu machen, legen Sie das Argument auf einen Nullable-Verweistyp fest und fügen das `NotNullWhen`-Attribut hinzu:

```csharp
bool IsNullOrEmpty([NotNullWhen(false)] string? value);
```

Auf diese Weise wird der Compiler darüber informiert, dass jeglicher Code mit Rückgabewert `false` nicht auf NULL überprüft werden muss. Durch das Hinzufügen des Attributs wird die statische Analyse des Compilers darüber informiert, dass `IsNullOrEmpty` die erforderliche NULL-Überprüfung durchführt: bei Rückgabe von `false` ist das Eingabeargument nicht `null`.

```csharp
string? userInput = GetUserInput();
if (!string.IsNullOrEmpty(userInput))
{
   int messageLength = userInput.Length; // no null check needed.
}
// null check needed on userInput here.
```

Die <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType>-Methode wird für .NET Core 3.0 wie oben gezeigt mit Anmerkungen versehen. Sie verwenden möglicherweise ähnliche Methoden in Ihrer Codebasis, die den Zustand von Objekten auf NULL-Werte überprüfen. Der Compiler erkennt keine benutzerdefinierten Methoden für die NULL-Überprüfung, und Sie müssen die Anmerkungen selbst hinzufügen. Wenn Sie das Attribut hinzufügen, hat die statische Analyse des Compilers Kenntnis darüber, wann die getestete Variable auf NULL-Werte überprüft wurde.

Eine weitere Verwendung für diese Attribute ist das `Try*`-Muster. Die Nachbedingungen für `ref`- und `out`-Variablen werden über den Rückgabewert kommuniziert. Betrachten Sie die zuvor gezeigte Methode:

```csharp
bool TryGetMessage(string key, out string message)
```

Die vorstehende Methode folgt einem typischen .NET-Idiom: Der Rückgabewert gibt an, ob `message` auf den gefunden Wert oder – falls „message“ nicht gefunden wird – auf den Standardwert festgelegt wurde. Wenn die Methode `true` zurückgibt, ist der Wert von `message` ungleich NULL. Andernfalls legt die Methode `message` auf NULL fest.

Sie können dieses Idiom mithilfe des `NotNullWhen`-Attributs kommunizieren. Wenn Sie die Signatur für Nullable-Verweistypen aktualisieren, ändern Sie `message` in `string?`, und fügen Sie ein Attribut hinzu:

```csharp
bool TryGetMessage(string key, [NotNullWhen(true)] out string? message)
```

Im vorstehenden Beispiel ist der Wert von `message` bekanntermaßen ungleich NULL, wenn `TryGetMessage` den Wert `true` zurückgibt. Sie sollten ähnliche Methoden in Ihrer Codebasis in gleicher Weise mit Anmerkungen versehen: Die Argumente könnten `null` sein und sind bekanntermaßen ungleich NULL, wenn die Methode `true` zurückgibt.

Es gibt ein letztes Attribut, das Sie möglicherweise ebenfalls benötigen. Gelegentlich hängt der NULL-Zustand eines Rückgabewerts vom NULL-Zustand von mindestens einem Eingabeargument ab. Diese Methoden geben einen Nicht-NULL-Wert zurück, wenn bestimmt Eingabeargumente nicht `null` sind. Um diese Methoden korrekt mit Anmerkungen zu versehen, verwenden Sie das `NotNullIfNotNull`-Attribut. Sehen Sie sich die folgende Methode an:

```csharp
string GetTopLevelDomainFromFullUrl(string url);
```

Wenn das `url`-Argument ungleich NULL ist, ist die Ausgabe nicht `null`. Sobald Nullable-Verweise aktiviert werden, funktioniert diese Signatur ordnungsgemäß, sofern Ihre API keine NULL-Eingabe akzeptiert. Wenn die Eingabe jedoch NULL sein darf, kann auch der Rückgabewert NULL sein. Deshalb könnten Sie die Signatur in den folgenden Code ändern:

```csharp
string? GetTopLevelDomainFromFullUrl(string? url);
```

Dies funktioniert ebenfalls, zwingt die Aufrufer aber häufig dazu, zusätzliche `null`-Überprüfungen zu implementieren. Der Vertrag sieht vor, dass der Rückgabewert nur dann `null` lautet, wenn das Eingabeargument `url` den Wert `null` aufweist. Um diesen Vertrag auszudrücken, versehen Sie die Methode wie im folgenden Code gezeigt mit Anmerkungen:

```csharp
[return: NotNullIfNotNull("url")]
string? GetTopLevelDomainFromFullUrl(string? url);
```

Der Rückgabewert und das Argument wurden beide um `?` ergänzt, um darauf hinzuweisen, dass beide den Wert `null` annehmen können. Das Attribut verdeutlicht außerdem, dass der Rückgabewert ungleich NULL ist, wenn das `url`-Argument ungleich `null` ist.

Sie geben bedingte Nachbedingungen mit diesen Attributen an:

- [MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): Ein Non-Nullable-Eingabeargument darf NULL sein, wenn die Methode den angegebenen `bool`-Wert zurückgibt.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): Ein Nullable-Eingabeargument ist nicht NULL, wenn die Methode den angegebenen `bool`-Wert zurückgibt.
- [NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): Ein Rückgabewert ist nicht NULL, wenn das Eingabeargument für den angegebenen Parameter nicht NULL ist.

## <a name="verify-unreachable-code"></a>Überprüfen von unerreichbarem Code

Einige Methoden, typischerweise Ausnahmehilfsmethoden oder andere Hilfsmethoden, werden immer mit Ausgabe einer Ausnahme beendet. Eine Hilfsmethode kann eine Ausnahme basierend auf dem Wert eines booleschen Arguments auslösen.

Im ersten Fall können Sie das `DoesNotReturn`-Attribut zur Methodendeklaration hinzufügen. Der Compiler unterstützt Sie auf drei Arten. 1\. Der Compiler gibt eine Warnung aus, wenn die Methode beendet werden kann, ohne eine Ausnahme auszulösen. 2\. Der Compiler markiert Code nach einem Aufruf dieser Methode als *unerreichbar*, bis eine geeignete `catch`-Klausel gefunden wird. 3\. Der unerreichbare Code hat keine Auswirkung auf NULL-Zustände. Betrachten Sie diese Methode:

```csharp
[DoesNotReturn]
private void FailFast()
{
    throw new InvalidOperationException();
}

public void SetState(object containedField)
{
    if (!isInitialized)
    {
        FailFast();
    }

    // unreachable code:
    _field = containedField;
}
```

Im zweiten Fall fügen Sie das `DoesNotReturnIf`-Attribut einem booleschen Parameter der Methode hinzu. Sie können das vorherige Beispiel folgendermaßen abändern:

```csharp
private void FailFast([DoesNotReturnIf(false)] bool isValid)
{
    if (!isValid)
    {
        throw new InvalidOperationException();
    }
}

public void SetState(object containedField)
{
    FailFast(isInitialized);

    // unreachable code when "isInitialized" is false:
    _field = containedField;
}
```

## <a name="summary"></a>Zusammenfassung

[!INCLUDE [C# version alert](../../includes/csharp-version-alert.md)]

Das Hinzufügen von Nullable-Verweistypen ermöglicht eine Beschreibung der Erwartungen für Ihre APIs für Variablen, die den Wert `null` annehmen könnten. Die zusätzlichen Attribute erweitern die Möglichkeiten zur Beschreibung des NULL-Zustands von Variablen als Vor- und Nachbedingungen. Durch diese Attribute werden Ihre Erwartungen klarer beschrieben und verbessern das Benutzererlebnis für Entwickler, die Ihre APIs nutzen.

Wenn Sie Bibliotheken für einen Nullable-Kontext aktualisieren, fügen Sie diese Attribute hinzu, um Benutzer bei der richtigen Verwendung Ihrer APIs zu unterstützen. Die Attribute unterstützen Sie bei der vollständigen Beschreibung des NULL-Zustands von Eingabeargumenten und Rückgabewerten:

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): Ein Non-Nullable-Eingabeargument darf NULL sein.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): Ein Nullable-Eingabeargument darf nie NULL sein.
- [MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): Ein Non-Nullable-Rückgabewert darf NULL sein.
- [NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): Ein Nullable-Rückgabetyp ist niemals NULL.
- [MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): Ein Non-Nullable-Eingabeargument darf NULL sein, wenn die Methode den angegebenen `bool`-Wert zurückgibt.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): Ein Nullable-Eingabeargument ist nicht NULL, wenn die Methode den angegebenen `bool`-Wert zurückgibt.
- [NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): Ein Rückgabewert ist nicht NULL, wenn das Eingabeargument für den angegebenen Parameter nicht NULL ist.
- [DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute): Die Methode gibt niemals ein Ergebnis zurück. Anders ausgedrückt: Die Methode löst immer eine Ausnahme aus.
- [DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): Die Methode gibt niemals ein Ergebnis zurück, wenn der zugeordnete Parameter `bool` einen angegebenen Wert aufweist.
