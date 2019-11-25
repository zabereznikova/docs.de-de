---
title: Codeverträge
ms.date: 09/05/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Code contracts
ms.assetid: 84526045-496f-489d-8517-a258cf76f040
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 103d668dd7a7436fd1acdccdc0afc2431ed8372a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975009"
---
# <a name="code-contracts"></a>Codeverträge

Codeverträge bieten eine Möglichkeit, Vorbedingungen, Nachbedingungen und Objektinvarianten im Code festzulegen. Vorbedingungen sind Anforderungen, die beim Eingeben einer Methode oder Eigenschaft erfüllt werden müssen. Nachbedingungen beschreiben Erwartungen zu dem Zeitpunkt, zu dem die Methode oder der Eigenschaftencode beendet wird. Objektinvarianten beschreiben den erwarteten Zustand für eine Klasse, die in einem einwandfreien Zustand ist.

Codeverträge enthalten Klassen zum Markieren des Codes, eine statische Analyse für die Kompilierzeitanalyse und eine Laufzeitanalyse. Die Klassen für Codeverträge befinden sich im <xref:System.Diagnostics.Contracts>-Namespace.

Codeverträge bieten folgende Vorteile:

- Verbessertes Testen: Codeverträge ermöglichen eine statische Vertragsüberprüfung, Laufzeitüberprüfung und Dokumentationsgenerierung.

- Automatische Testtools: Sie können mithilfe von Codeverträgen aussagekräftigere Komponententests generieren, indem bedeutungslose Testargumente, die die Vorbedingungen nicht erfüllen, herausgefiltert werden.

- Statische Überprüfung: Mit der statischen Prüfung kann bestimmt werden, ob Vertragsverletzungen vorliegen, ohne das Programm auszuführen. Es wird nach impliziten Verträgen (wie NULL-Dereferenzierungen und Arraygrenzen) sowie nach expliziten Verträgen gesucht.

