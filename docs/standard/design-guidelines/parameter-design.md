---
title: Parameterentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
ms.openlocfilehash: 78eb07503810e75d14bcd73740fe429e2f73475e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743677"
---
# <a name="parameter-design"></a>Parameter Entwurf

Dieser Abschnitt enthält allgemeine Richtlinien zum Parameter Entwurf, einschließlich Abschnitten mit Richtlinien zum Überprüfen von Argumenten. Außerdem sollten Sie die in [Benennungs Parametern](../../../docs/standard/design-guidelines/naming-parameters.md)beschriebenen Richtlinien beachten.

 in ✔️ wird der am wenigsten abgeleitete Parametertyp verwendet, der die für den Member erforderliche Funktionalität bereitstellt.

 Angenommen, Sie möchten eine Methode entwerfen, die eine Auflistung auflistet und jedes Element in der Konsole ausgibt. Eine solche Methode sollte z. b. <xref:System.Collections.IEnumerable> als Parameter, nicht jedoch <xref:System.Collections.ArrayList> oder <xref:System.Collections.IList>annehmen.

 ❌ keine reservierten Parameter verwenden.

 Wenn in einer zukünftigen Version mehr Eingaben für einen Member erforderlich sind, kann eine neue Überladung hinzugefügt werden.

 ❌ verfügen über keine öffentlich verfügbar gemachten Methoden, die Zeiger, Zeiger Arrays oder mehrdimensionale Arrays als Parameter verwenden.

 Zeiger und mehrdimensionale Arrays sind relativ schwierig zu verwenden. In fast allen Fällen können APIs umgestaltet werden, um zu vermeiden, dass diese Typen als Parameter übernommen werden.

 ✔️ Alle `out` Parameter nach allen nach Wert-und `ref`-Parametern platzieren (ausgenommen Parameter Arrays), selbst wenn dies zu einer Inkonsistenz bei der Parameter Anordnung zwischen über Ladungen führt (siehe Element [Überladung](../../../docs/standard/design-guidelines/member-overloading.md)).

 Die `out` Parameter können als zusätzliche Rückgabewerte angesehen werden, und durch Gruppierung werden die Methoden Signaturen leichter zu verstehen.

 beim Überschreiben von Membern oder Implementieren von Schnittstellenmembern sind ✔️ konsistent.

 Dadurch wird die Beziehung zwischen den Methoden besser kommuniziert.

### <a name="choose-between-enum-and-boolean-parameters"></a>Auswahl zwischen Aufzählungs-und booleschen Parametern
 ✔️ verwenden Enumerationswerte, wenn ein Member andernfalls mindestens zwei boolesche Parameter aufweisen würde.

 ❌ verwenden keine booleschen Werte, es sei denn, Sie sind sicher, dass nie mehr als zwei Werte benötigt werden.

 Enumerationen geben Ihnen einen gewissen Raum für eine zukünftige Addition von Werten. Sie sollten jedoch alle Implikationen beachten, die sich aus dem Hinzufügen von Werten zu Enumerationen machen, die im [Enumerationsentwurf](../../../docs/standard/design-guidelines/enum.md)beschrieben werden.

 ✔️ sollten Sie die Verwendung von booleschen Werten für Konstruktorparameter in Erwägung gezogen, die tatsächlich zwei Zustands Werte sind und einfach zum Initialisieren von booleschen Eigenschaften verwendet werden.

### <a name="validate-arguments"></a>Validieren von Argumenten
 ✔️ Überprüfen Sie Argumente, die an öffentliche, geschützte oder explizit implementierte Member übermittelt werden. Lösen Sie <xref:System.ArgumentException?displayProperty=nameWithType>oder eine der zugehörigen Unterklassen aus, wenn die Validierung fehlschlägt.

 Beachten Sie, dass die tatsächliche Validierung nicht unbedingt im öffentlichen oder geschützten Member selbst erfolgen muss. Dies kann in einer privaten oder internen Routine auf einer niedrigeren Ebene vorkommen. Der Hauptgrund dafür ist, dass die gesamte Oberfläche, die den Endbenutzern zur Verfügung gestellt wird, die Argumente prüft.

 ✔️ lösen <xref:System.ArgumentNullException> aus, wenn ein NULL-Argument übergeben wird und der Member keine NULL-Argumente unterstützt.

 ✔️ Überprüfen Sie die Aufzählungs Parameter.

 Gehen Sie nicht davon aus, dass sich die Aufzählungs Argumente in dem von der-Aufzählung definierten Bereich befinden. Die CLR ermöglicht das Umwandeln eines beliebigen ganzzahligen Werts in einen Enumerationswert, auch wenn der Wert nicht in der Enumeration definiert ist.

 ❌ keine <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> für Überprüfungen des Aufzählungs Bereichs verwenden.

 ✔️ Beachten Sie, dass änderbare Argumente möglicherweise geändert wurden, nachdem Sie überprüft wurden.

 Wenn der Member Sicherheits sensibel ist, wird empfohlen, eine Kopie zu erstellen und dann das Argument zu validieren und zu verarbeiten.

