---
title: Parameterentwurf
ms.date: 10/22/2008
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
ms.openlocfilehash: 815075198f34c0c045603b9d377b9d5fbdf1a91d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707879"
---
# <a name="parameter-design"></a>Parameterentwurf

Dieser Abschnitt enthält allgemeine Richtlinien zum Parameter Entwurf, einschließlich Abschnitten mit Richtlinien zum Überprüfen von Argumenten. Außerdem sollten Sie die in [Benennungs Parametern](naming-parameters.md)beschriebenen Richtlinien beachten.

 in ✔️ wird der am wenigsten abgeleitete Parametertyp verwendet, der die für den Member erforderliche Funktionalität bereitstellt.

 Angenommen, Sie möchten eine Methode entwerfen, die eine Auflistung auflistet und jedes Element in der Konsole ausgibt. Eine solche Methode sollte z <xref:System.Collections.IEnumerable> . b. den-Parameter, nicht <xref:System.Collections.ArrayList> oder verwenden <xref:System.Collections.IList> .

 ❌ Verwenden Sie keine reservierten Parameter.

 Wenn in einer zukünftigen Version mehr Eingaben für einen Member erforderlich sind, kann eine neue Überladung hinzugefügt werden.

 ❌ Sie verfügen nicht über öffentlich verfügbar gemachte Methoden, die Zeiger, Zeiger Arrays oder mehrdimensionale Arrays als Parameter verwenden.

 Zeiger und mehrdimensionale Arrays sind relativ schwierig zu verwenden. In fast allen Fällen können APIs umgestaltet werden, um zu vermeiden, dass diese Typen als Parameter übernommen werden.

 ✔️ alle `out` Parameter nach allen nach-Wert-und- `ref` Parametern platzieren (ausgenommen Parameter Arrays), selbst wenn dies zu einer Inkonsistenz bei der Parameter Anordnung zwischen über Ladungen führt (siehe Element [Überladung](member-overloading.md)).

 Die `out` Parameter können als zusätzliche Rückgabewerte angesehen werden. durch Gruppierung werden die Methoden Signaturen leichter zu verstehen.

 beim Überschreiben von Membern oder Implementieren von Schnittstellenmembern sind ✔️ konsistent.

 Dadurch wird die Beziehung zwischen den Methoden besser kommuniziert.

### <a name="choosing-between-enum-and-boolean-parameters"></a>Auswählen zwischen Aufzählungs-und booleschen Parametern  

 ✔️ verwenden Enumerationswerte, wenn ein Member andernfalls mindestens zwei boolesche Parameter aufweisen würde.

 ❌ Verwenden Sie keine booleschen Werte, es sei denn, Sie sind sicher, dass nie mehr als zwei Werte benötigt werden.

 Enumerationen geben Ihnen einen gewissen Raum für eine zukünftige Addition von Werten. Sie sollten jedoch alle Implikationen beachten, die sich aus dem Hinzufügen von Werten zu Enumerationen machen, die im [Enumerationsentwurf](enum.md)beschrieben werden.

 ✔️ sollten Sie die Verwendung von booleschen Werten für Konstruktorparameter in Erwägung gezogen, die tatsächlich zwei Zustands Werte sind und einfach zum Initialisieren von booleschen Eigenschaften verwendet werden.

### <a name="validating-arguments"></a>Validieren von Argumenten

 ✔️ Überprüfen Sie Argumente, die an öffentliche, geschützte oder explizit implementierte Member übermittelt werden. Throw <xref:System.ArgumentException?displayProperty=nameWithType> oder eine der zugehörigen Unterklassen, wenn die Validierung fehlschlägt.

 Beachten Sie, dass die tatsächliche Validierung nicht unbedingt im öffentlichen oder geschützten Member selbst erfolgen muss. Dies kann in einer privaten oder internen Routine auf einer niedrigeren Ebene vorkommen. Der Hauptgrund dafür ist, dass die gesamte Oberfläche, die den Endbenutzern zur Verfügung gestellt wird, die Argumente prüft.

 ✔️ lösen Sie aus, <xref:System.ArgumentNullException> Wenn ein NULL-Argument übergeben wird und der Member keine NULL-Argumente unterstützt.

 ✔️ Überprüfen Sie die Aufzählungs Parameter.

 Gehen Sie nicht davon aus, dass sich die Aufzählungs Argumente in dem von der-Aufzählung definierten Bereich befinden. Die CLR ermöglicht das Umwandeln eines beliebigen ganzzahligen Werts in einen Enumerationswert, auch wenn der Wert nicht in der Enumeration definiert ist.

 ❌ Verwenden Sie nicht für Aufzählungs <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> Bereichs Überprüfungen.

 ✔️ Beachten Sie, dass änderbare Argumente möglicherweise geändert wurden, nachdem Sie überprüft wurden.

 Wenn der Member Sicherheits sensibel ist, wird empfohlen, eine Kopie zu erstellen und dann das Argument zu validieren und zu verarbeiten.

