---
title: Eigenschaftenentwurf
ms.date: 10/22/2008
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
ms.openlocfilehash: 1cf41a08c641e9251084e5dcac6c46bc54857717
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828737"
---
# <a name="property-design"></a>Eigenschaftenentwurf
Obwohl die Eigenschaften den Methoden technisch ähnlich ähnlich sind, unterscheiden Sie sich in Bezug auf Ihre Verwendungs Szenarien erheblich. Sie sollten als intelligente Felder betrachtet werden. Sie verfügen über die Aufruf Syntax der Felder und die Flexibilität der Methoden.

 ✔️ Erstellen Sie Get-only-Eigenschaften, wenn der Aufrufer den Wert der-Eigenschaft nicht ändern kann.

 Beachten Sie, dass der Eigenschafts Wert auch dann geändert werden kann, wenn es sich bei dem Typ der Eigenschaft um einen änderbaren Referenztyp handelt.

 ❌ Stellen Sie keine festgelegten Eigenschaften oder Eigenschaften mit dem Setter bereit, der über breitere Zugriffsmöglichkeiten verfügt als der Getter.

 Verwenden Sie z. b. keine Eigenschaften mit einem öffentlichen Setter und einem geschützten Getter.

 Wenn der Getter der Eigenschaft nicht bereitgestellt werden kann, implementieren Sie die Funktionalität stattdessen als Methode. Starten Sie ggf. den Methodennamen mit, `Set` und befolgen Sie den Namen der Eigenschaft. Beispielsweise <xref:System.AppDomain> verfügt über eine Methode, die aufgerufen wird, `SetCachePath` anstatt eine nur-Eigenschaft mit dem Namen zu verwenden `CachePath` .

 ✔️ Stellen sinnvolle Standardwerte für alle Eigenschaften bereit, um sicherzustellen, dass die Standardwerte nicht zu einer Sicherheitslücke oder zu einem äußerst ineffizienten Code führen.

 ✔️ erlauben, dass Eigenschaften in beliebiger Reihenfolge festgelegt werden, auch wenn dies zu einem temporären ungültigen Zustand des Objekts führt.

 Es kommt häufig vor, dass zwei oder mehr Eigenschaften mit einem Punkt verknüpft werden, an dem einige Werte einer Eigenschaft aufgrund der Werte anderer Eigenschaften desselben Objekts möglicherweise ungültig sind. In solchen Fällen sollten Ausnahmen, die sich aus dem ungültigen Zustand ergeben, verschoben werden, bis die miteinander verknüpften Eigenschaften tatsächlich vom Objekt zusammen verwendet werden.

 ✔️ behalten Sie den vorherigen Wert bei, wenn ein Eigenschaften Setter eine Ausnahme auslöst.

 ❌ Vermeiden Sie das Auslösen von Ausnahmen von Eigenschaften Getter.

 Eigenschaften Getter sollten einfache Vorgänge sein und sollten keine Vorbedingungen aufweisen. Wenn ein Getter eine Ausnahme auslösen kann, sollte er wahrscheinlich neu gestaltet werden, um eine Methode zu sein. Beachten Sie, dass diese Regel nicht für Indexer gilt, bei denen Ausnahmen aufgrund der Validierung der Argumente erwartet werden.