### <a name="pass-parameters"></a>Übergeben von Parametern
 Aus Sicht eines Framework-Designers gibt es drei Hauptgruppen von Parametern: nach Wert Parameter, `ref` Parameter und `out` Parameter.

 Wenn ein Argument durch einen by-value-Parameter übergeben wird, empfängt der Member eine Kopie des tatsächlich übergebenen Arguments. Wenn das Argument ein Werttyp ist, wird eine Kopie des Arguments auf dem Stapel abgelegt. Wenn das Argument ein Referenztyp ist, wird eine Kopie des Verweises auf dem Stapel abgelegt. Die beliebtesten CLR-Sprachen, wie C#z. b. C++, Visual Basic und, werden standardmäßig zum Übergeben von Parametern nach Wert übergeben.

 Wenn ein Argument über einen `ref`-Parameter übergeben wird, empfängt der Member einen Verweis auf das tatsächlich übergebene Argument. Wenn das Argument ein Werttyp ist, wird ein Verweis auf das Argument auf dem Stapel abgelegt. Wenn es sich bei dem Argument um einen Verweistyp handelt, wird ein Verweis auf den Verweis auf den Stapel eingefügt. `Ref` Parameter können verwendet werden, um zuzulassen, dass der Member vom Aufrufer übergeben wird.

 `Out` Parameter ähneln `ref` Parametern, mit einigen kleinen unterschieden. Der-Parameter wird anfänglich als nicht zugewiesen betrachtet und kann nicht im Element Text gelesen werden, bevor ihm ein Wert zugewiesen wird. Außerdem muss dem-Parameter ein Wert zugewiesen werden, bevor der Member zurückgegeben wird.

 ❌ die Verwendung von `out` oder `ref` Parametern vermeiden.

 Die Verwendung von `out`-oder `ref`-Parametern erfordert die Verwendung von Zeigern, das Verständnis der Unterschiede zwischen Werttypen und Verweis Typen sowie die Behandlung von Methoden mit mehreren Außerdem wird der Unterschied zwischen `out`-und `ref`-Parametern nicht weitgehend verstanden. Frameworkarchitekten, die für eine allgemeine Zielgruppe entwerfen, sollten nicht erwarten, dass Benutzer mit `out`-oder `ref`-Parametern arbeiten.

 ❌ die Verweis Typen nicht als Verweis übergeben.

 Es gibt einige begrenzte Ausnahmen für die Regel, z. b. eine Methode, die zum Austauschen von Verweisen verwendet werden kann.

### <a name="members-with-variable-number-of-parameters"></a>Elemente mit variabler Anzahl von Parametern
 Member, die eine Variable Anzahl von Argumenten annehmen können, werden durch Angabe eines Array Parameters ausgedrückt. <xref:System.String> stellt z. b. die folgende Methode bereit:

```csharp
public class String {
    public static string Format(string format, object[] parameters);
}
```

 Ein Benutzer kann dann die <xref:System.String.Format%2A?displayProperty=nameWithType>-Methode wie folgt aufzurufen:

 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`

 Durch das C# Hinzufügen des params-Schlüssel Worts zu einem Array Parameter wird der Parameter in einen sogenannten params-Array Parameter geändert und eine Verknüpfung zur Erstellung eines temporären Arrays bereitgestellt.

```csharp
public class String {
    public static string Format(string format, params object[] parameters);
}
```

 Dadurch kann der Benutzer die Methode aufzurufen, indem er die Array Elemente direkt in der Argumentliste übergibt.

 `String.Format("File {0} not found in {1}",filename,directory);`

 Beachten Sie, dass das parameterschlüsselwort nur dem letzten Parameter in der Parameterliste hinzugefügt werden kann.

 ✔️ Sie ggf. das params-Schlüsselwort zu Array Parametern hinzufügen, wenn Sie erwarten, dass die Endbenutzer Arrays mit einer kleinen Anzahl von Elementen übergeben. Wenn davon ausgegangen wird, dass viele Elemente in gängigen Szenarien übergeben werden, werden diese Elemente wahrscheinlich nicht von den Benutzern Inline übergeben, sodass das params-Schlüsselwort nicht erforderlich ist.

 ❌ die Verwendung von params-Arrays vermeiden, wenn der Aufrufer fast immer die Eingabe in einem Array haben würde.

 Beispielsweise werden Elemente mit Bytearray-Parametern fast nie aufgerufen, indem einzelne Bytes übergeben werden. Aus diesem Grund verwenden Bytearray-Parameter im .NET Framework nicht das params-Schlüsselwort.

 ❌ keine params-Arrays verwenden, wenn das Array vom Member geändert wird, der den Parameter "params Array" annimmt.

 Aufgrund der Tatsache, dass viele Compiler die Argumente für den Member in ein temporäres Array an der aufrufssite umwandeln, kann das Array ein temporäres Objekt sein. Daher gehen alle Änderungen am Array verloren.

 ✔️ in Erwägung gezogen, das Schlüsselwort "para" in einer einfachen Überladung zu verwenden, auch wenn es von einer komplexeren Überladung nicht verwendet werden konnte.

 Fragen Sie sich, ob Benutzer den Wert des params-Arrays in einer Überladung haben würden, auch wenn Sie nicht in allen über Ladungen vorhanden wäre.

 ✔️ versuchen, Parameter zu sortieren, um die Verwendung des Schlüssel Worts "Parameter" zu ermöglichen.

 ✔️ sollten Sie besondere über Ladungen und Codepfade für Aufrufe mit einer kleinen Anzahl von Argumenten in äußerst Leistungs relevanten APIs bereitstellen.

 Dadurch ist es möglich, keine Array Objekte zu erstellen, wenn die API mit einer kleinen Anzahl von Argumenten aufgerufen wird. Bilden Sie die Namen der Parameter, indem Sie eine Singular Form des Array-Parameters und ein numerisches Suffix hinzufügen.

 Dies sollten Sie nur tun, wenn Sie den gesamten Codepfad als Sonderfall verwenden, nicht nur ein Array erstellen und die allgemeinere Methode aufrufen.

 ✔️ Beachten Sie, dass NULL als params-Array Argument übermittelt werden kann.

 Vor der Verarbeitung sollten Sie überprüfen, ob das Array nicht NULL ist.

 ❌ nicht die `varargs` Methoden verwenden, die auch als Ellipsen bezeichnet werden.

 Einige CLR-Sprachen, wie C++z. b., unterstützen eine alternative Konvention zum Übergeben von Variablen Parameterlisten, die als `varargs` Methoden bezeichnet Die Konvention sollte nicht in Frameworks verwendet werden, da Sie nicht CLS-kompatibel ist.

### <a name="pointer-parameters"></a>Zeiger Parameter
 Im Allgemeinen sollten Zeiger nicht in der öffentlichen Oberfläche eines gut entworfenen verwalteten Code-Frameworks angezeigt werden. In den meisten Fällen sollten Zeiger gekapselt werden. In einigen Fällen sind Zeiger aber aus Interoperabilitäts Gründen erforderlich, und die Verwendung von Zeigern in solchen Fällen ist angemessen.

 ✔️ eine Alternative für alle Member bereitstellen, die ein Zeigerargument verwenden, da Zeiger nicht CLS-kompatibel sind.

 ❌ eine teure Argument Überprüfung von Zeiger Argumenten vermeiden.

 beim Entwerfen von Membern mit Zeigern folgen ✔️ allgemeinen Zeiger bezogenen Konventionen.

 Beispielsweise ist es nicht erforderlich, den Start Index zu übergeben, da einfache Zeigerarithmetik verwendet werden kann, um das gleiche Ergebnis zu erzielen.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Weitere Informationen

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