- Referenzdokumentation: Der Dokumentations-Generator erweitert vorhandene XML-Dokumentationsdateien um Vertragsinformationen. Es gibt auch Stylesheets, die mit [Sandcastle](https://github.com/EWSoftware/SHFB) verwendet werden können, sodass die generierten Dokumentationsseiten Vertragsabschnitte enthalten können.

Alle .NET Framework-Sprachen können umgehend Verträge nutzen. Sie müssen keinen speziellen Parser oder Compiler schreiben. Mit einem Visual Studio-Add-In können Sie die Ebene der auszuführenden Codevertragsanalyse angeben. Durch die Analysen kann überprüft werden, ob die Verträge wohlgeformt sind (Typüberprüfung und Namensauflösung), und es kann eine kompilierte Form der Verträge im Microsoft Intermediate Language(MSIL)-Format erzeugt werden. Die Erstellung von Verträgen in Visual Studio ermöglicht die Nutzung der vom Tool bereitgestellten IntelliSense-Standardfunktionen.

Die meisten Methoden in der Vertragsklasse werden bedingt kompiliert. Das heißt, dass der Compiler nur dann Aufrufe dieser Methoden ausgibt, wenn Sie mithilfe der `#define`-Anweisung ein Sonderzeichen (CONTRACTS_FULL) definieren. CONTRACTS_FULL ermöglicht das Schreiben von Verträgen in den Code ohne Verwendung von `#ifdef`-Anweisungen. Sie können unterschiedliche Builds erstellen, von denen einige Verträge enthalten und andere keine Verträge enthalten.

Tools und ausführliche Anweisungen zur Verwendung von Code Verträgen finden Sie unter [Code Verträge](https://marketplace.visualstudio.com/items?itemName=RiSEResearchinSoftwareEngineering.CodeContractsforNET) auf der Visual Studio Marketplace-Website.

## <a name="preconditions"></a>Vorbedingungen

Sie können Vorbedingungen mit der <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType>-Methode ausdrücken. Vorbedingungen geben den Zustand beim Aufrufen einer Methode an. Sie werden im Allgemeinen zum Angeben gültiger Parameterwerte verwendet. Auf alle Member, die in Vorbedingungen erwähnt werden, muss mindestens wie auf die Methode selbst zugegriffen werden können. Andernfalls wird die Vorbedingung möglicherweise nicht von allen Aufrufern einer Methode verstanden. Die Bedingung darf keine Nebeneffekte haben. Das Laufzeitverhalten fehlerhafter Vorbedingungen wird durch die Laufzeitanalyse bestimmt.

Die folgende Vorbedingung drückt z. B. aus, dass der Parameter `x` nicht NULL sein darf.

```csharp
Contract.Requires(x != null);
```

Wenn im Code bei Verletzung einer Vorbedingung eine bestimmte Ausnahme ausgelöst werden soll, können Sie die generische Überladung von <xref:System.Diagnostics.Contracts.Contract.Requires%2A> wie folgt verwenden:

```csharp
Contract.Requires<ArgumentNullException>(x != null, "x");
```

### <a name="legacy-requires-statements"></a>Ältere "Requires"-Anweisungen

Der Großteil des Codes enthält einige Parametervalidierungsfunktionen in Form des `if`-`then`-`throw`-Codes. Die Vertragstools erkennen diese Anweisungen in den folgenden Fällen als Vorbedingungen:

- Die Anweisungen werden vor allen anderen Anweisungen in einer Methode angezeigt.

- Auf den gesamten Satz solcher Anweisungen folgt ein expliziter <xref:System.Diagnostics.Contracts.Contract>-Methodenaufruf, beispielsweise ein Aufruf der <xref:System.Diagnostics.Contracts.Contract.Requires%2A>-, <xref:System.Diagnostics.Contracts.Contract.Ensures%2A>-, <xref:System.Diagnostics.Contracts.Contract.EnsuresOnThrow%2A>- oder <xref:System.Diagnostics.Contracts.Contract.EndContractBlock%2A>-Methode.

Wenn `if`-`then`-`throw`-Anweisungen in dieser Form angezeigt werden, erkennen die Tools sie als ältere `requires`-Anweisungen. Wenn keine anderen Verträge auf die `if`-`then`-`throw`-Sequenz folgen, beenden Sie den Code mit der <xref:System.Diagnostics.Contracts.Contract.EndContractBlock%2A?displayProperty=nameWithType>-Methode.

```csharp
if (x == null) throw new ...
Contract.EndContractBlock(); // All previous "if" checks are preconditions
```

Beachten Sie, dass die Bedingung im vorangehenden Test eine negierte Vorbedingung ist. (Die tatsächliche Vorbedingung wäre `x != null`.) Eine negatierte Vorbedingung ist hochgradig eingeschränkt: Sie muss wie im vorherigen Beispiel geschrieben werden. Das heißt, Sie sollte keine `else` Klauseln enthalten, und der Text der `then`-Klausel muss eine einzelne `throw`-Anweisung sein. Der `if`-Test unterliegt Reinheits- und Sichtbarkeitsregeln (siehe [Verwendungsrichtlinien](#usage_guidelines)), aber der `throw`-Ausdruck unterliegt nur Reinheitsregeln. Der Typ der ausgelösten Ausnahme muss jedoch genauso sichtbar sein wie die Methode, in der der Vertrag vorkommt.

## <a name="postconditions"></a>Nachbedingungen

Nachbedingungen sind Verträge für den Zustand einer Methode, wenn diese beendet wird. Die Nachbedingung wird unmittelbar vor dem Beenden einer Methode überprüft. Das Laufzeitverhalten fehlerhafter Nachbedingungen wird durch die Laufzeitanalyse bestimmt.

Im Gegensatz zu Vorbedingungen können Nachbedingungen mit geringerer Sichtbarkeit auf Member verweisen. Ein Client ist möglicherweise nicht in der Lage, einige der Informationen zu verstehen oder zu verwenden, die durch eine Nachbedingung mithilfe eines privaten Zustands ausgedrückt wurden. Dadurch wird die Fähigkeit des Clients, die Methode ordnungsgemäß zu verwenden, jedoch nicht beeinträchtigt.

### <a name="standard-postconditions"></a>Standardmäßige Nachbedingungen

Sie können standardmäßige Nachbedingungen mit der <xref:System.Diagnostics.Contracts.Contract.Ensures%2A>-Methode ausdrücken. Nachbedingungen drücken eine Bedingung aus, die bei normaler Beendigung der Methode `true` sein muss.

```csharp
Contract.Ensures(this.F > 0);
```

### <a name="exceptional-postconditions"></a>Ausnahmenachbedingungen

Ausnahmenachbedingungen sind Nachbedingungen, die `true` sein sollten, wenn eine bestimmte Ausnahme von einer Methode ausgelöst wird. Sie können diese Nachbedingungen mit der <xref:System.Diagnostics.Contracts.Contract.EnsuresOnThrow%2A?displayProperty=nameWithType>-Methode (wie im folgenden Beispiel gezeigt) angeben.

```csharp
Contract.EnsuresOnThrow<T>(this.F > 0);
```

Das Argument ist die Bedingung, die `true` sein muss, wenn eine Ausnahme ausgelöst wird, bei der es sich um einen Untertyp von `T` handelt.

Es gibt einige Ausnahmetypen, die nur erschwert in einer Ausnahmenachbedingung verwendet werden können. Beispielsweise erfordert die Verwendung des <xref:System.Exception>-Typs für `T`, dass die Bedingung durch die Methode unabhängig vom Typ der ausgelösten Ausnahme gewährleistet wird, auch wenn es sich um einen Stapelüberlauf oder eine andere nicht kontrollierbare Ausnahme handelt. Verwenden Sie Ausnahmenachbedingungen nur für bestimmte Ausnahmen, die beim Aufruf eines Members ausgelöst werden könnten, z. B. wenn eine <xref:System.InvalidTimeZoneException> für einen <xref:System.TimeZoneInfo>-Methodenaufruf ausgelöst wird.

### <a name="special-postconditions"></a>Besondere Nachbedingungen

Die folgenden Methoden können nur innerhalb von Nachbedingungen verwendet werden:

- Mit dem Ausdruck `Contract.Result<T>()`, in dem `T` durch den Rückgabetyp der Methode ersetzt wird, können Sie auf Methodenrückgabewerte in Nachbedingungen verweisen. Wenn der Compiler den Typ nicht ableiten kann, müssen Sie ihn explizit angeben. Der C#-Compiler kann beispielsweise keine Typen für Methoden ableiten, die keine Argumente akzeptieren. Daher ist die folgende Nachbedingung erforderlich: `Contract.Ensures(0 <Contract.Result<int>())`-Methoden mit dem Rückgabetyp `void` können in ihren Nachbedingungen nicht auf `Contract.Result<T>()` verweisen.

- Ein prestate-Wert in einer Nachbedingung verweist auf den Wert eines Ausdrucks am Anfang einer Methode oder Eigenschaft. Er verwendet den Ausdruck `Contract.OldValue<T>(e)`, wobei `T` der Typ von `e` ist. Sie können das generische Typargument weglassen, wenn der Compiler den Typ ableiten kann. (Beispielsweise leitet der C# Compiler den Typ immer ab, da er ein Argument annimmt.) Es gibt mehrere Einschränkungen hinsichtlich der möglichen `e` und der Kontexte, in denen ein Alter Ausdruck auftreten kann. Ein alter Ausdruck darf keinen anderen alten Ausdruck enthalten. Vor allem muss ein alter Ausdruck auf einen Wert verweisen, der im Vorbedingungszustand der Methode vorhanden war. Es muss sich also um einen Ausdruck handeln, der ausgewertet werden kann, solange die Vorbedingung der Methode `true` ist. Nachfolgend finden Sie mehrere Instanzen dieser Regel.

  - Der Wert muss im Vorbedingungszustand der Methode vorhanden sein. Um auf ein Feld für ein Objekt zu verweisen, müssen die Vorbedingungen sicherstellen, dass das Objekt immer ungleich NULL ist.

  - Sie können nicht auf den Rückgabewert der Methode in einem alten Ausdruck verweisen:

      ```csharp
      Contract.OldValue(Contract.Result<int>() + x) // ERROR
      ```

  - Sie können nicht auf `out`-Parameter in einem alten Ausdruck verweisen.

  - Ein alter Ausdruck kann nicht von der gebundenen Variablen eines Quantifizierers abhängen, wenn der Bereich des Quantifizierers vom Rückgabewert der Methode abhängt:

      ```csharp
      Contract.ForAll(0, Contract.Result<int>(), i => Contract.OldValue(xs[i]) > 3); // ERROR
      ```

  - Ein alter Ausdruck kann nur auf den Parameter des anonymen Delegaten in einem <xref:System.Diagnostics.Contracts.Contract.ForAll%2A>- oder <xref:System.Diagnostics.Contracts.Contract.Exists%2A>-Aufruf verweisen, wenn er als Indexer oder Argument für einen Methodenaufruf verwendet wird:

      ```csharp
      Contract.ForAll(0, xs.Length, i => Contract.OldValue(xs[i]) > 3); // OK
      Contract.ForAll(0, xs.Length, i => Contract.OldValue(i) > 3); // ERROR
      ```

  - Ein alter Ausdruck kann nicht im Text eines anonymen Delegaten auftreten, wenn der Wert des alten Ausdrucks von einem der Parameter des anonymen Delegaten abhängt, sofern der anonyme Delegat kein Argument für die <xref:System.Diagnostics.Contracts.Contract.ForAll%2A>- oder <xref:System.Diagnostics.Contracts.Contract.Exists%2A>-Methode ist:

      ```csharp
      Method(... (T t) => Contract.OldValue(... t ...) ...); // ERROR
      ```

  - `Out`-Parameter stellen ein Problem dar, weil Verträge vor dem Text der Methode angezeigt werden und die meisten Compiler keine Verweise auf `out`-Parameter in Nachbedingungen zulassen. Zur Lösung dieses Problems steht in der <xref:System.Diagnostics.Contracts.Contract>-Klasse die <xref:System.Diagnostics.Contracts.Contract.ValueAtReturn%2A>-Methode zur Verfügung, die eine Nachbedingung auf Grundlage eines `out`-Parameters zulässt.

      ```csharp
      public void OutParam(out int x)
      {
          Contract.Ensures(Contract.ValueAtReturn(out x) == 3);
          x = 3;
      }
      ```

      Wie bei der <xref:System.Diagnostics.Contracts.Contract.OldValue%2A>-Methode können Sie den generischen Typparameter weglassen, wenn der Compiler den Typ ableiten kann. Der Vertrags-Rewriter ersetzt den Methodenaufruf durch den Wert des `out`-Parameters. Die <xref:System.Diagnostics.Contracts.Contract.ValueAtReturn%2A>-Methode kann nur in Nachbedingungen angezeigt werden. Das Argument für die Methode muss ein `out`-Parameter oder ein Feld eines strukturbezogenen `out`-Parameters sein. Letzteres ist auch hilfreich, wenn auf Felder in der Nachbedingung eines Strukturkonstruktors verwiesen wird.

      > [!NOTE]
      > Derzeit kann von den Tools für die Codevertragsanalyse nicht überprüft werden, ob `out`-Parameter ordnungsgemäß initialisiert werden, und deren Nennung in der Nachbedingung wird ignoriert. Wenn also im vorherigen Beispiel in der Zeile nach dem Vertrag der Wert von `x` verwendet worden wäre, statt der Zeile eine ganze Zahl zuzuweisen, würde ein Compiler nicht den entsprechenden Fehler ausgeben. In einem Build, in dem das CONTRACTS_FULL-Präprozessorsymbol nicht definiert ist (z.B. in einem Releasebuild), gibt der Compiler jedoch einen Fehler aus.

## <a name="invariants"></a>Invarianten

Objektinvarianten sind Bedingungen, die für jede Instanz einer Klasse "true" sein sollten, wenn das Objekt für einen Client sichtbar ist. Sie drücken die Bedingungen aus, unter denen das Objekt als korrekt betrachtet wird.

Die invarianten Methoden werden identifiziert, indem sie mit dem <xref:System.Diagnostics.Contracts.ContractInvariantMethodAttribute>-Attribut markiert werden. Die invarianten Methoden dürfen keinen Code enthalten. Eine Ausnahme bildet eine Sequenz von Aufrufen der <xref:System.Diagnostics.Contracts.Contract.Invariant%2A>-Methode, bei denen (wie im folgenden Beispiel gezeigt) jeweils eine einzelne Invariante angegeben wird.

```csharp
[ContractInvariantMethod]
protected void ObjectInvariant ()
{
    Contract.Invariant(this.y >= 0);
    Contract.Invariant(this.x > this.y);
    ...
}
```

Invarianten werden durch das CONTRACTS_FULL-Präprozessorsymbol bedingt definiert. Bei der Laufzeitüberprüfung werden die Invarianten am Ende jeder öffentlichen Methode überprüft. Wenn eine Invariante eine öffentliche Methode in der gleichen Klasse erwähnt, wird die Invariantenüberprüfung, die normalerweise am Ende dieser öffentlichen Methode erfolgt, deaktiviert. Stattdessen wird die Überprüfung nur am Ende des äußersten Methodenaufrufs dieser Klasse ausgeführt. Dies geschieht auch, wenn die Klasse wegen eines Aufrufs einer Methode in einer anderen Klasse erneut eingegeben wird. Invarianten werden nicht für einen objektfinalizer und eine <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> Implementierung geprüft.

<a name="usage_guidelines"></a>

## <a name="usage-guidelines"></a>Verwendungsrichtlinien

### <a name="contract-ordering"></a>Verträge – Reihenfolge

In der folgenden Tabelle wird die Reihenfolge der Elemente aufgeführt, die Sie beim Schreiben von Methodenverträgen verwenden sollten.

|`If-then-throw statements`|Abwärtskompatible öffentliche Vorbedingungen|
|-|-|
|<xref:System.Diagnostics.Contracts.Contract.Requires%2A>|Alle öffentlichen Vorbedingungen|
|<xref:System.Diagnostics.Contracts.Contract.Ensures%2A>|Alle öffentlichen (normalen) Nachbedingungen|
|<xref:System.Diagnostics.Contracts.Contract.EnsuresOnThrow%2A>|Alle öffentlichen Ausnahmenachbedingungen|
|<xref:System.Diagnostics.Contracts.Contract.Ensures%2A>|Alle privaten/internen (normalen) Nachbedingungen|
|<xref:System.Diagnostics.Contracts.Contract.EnsuresOnThrow%2A>|Alle privaten/internen Ausnahmenachbedingungen|
|<xref:System.Diagnostics.Contracts.Contract.EndContractBlock%2A>|Rufen Sie bei Verwendung von `if`-`then`-`throw`-Formatvorbedingungen ohne andere Verträge <xref:System.Diagnostics.Contracts.Contract.EndContractBlock%2A> auf, um anzugeben, dass es sich bei allen vorherigen If-Überprüfungen um Vorbedingungen handelt.|

<a name="purity"></a>

### <a name="purity"></a>Reinheit

Alle Methoden, die in einem Vertrag aufgerufen werden, müssen "rein" sein, was bedeutet, dass kein bereits vorhandener Zustand aktualisiert werden darf. Mit einer reinen Methode können Objekte geändert werden, die nach Eintragung in die reine Methode erstellt wurden.

Bei Verwendung von Codevertragstools wird derzeit davon ausgegangen, dass die folgenden Codeelemente rein sind:

- Methoden, die mit dem <xref:System.Diagnostics.Contracts.PureAttribute> markiert sind.

- Typen, die mit dem <xref:System.Diagnostics.Contracts.PureAttribute> markiert sind (das Attribut gilt für alle Methoden des Typs).

- Get-Eigenschaftenaccessoren

- Operatoren (statische Methoden, deren Namen mit „op“ beginnen, die einen oder zwei Parameter und einen nicht leeren Rückgabetyp aufweisen).

- Eine beliebige Methode, deren vollqualifizierter Name mit "System.Diagnostics.Contracts.Contract", "System.String", "System.IO.Path" oder "System.Type" beginnt.

- Ein beliebiger aufgerufener Delegat, vorausgesetzt, dass dem Delegattyp selbst das <xref:System.Diagnostics.Contracts.PureAttribute> zugewiesen ist. Die Delegattypen <xref:System.Predicate%601?displayProperty=nameWithType> und <xref:System.Comparison%601?displayProperty=nameWithType> werden als rein eingestuft.

<a name="visibility"></a>

### <a name="visibility"></a>Sichtbarkeit

Alle in einem Vertrag erwähnten Member müssen mindestens ebenso sichtbar sein wie die Methode, in der sie angezeigt werden. Ein privates Feld kann beispielsweise nicht in einer Vorbedingung für eine öffentliche Methode erwähnt werden. Clients können keinen derartigen Vertrag überprüfen, bevor sie die Methode aufrufen. Wenn das Feld jedoch mit dem <xref:System.Diagnostics.Contracts.ContractPublicPropertyNameAttribute> markiert wird, unterliegt es diesen Regeln nicht.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Verwendung von Codeverträgen veranschaulicht.

[!code-csharp[ContractExample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/contractexample/cs/program.cs#1)]
[!code-vb[ContractExample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/contractexample/vb/program.vb#1)]