### <a name="indexed-property-design"></a>Design der indizierten Eigenschaft
 Eine indizierte Eigenschaft ist eine spezielle Eigenschaft, die über Parameter verfügen kann und mit spezieller Syntax ähnlich der Array Indizierung aufgerufen werden kann.

 Indizierte Eigenschaften werden im Allgemeinen als Indexer bezeichnet. Indexer sollten nur in APIs verwendet werden, die den Zugriff auf Elemente in einer logischen Auflistung ermöglichen. Beispielsweise ist eine Zeichenfolge eine Auflistung von Zeichen, und der Indexer für <xref:System.String?displayProperty=nameWithType> wurde hinzugefügt, um auf seine Zeichen zuzugreifen.

 ✔️ können Indexer verwenden, um den Zugriff auf Daten bereitzustellen, die in einem internen Array gespeichert sind.

 ✔️ sollten Indexer für Typen bereitgestellt werden, die Element Auflistungen darstellen.

 ❌ Vermeiden Sie die Verwendung von indizierten Eigenschaften mit mehr als einem Parameter.

 Wenn der Entwurf mehrere Parameter erfordert, überdenken Sie, ob die-Eigenschaft tatsächlich einen Accessor für eine logische Auflistung darstellt. Wenn dies nicht der Fall ist, verwenden Sie stattdessen-Methoden. Sie sollten den Methodennamen ggf `Get` . mit oder Starten `Set` .

 ❌ Vermeiden Sie Indexer mit anderen Parametertypen als <xref:System.Int32?displayProperty=nameWithType> , <xref:System.Int64?displayProperty=nameWithType> , <xref:System.String?displayProperty=nameWithType> , <xref:System.Object?displayProperty=nameWithType> oder einer Enumeration.

 Wenn der Entwurf andere Typen von Parametern erfordert, sollten Sie nachdrücklich neu auswerten, ob die API tatsächlich einen Accessor für eine logische Auflistung darstellt. Wenn dies nicht der Fall ist, verwenden Sie eine-Methode. Sie sollten den Methodennamen ggf `Get` . mit oder Starten `Set` .

 ✔️ den Namen `Item` für indizierte Eigenschaften verwenden, es sei denn, es gibt einen offensichtlich besseren Namen (z. b. siehe die- <xref:System.String.Chars%2A> Eigenschaft für `System.String` ).

 In c# sind Indexer standardmäßig benannte Elemente. <xref:System.Runtime.CompilerServices.IndexerNameAttribute>Kann verwendet werden, um diesen Namen anzupassen.

 ❌ Geben Sie keinen Indexer und keine Methoden an, die semantisch äquivalent sind.

 ❌ Geben Sie nicht mehr als eine Familie überladener Indexer in einem Typ an.

 Dies wird vom c#-Compiler erzwungen.

 ❌ Verwenden Sie keine nicht standardmäßigen indizierten Eigenschaften.

 Dies wird vom c#-Compiler erzwungen.

### <a name="property-change-notification-events"></a>Benachrichtigungs Ereignisse für Eigenschafts Änderungen
 Manchmal ist es hilfreich, ein Ereignis anzugeben, das den Benutzer über Änderungen in einem Eigenschafts Wert benachrichtigt. Beispielsweise löst `System.Windows.Forms.Control` ein- `TextChanged` Ereignis aus, nachdem sich der Wert der- `Text` Eigenschaft geändert hat.

 ✔️ sollten Änderungs Benachrichtigungs Ereignisse in Erwägung ziehen, wenn Eigenschaftswerte in APIs auf hoher Ebene (normalerweise Designer Komponenten) geändert werden.

 Wenn ein Benutzer ein gutes Szenario kennt, wenn eine Eigenschaft eines Objekts geändert wird, sollte das Objekt ein Änderungs Benachrichtigungs Ereignis für die Eigenschaft angeben.

 Es ist jedoch unwahrscheinlich, dass Sie den Aufwand für die Anwendung solcher Ereignisse für APIs auf niedriger Ebene, wie z. b. Basis Typen oder Sammlungen, erhöhen sollten. Beispielsweise werden <xref:System.Collections.Generic.List%601> solche Ereignisse nicht durch das Hinzufügen eines neuen Elements zur Liste, und die- `Count` Eigenschaft wird geändert.

 ✔️ sollten Änderungs Benachrichtigungs Ereignisse in Erwägung ziehen, wenn sich der Wert einer Eigenschaft über externe Erzwingung ändert.

 Wenn sich ein Eigenschafts Wert über eine externe Kraft ändert (anders als durch Aufrufen von Methoden für das Objekt), geben Sie Ereignisse an den Entwickler an, dass sich der Wert ändert und sich geändert hat. Ein gutes Beispiel ist die- `Text` Eigenschaft eines Textfeld-Steuer Elements. Wenn der Benutzer Text in ein- `TextBox` Objekt eingibt, wird der-Eigenschafts Wert automatisch geändert.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Entwurfs Richtlinien für Member](member.md)
- [Framework-Entwurfs Richtlinien](index.md)