### <a name="parameter-passing"></a>Parameterübergabe

 Aus der Perspektive eines Framework-Designers besteht aus drei Hauptgruppen von Parametern: nach Wert Parametern, `ref` Parametern und `out` Parametern.

 Wenn ein Argument durch einen by-value-Parameter übergeben wird, empfängt der Member eine Kopie des tatsächlich übergebenen Arguments. Wenn das Argument ein Werttyp ist, wird eine Kopie des Arguments auf dem Stapel abgelegt. Wenn das Argument ein Referenztyp ist, wird eine Kopie des Verweises auf dem Stapel abgelegt. Bei den beliebtesten CLR-Sprachen, wie z. b. c#, VB.net und C++, wird standardmäßig die Übergabe von Parametern nach Wert angegeben.

 Wenn ein Argument durch einen Parameter übergeben wird `ref` , erhält der Member einen Verweis auf das tatsächlich übergebene Argument. Wenn das Argument ein Werttyp ist, wird ein Verweis auf das Argument auf dem Stapel abgelegt. Wenn es sich bei dem Argument um einen Verweistyp handelt, wird ein Verweis auf den Verweis auf den Stapel eingefügt. `Ref` Parameter können verwendet werden, um zuzulassen, dass der Member vom Aufrufer übergeben wird.

 `Out` Parameter ähneln `ref` Parametern mit einigen kleinen unterschieden. Der-Parameter wird anfänglich als nicht zugewiesen betrachtet und kann nicht im Element Text gelesen werden, bevor ihm ein Wert zugewiesen wird. Außerdem muss dem-Parameter ein Wert zugewiesen werden, bevor der Member zurückgegeben wird.

 ❌ Verwenden Sie keine- `out` oder- `ref` Parameter.

 Die `out` Verwendung `ref` von-oder-Parametern erfordert die Verwendung von Zeigern, die Unterschiede zwischen Werttypen und Verweis Typen sowie die Behandlung von Methoden mit mehreren Rückgabe Werten Außerdem wird der Unterschied zwischen `out` -und- `ref` Parametern nicht häufig verstanden. Frameworkarchitekten, die für eine allgemeine Zielgruppe entwerfen, sollten nicht erwarten, dass Benutzer mit- `out` oder- `ref` Parametern arbeiten

 ❌ Übergeben Sie Verweis Typen nicht als Verweis.

 Es gibt einige begrenzte Ausnahmen für die Regel, z. b. eine Methode, die zum Austauschen von Verweisen verwendet werden kann.

### <a name="members-with-variable-number-of-parameters"></a>Elemente mit variabler Anzahl von Parametern

 Member, die eine Variable Anzahl von Argumenten annehmen können, werden durch Angabe eines Array Parameters ausgedrückt. Beispielsweise <xref:System.String> stellt die folgende Methode bereit:

```csharp
public class String {
    public static string Format(string format, object[] parameters);
}
```

 Ein Benutzer kann dann die- <xref:System.String.Format%2A?displayProperty=nameWithType> Methode wie folgt aufzurufen:

 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`

 Wenn Sie das c#-params-Schlüsselwort zu einem Array-Parameter hinzufügen, wird der Parameter in einen sogenannten params-Array Parameter geändert und eine Verknüpfung zur Erstellung eines temporären Arrays bereitgestellt.

```csharp
public class String {
    public static string Format(string format, params object[] parameters);
}
```

 Dadurch kann der Benutzer die Methode aufzurufen, indem er die Array Elemente direkt in der Argumentliste übergibt.

 `String.Format("File {0} not found in {1}",filename,directory);`

 Beachten Sie, dass das parameterschlüsselwort nur dem letzten Parameter in der Parameterliste hinzugefügt werden kann.

 ✔️ Sie ggf. das params-Schlüsselwort zu Array Parametern hinzufügen, wenn Sie erwarten, dass die Endbenutzer Arrays mit einer kleinen Anzahl von Elementen übergeben. Wenn davon ausgegangen wird, dass viele Elemente in gängigen Szenarien übergeben werden, werden diese Elemente wahrscheinlich nicht von den Benutzern Inline übergeben, sodass das params-Schlüsselwort nicht erforderlich ist.

 ❌ Vermeiden Sie die Verwendung von params-Arrays, wenn der Aufrufer fast immer die Eingabe in einem Array haben würde.

 Beispielsweise werden Elemente mit Bytearray-Parametern fast nie aufgerufen, indem einzelne Bytes übergeben werden. Aus diesem Grund verwenden Bytearray-Parameter im .NET Framework nicht das params-Schlüsselwort.

 ❌ Verwenden Sie keine params-Arrays, wenn das Array durch den Member geändert wird, der den Parameter "params Array" annimmt.

 Aufgrund der Tatsache, dass viele Compiler die Argumente für den Member in ein temporäres Array an der aufrufssite umwandeln, kann das Array ein temporäres Objekt sein. Daher gehen alle Änderungen am Array verloren.

 ✔️ in Erwägung gezogen, das Schlüsselwort "para" in einer einfachen Überladung zu verwenden, auch wenn es von einer komplexeren Überladung nicht verwendet werden konnte.

 Fragen Sie sich, ob Benutzer den Wert des params-Arrays in einer Überladung haben würden, auch wenn Sie nicht in allen über Ladungen vorhanden wäre.

 ✔️ versuchen, Parameter zu sortieren, um die Verwendung des Schlüssel Worts "Parameter" zu ermöglichen.

 ✔️ sollten Sie besondere über Ladungen und Codepfade für Aufrufe mit einer kleinen Anzahl von Argumenten in äußerst Leistungs relevanten APIs bereitstellen.

 Dadurch ist es möglich, keine Array Objekte zu erstellen, wenn die API mit einer kleinen Anzahl von Argumenten aufgerufen wird. Bilden Sie die Namen der Parameter, indem Sie eine Singular Form des Array-Parameters und ein numerisches Suffix hinzufügen.

 Dies sollten Sie nur tun, wenn Sie den gesamten Codepfad als Sonderfall verwenden, nicht nur ein Array erstellen und die allgemeinere Methode aufrufen.

 ✔️ Beachten Sie, dass NULL als params-Array Argument übermittelt werden kann.

 Vor der Verarbeitung sollten Sie überprüfen, ob das Array nicht NULL ist.

 ❌ Verwenden Sie die- `varargs` Methoden, die auch als Ellipsen bezeichnet werden.

 Einige CLR-Sprachen, wie z. b. C++, unterstützen eine alternative Konvention zum Übergeben von Variablen Parameterlisten mit dem Namen `varargs` Methoden. Die Konvention sollte nicht in Frameworks verwendet werden, da Sie nicht CLS-kompatibel ist.

### <a name="pointer-parameters"></a>Zeigerparameter

 Im Allgemeinen sollten Zeiger nicht in der öffentlichen Oberfläche eines gut entworfenen verwalteten Code-Frameworks angezeigt werden. In den meisten Fällen sollten Zeiger gekapselt werden. In einigen Fällen sind Zeiger aber aus Interoperabilitäts Gründen erforderlich, und die Verwendung von Zeigern in solchen Fällen ist angemessen.

 ✔️ eine Alternative für alle Member bereitstellen, die ein Zeigerargument verwenden, da Zeiger nicht CLS-kompatibel sind.

 ❌ Vermeiden Sie eine teure Argument Überprüfung von Zeiger Argumenten.

 beim Entwerfen von Membern mit Zeigern folgen ✔️ allgemeinen Zeiger bezogenen Konventionen.

 Beispielsweise ist es nicht erforderlich, den Start Index zu übergeben, da einfache Zeigerarithmetik verwendet werden kann, um das gleiche Ergebnis zu erzielen.

 *Teile &copy; 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Weitere Informationen

- [Entwurfs Richtlinien für Member](member.md)
- [Framework-Entwurfs Richtlinien](index.md)
