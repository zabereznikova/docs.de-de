---
title: Leistungs Regeln (Code Analyse)
description: Erfahren Sie mehr über die Leistungs Regeln für die Code Analyse.
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.performancerules
helpviewer_keywords:
- rules, performance
- performance rules
- performance, rules
- managed code analysis rules, performance rules
author: gewarren
ms.author: gewarren
ms.openlocfilehash: 4409cc46eb73f13f8e59d7a51899da27035bb6af
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "96590680"
---
# <a name="performance-rules"></a>Leistungsregeln

Leistungs Regeln unterstützen Hochleistungs Bibliotheken und-Anwendungen.

## <a name="in-this-section"></a>In diesem Abschnitt

| Regel | Beschreibung |
| - | - |
| [CA1802: Nach Möglichkeit Literale verwenden.](ca1802.md) | Ein Feld wird als statisch und schreibgeschützt deklariert (in Visual Basic freigegeben und schreibgeschützt) und mit einem Wert initialisiert, der zur Kompilierzeit berechnet werden kann. Da der Wert, der dem Zielfeld zugewiesen ist, zur Kompilierzeit komprimiert werden kann, ändern Sie die Deklaration in ein Konstantenfeld (Konstantenin Visual Basic), sodass der Wert zur Kompilierzeit anstelle der Laufzeit berechnet wird. |
| [CA1805: nicht unnötig initialisieren](ca1805.md) | Die .NET-Laufzeit initialisiert alle Felder von Verweis Typen mit ihren Standardwerten, bevor der Konstruktor ausgeführt wird. In den meisten Fällen ist das explizite Initialisieren eines Felds auf seinen Standardwert redundant, wodurch Wartungskosten erhöht und die Leistung beeinträchtigt werden kann (z. b. mit erhöhter assemblygröße). |
| [CA1806: Methodenergebnisse nicht ignorieren.](ca1806.md) | Ein neues-Objekt wird erstellt, aber nie verwendet, oder eine Methode, die eine neue Zeichenfolge erstellt und zurückgibt, wird aufgerufen, und die neue Zeichenfolge wird nie verwendet, oder eine Component Object Model (com)-oder P/aufrufen-Methode gibt ein HRESULT oder einen Fehlercode zurück, das nie verwendet wird. |
| [CA1810: Statische Felder von Referenztypen inline initialisieren.](ca1810.md) | Wenn ein Typ einen expliziten statischen Konstruktor deklariert, überprüft der JIT-Compiler (Just in Time) jede statische Methode und jeden Instanzenkonstruktor des Typs. Dadurch wird sichergestellt, dass der statische Konstruktor zuvor aufgerufen wurde. Durch die Überprüfung statischer Konstruktoren kann die Leistung herabgesetzt werden. |
| [CA1812: Nicht instanziierte interne Klassen vermeiden.](ca1812.md) | Eine Instanz eines Typs auf Assemblyebene wird nicht durch Code in der Assembly erstellt. |
| [CA1813: Nicht versiegelte Attribute vermeiden.](ca1813.md) | .NET stellt Methoden zum Abrufen von benutzerdefinierten Attributen bereit. Standardmäßig wird mit diesen Methoden die Attributvererbungshierarchie durchsucht. Durch Verwendung eines versiegelten Attributs wird das Durchsuchen der Vererbungshierarchie unterbunden und die Leistung u. U. verbessert. |
| [CA1814: Jagged Arrays mehrdimensionalen Arrays vorziehen.](ca1814.md) | Ein verzweigtes Array ist ein Array, dessen Elemente wiederum Arrays sind. Die Arrays, aus denen die Elemente bestehen, können unterschiedlich groß sein, was zu weniger Verlust von Speicherplatz für einige Datenmengen führen kann. |
| [CA1815: Equals und Gleichheitsoperator für Werttypen überschreiben.](ca1815.md) | Bei Werttypen wird die Reflection-Bibliothek von der geerbten Implementierung von Equals verwendet und der Inhalt aller Felder verglichen. Reflection ist rechenintensiv, und das Überprüfen eines jeden Felds auf Gleichheit ist eventuell unnötig. Wenn Sie erwarten, dass die Benutzer Instanzen vergleichen oder sortieren bzw. dass sie die Instanzen als Schlüssel für Hashtabellen verwenden, sollte der Werttyp Equals implementieren. |
| [CA1819: Eigenschaften sollten keine Arrays zurückgeben.](ca1819.md) | Arrays, die von Eigenschaften zurückgegeben werden, sind nicht schreibgeschützt, auch wenn die Eigenschaft schreibgeschützt ist. Damit das Array gegen Manipulationen geschützt bleibt, muss die Eigenschaft eine Kopie des Arrays zurückgeben. Normalerweise verstehen die Benutzer nicht, welche negativen Auswirkungen der Aufruf einer solchen Eigenschaft auf die Leistung hat. |
| [CA1820: Mithilfe der Zeichenfolgenlänge auf leere Zeichenfolgen prüfen.](ca1820.md) | Der Vergleich von Zeichenfolgen mit der String.Length-Eigenschaft oder der String.IsNullOrEmpty-Methode führt erheblich schneller zu Ergebnissen als das Verwenden von Equals. |
| [CA1821: Leere Finalizer entfernen.](ca1821.md) | Finalizer sollten möglichst vermieden werden, da durch Verfolgung der Objektlebensdauer zusätzliche Leistung beansprucht wird. Ein leerer Finalizer verursacht zusätzlichen Aufwand ohne jeglichen Vorteil. |
| [CA1822: Member als statisch markieren.](ca1822.md) | Member, die nicht auf Instanzdaten oder Aufrufen von Instanzmethoden zugreifen, können als statisch gekennzeichnet werden (in Visual Basic freigegeben). Danach gibt der Compiler nicht virtuelle Aufrufsites an diese Member aus. Dies kann zu einer messbaren Leistungssteigerung für leistungsabhängigen Code führen. |
| [CA1823: Nicht verwendete private Felder vermeiden.](ca1823.md) | Es wurden private Felder erkannt, auf die in der Assembly anscheinend kein Zugriff erfolgt. |
| [CA1824: Assemblys mit NeutralResourcesLanguageAttribute markieren.](ca1824.md) | Das NeutralResourcesLanguage-Attribut informiert den Ressourcen-Manager der Sprache, die verwendet wurde, um die Ressourcen einer neutralen Kultur für eine Assembly anzuzeigen. Auf diese Weise wird die Suchleistung für die erste zu ladende Ressource verbessert und Ihr Workingset kann sich verkleinern. |
| [CA1825: Vermeiden Sie Arrayzuteilungen mit einer Länge von 0 (null).](ca1825.md) | Die Initialisierung eines Arrays der Länge 0 (null) führt zu einer unnötigen Speicher Belegung. Verwenden Sie stattdessen die statisch zugeordnete leere Array Instanz, indem Sie aufrufen <xref:System.Array.Empty%2A?displayProperty=nameWithType> . Die Speicher Belegung wird für alle Aufrufe dieser Methode freigegeben. |
| [CA1826: Eigenschaft anstelle der LINQ-Enumerable-Methode verwenden.](ca1826.md) | <xref:System.Linq.Enumerable> Die LINQ-Methode wurde für einen Typ verwendet, der eine äquivalente, effizientere Eigenschaft unterstützt. |
| [CA1827: Count/LongCount nicht verwenden, wenn Any verwendet werden kann.](ca1827.md) | <xref:System.Linq.Enumerable.Count%2A> die-Methode oder die- <xref:System.Linq.Enumerable.LongCount%2A> Methode wurde verwendet, wenn die <xref:System.Linq.Enumerable.Any%2A> Methode effizienter wäre. |
| [CA1828: CountAsync/LongCountAsync nicht verwenden, wenn AnyAsync verwendet werden kann.](ca1828.md) | <xref:Microsoft.EntityFrameworkCore.EntityFrameworkQueryableExtensions.CountAsync%2A> die-Methode oder die- <xref:Microsoft.EntityFrameworkCore.EntityFrameworkQueryableExtensions.LongCountAsync%2A> Methode wurde verwendet, wenn die <xref:Microsoft.EntityFrameworkCore.EntityFrameworkQueryableExtensions.AnyAsync%2A> Methode effizienter wäre. |
| [CA1829: Length/Count-Eigenschaft anstelle der Enumerable.Count-Methode verwenden.](ca1829.md) | <xref:System.Linq.Enumerable.Count%2A> Die LINQ-Methode wurde für einen Typ verwendet, der eine äquivalente, effizientere oder-Eigenschaft unterstützt `Length` `Count` . |
| [CA1830: Bevorzugen Sie stark typisierte Append- und Insert-Methodenüberladungen für StringBuilder.](ca1830.md) | <xref:System.Text.StringBuilder.Append%2A> und <xref:System.Text.StringBuilder.Insert%2A> Stellen über Ladungen für mehrere Typen bereit, die über System. String hinausgehen.  Bevorzugen Sie nach Möglichkeit die stark typisierten über Ladungen über die Verwendung von ToString () und der Zeichen folgen basierten Überladung. |
| [CA1831: Verwenden Sie für Zeichenfolgen bei Bedarf anstelle von Range-basierten Indexern „AsSpan“.](ca1831.md) | Wenn Sie einen Range-Indexer für eine Zeichenfolge verwenden und den Wert implizit einem "Read onlyspan"- &lt; Char- &gt; Typ zuweisen, wird die-Methode <xref:System.String.Substring%2A?#System_String_Substring_System_Int32_System_Int32_> anstelle von verwendet <xref:System.Span%601.Slice%2A?#System_Span_1_Slice_System_Int32_System_Int32_> , wodurch eine Kopie des angeforderten Teils der Zeichenfolge erzeugt wird. |
| [CA1832: Verwenden Sie „AsSpan“ oder „AsMemory“ anstelle von Range-basierten Indexern zum Abrufen eines ReadOnlySpan- oder ReadOnlyMemory-Teils eines Arrays.](ca1832.md) | Wenn Sie einen Range-Indexer für ein Array verwenden und den Wert implizit einem- <xref:System.ReadOnlySpan%601> oder- <xref:System.ReadOnlyMemory%601> Typ zuweisen, wird die-Methode <xref:System.Runtime.CompilerServices.RuntimeHelpers.GetSubArray%2A> anstelle von verwendet <xref:System.Span%601.Slice%2A?#System_Span_1_Slice_System_Int32_System_Int32_> , wodurch eine Kopie des angeforderten Teils des Arrays erzeugt wird. |
| [CA1833: Verwenden Sie „AsSpan“ oder „AsMemory“ anstelle von Range-basierten Indexern zum Abrufen eines Span- oder Memory-Teils eines Arrays.](ca1833.md) | Wenn Sie einen Range-Indexer für ein Array verwenden und den Wert implizit einem- <xref:System.Span%601> oder- <xref:System.Memory%601> Typ zuweisen, wird die-Methode <xref:System.Runtime.CompilerServices.RuntimeHelpers.GetSubArray%2A> anstelle von verwendet <xref:System.Span%601.Slice%2A?#System_Span_1_Slice_System_Int32_System_Int32_> , wodurch eine Kopie des angeforderten Teils des Arrays erzeugt wird. |
| [CA1834: Verwenden von StringBuilder.Append(char) für Zeichenfolgen mit einem einzelnen Zeichen](ca1834.md) | <xref:System.Text.StringBuilder> verfügt über eine-Überladung `Append` , die einen `char` als sein Argument annimmt. Bevorzugen Sie die `char` Überladung, um die Leistung zu verbessern |
| [CA1835: bevorzugen Sie die "Memory"-basierten über Ladungen für "Read Async" und "schreiteasync".](ca1835.md) | ' Stream ' weist eine ' Schreib async '-Überladung auf, die ein ' Memory &lt; Byte &gt; ' als erstes Argument annimmt, und eine ' schreiteasync '-Überladung, die ein ' Read onlymemory &lt; Byte &gt; ' als erstes Argument annimmt. Bevorzugen Sie das Aufrufen der Speicher basierten über Ladungen, die effizienter sind. |
| [CA1836: bevorzugen `IsEmpty` , `Count` Wenn verfügbar](ca1836.md) | Bevorzugt eine `IsEmpty` Eigenschaft, die effizienter ist als `Count` , oder, `Length` <xref:System.Linq.Enumerable.Count%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> <xref:System.Linq.Enumerable.LongCount%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> um zu bestimmen, ob das Objekt Elemente enthält oder nicht. |
| [CA1837: Verwenden Sie `Environment.ProcessId` anstelle von. `Process.GetCurrentProcess().Id`](ca1837.md) | `Environment.ProcessId` ist einfacher und schneller als `Process.GetCurrentProcess().Id` . |
| [CA1838: `StringBuilder` Parameter für P/Aufrufe vermeiden](ca1838.md) | Beim Marshalling von `StringBuilder` wird immer eine native Puffer Kopie erstellt, was zu mehreren Zuordnungen für einen marshallingvorgang führt. |
