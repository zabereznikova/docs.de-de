---
title: UriTemplate und UriTemplateTable
ms.date: 03/30/2017
ms.assetid: 5cbbe03f-4a9e-4d44-9e02-c5773239cf52
ms.openlocfilehash: 106ba21b58dabab96afbc8fb6db5cb305386f2fe
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595075"
---
# <a name="uritemplate-and-uritemplatetable"></a>UriTemplate und UriTemplateTable
Webentwickler müssen in der Lage sein, die Form und das Layout der URIs zu beschreiben, auf die ihre Dienste reagieren. Windows Communication Foundation (WCF) hat zwei neue Klassen hinzugefügt, um Entwicklern die Kontrolle über Ihre URIs zu verschaffen. <xref:System.UriTemplate>und <xref:System.UriTemplateTable> bilden die Basis des URI-basierten Dispatchmoduls in WCF. Diese Klassen können auch eigenständig verwendet werden, sodass Entwickler Vorlagen und den URI-Zuordnungsmechanismus nutzen können, ohne einen WCF-Dienst implementieren zu müssen.  
  
## <a name="templates"></a>Vorlagen  
 Eine Vorlage ist eine Möglichkeit, einen Satz relativer URIs zu beschreiben. Der Satz von URI-Vorlagen in der folgenden Tabelle zeigt, wie ein System, das verschiedene Arten von Wetterdaten abruft, definiert werden könnte.  
  
|Daten|Vorlage|  
|----------|--------------|  
|Nationale Vorhersage|Wetter/national|  
|Bundeslandvorhersage|Wetter/{Staat}|  
|Ortsvorhersage|Wetter/{Bundesland}/{Stadt}|  
|Aktivitätsvorhersage|Wetter/{Bundesland}/{Stadt}/{Aktivität}|  
  
 In dieser Tabelle wird ein Satz strukturell ähnlicher URIs beschrieben. Jeder Eintrag ist eine URI-Vorlage. Die Segmente in geschweiften Klammern beschreiben Variablen. Die Segmente, die nicht in geschweifte Klammern eingefasst sind, beschreiben Literalzeichenfolgen. Die WCF-Vorlagen Klassen ermöglichen es einem Entwickler, einen eingehenden URI zu akzeptieren, z. b. "/weather/WA/Seattle/Cycling", und ihn mit einer Vorlage zu vergleichen, die ihn beschreibt: "/Weather/{State}/{City}/{Activity}".  
  
## <a name="uritemplate"></a>UriTemplate  
 <xref:System.UriTemplate> ist eine Klasse, die eine URI-Vorlage kapselt. Der Konstruktor nimmt einen Zeichenfolgenparameter, der die Vorlage definiert. Diese Zeichenfolge enthält die Vorlage in dem im nächsten Abschnitt beschriebenen Format. Die <xref:System.UriTemplate>-Klasse bietet Methoden, die die Zuordnung eines eingehenden URI zu einer Vorlage, die Generierung eines URI aus einer Vorlage, das Abrufen einer Sammlung von Variablennamen, die in der Vorlage verwendet werden, die Bestimmung, ob zwei Vorlagen gleichwertig sind, und die Ausgabe der Zeichenfolge der Vorlage ermöglichen.  
  
 <xref:System.UriTemplate.Match%28System.Uri%2CSystem.Uri%29> nimmt eine Basisadresse und einen möglichen URI und versucht, den URI der Vorlage zuzuweisen. Wenn die Zuordnung erfolgreich ist, wird eine <xref:System.UriTemplateMatch>-Instanz zurückgegeben. Das <xref:System.UriTemplateMatch>-Objekt enthält einen Basis-URI, den möglichen URI, eine Name-Wert-Sammlung der Abfrageparameter, eine Matrix der Segmente des relativen Pfads, eine Name-Wert-Sammlung der Variablen, die zugeordnet wurden, die <xref:System.UriTemplate>-Instanz, die zum Durchführen der Zuordnung verwendet wurde, eine Zeichenfolge, die jeden nicht zugeordneten Teil des Kandidaten-URI enthält (wird verwendet, wenn die Vorlage über einen Platzhalter verfügt), und ein Objekt, das der Vorlage zugewiesen ist.  
  
> [!NOTE]
> Beim Vergleichen eines möglichen URIs mit einer Vorlage ignoriert die <xref:System.UriTemplate>-Klasse das Schema und die Portnummer.  
  
 Zum Generieren eines URI aus einer Vorlage stehen zwei Methoden zur Verfügung: <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> und <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29>. <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> akzeptiert eine Basisadresse und eine Name-Wert-Auflistung der Parameter. Wenn die Vorlage gebunden ist, werden diese Parameter durch Variablen ersetzt. <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29> akzeptiert die Name-Wert-Paare und ersetzt sie von links nach rechts.  
  
 <xref:System.UriTemplate.ToString> gibt die Vorlagenzeichenfolge zurück,  
  
 Die <xref:System.UriTemplate.PathSegmentVariableNames%2A>-Eigenschaft enthält eine Sammlung der Namen der Variablen, die innerhalb der Pfadsegmente in der Vorlagenzeichenfolge verwendet werden.  
  
 <xref:System.UriTemplate.IsEquivalentTo%28System.UriTemplate%29> akzeptiert <xref:System.UriTemplate> als Parameter und gibt einen booleschen Wert zurück, der angibt, ob die beiden Vorlagen gleichwertig sind. Weitere Informationen finden Sie im Abschnitt "Vorlagen Äquivalenz" weiter unten in diesem Thema.  
  
 <xref:System.UriTemplate> wurde für die Zusammenarbeit mit einem URI-Schema entwickelt, das der HTTP URI-Grammatik entspricht. Im Folgenden finden Sie Beispiele für unterstützte URI-Schemas:  
  
- `http://`  
  
- `https://`  
  
- `net.tcp://`  
  
- `net.pipe://`  
  
- `sb://`  
  
 Schemas wie "file://" und "urn://" entsprechen nicht der HTTP-URI-Grammatik und führen bei der Verwendung mit URI-Vorlagen zu unvorhersehbaren Ergebnissen.  
  
### <a name="template-string-syntax"></a>Vorlagenzeichenfolgen-Syntax  
 Eine Vorlage besteht aus drei Teilen: einem Pfad, einer optionalen Abfrage und einem optionalen Fragment. Ein Beispiel finden Sie in der folgenden Vorlage:  
  
`"/weather/{state}/{city}?forecast={length)#frag1`  
  
 Der Pfad besteht aus "/Wetter/{Bundesland}/{Ort}", die Abfrage besteht aus "?forecast={Länge}, und das Fragment besteht aus "#frag1."  
  
 Führende und nachstehende Schrägstriche sind im Pfadausdruck optional. Sowohl der Abfrage- als auch der Fragmentausdruck kann vollständig weggelassen werden. Ein Pfad besteht aus einer Reihe von Segmenten, die durch '/' getrennt sind, wobei jedes Segment einen Literalwert, einen Variablennamen (geschrieben in {geschweiften Klammern}) oder einen Platzhalter (geschrieben als ' \* ') aufweisen kann. In der vorherigen Vorlage ist das "\Wetter\"-Segment ein Literalwert, während "{Bundesland}" und "{Ort}" Variablen sind. Variablen nehmen Ihren Namen aus dem Inhalt Ihrer geschweiften Klammern und können später durch einen konkreten Wert ersetzt werden, um einen *geschlossenen URI*zu erstellen. Der Platzhalter ist optional, kann jedoch nur am Ende des URIs angezeigt werden, wo er "der restliche Pfad" logisch entspricht.  
  
 Der Abfrage Ausdruck gibt, sofern vorhanden, eine Reihe von ungeordneten Name-Wert-Paaren an, die durch ' & ' getrennt sind. Bei den Elementen des Abfrageausdrucks kann es sich entweder um Literalpaare (x=2) oder ein Variablenpaar (x={var}) handeln. Nur die rechte Seite der Abfrage kann einen variablen Ausdruck enthalten. ({someName} = {someValue} ist nicht zulässig. Ungepaarte Werte (?x) sind nicht zulässig. Es besteht kein Unterschied zwischen einem leeren Abfrageausdruck und einem Abfrageausdruck, der aus einem einzelnen "?" besteht (beide stehen für "jede Abfrage").  
  
 Der Fragmentausdruck kann aus einem Literalwert bestehen, Variablen sind nicht zulässig.  
  
 Alle Vorlagenvariablennamen innerhalb einer Vorlagenzeichenfolge müssen eindeutig sein. Bei Namen von Vorlagenvariablen wird die Groß- und Kleinschreibung nicht berücksichtigt.  
  
 Beispiele für gültige Vorlagenzeichenfolgen:  
  
- ""  
  
- "/Schuh"  
  
- "/Shoe/ \* "  
  
- "{Schuh}/Boot"  
  
- "{Schuh}/{Boat}/Bed/{Quilt}"  
  
- "Schuh/{Boots}"  
  
- "Schuh/{Boots}/ \* "  
  
- "Schuh/Boot? x = 2"  
  
- "Schuh/{Boot}? x = {Bed}"  
  
- "Schuh/{Boot}? x = {Bed} &y = Band"  
  
- "? x = {Schuh}"  
  
- "Schuh? x = 3&y = {var}  
  
 Beispiele für ungültige Vorlagenzeichenfolgen sind:  
  
- "{Schuh}/{Shoe}/x = 2" – doppelte Variablennamen.  
  
- "{Schuh}/Boat/? Bed = {Schuh}" – doppelte Variablennamen.  
  
- "? x = 2&x = 3" – Name/Wert-Paare innerhalb einer Abfrage Zeichenfolge müssen eindeutig sein, auch wenn Sie Literale sind.  
  
- "? x = 2&" – Abfrage Zeichenfolge ist falsch formatiert.  
  
- "? 2&x = {Schuh}" – Abfrage Zeichenfolge muss Name-Wert-Paare sein.  
  
- "? y = 2&&X = 3" – Abfrage Zeichenfolge muss Name-Wert-Paare sein, Namen dürfen nicht mit "&" beginnen.  
  
### <a name="compound-path-segments"></a>Zusammengesetzte Pfadsegmente  
 Bei zusammengesetzten Pfadsegmenten kann ein einzelnes URI-Pfadsegment mehrere Variablen sowie mit Literalwerten kombinierte Variablen enhalten. Im Folgenden finden Sie Beispiele für gültige zusammengesetzte Pfadsegmente:  
  
- /Dateiname.{Erw.}/  
  
- /{Dateiname}.jpg/  
  
- /{Dateiname}.{Erw.}/  
  
- /{a}.{b}Literalwert{c}({d})/  
  
 Im Folgenden finden Sie Beispiele für ungültige Pfadsegmente:  
  
- / {} -Variablen müssen benannt werden.  
  
- /{Schuh}{Boot} – Variablen müssen durch einen Literalwert getrennt werden.  
  
### <a name="matching-and-compound-path-segments"></a>Zuordnung und zusammengesetzte Pfadsegmente  
 Zusammengesetzte Pfadsegmente ermöglichen Ihnen das Definieren einer UriTemplate mit mehreren Variablen in nur einem Pfadsegment. Beispielsweise in der folgenden Vorlagen Zeichenfolge: "Adressen/{State}". {City} "zwei Variablen (State und City) werden innerhalb desselben Segments definiert. Diese Vorlage entspricht einer URL wie, `http://example.com/Washington.Redmond` aber Sie entspricht auch einer URL wie `http://example.com/Washington.Redmond.Microsoft` . Im letzteren Fall enthält die Zustands Variable "Washington", und die City-Variable enthält "Redmond. Microsoft". In diesem Fall entspricht jeder Text (mit Ausnahme von "/") der {city}-Variable. Wenn Sie eine Vorlage erstellen möchten, die nicht dem "zusätzlichen" Text entspricht, platzieren Sie die Variable in einem separaten Vorlagen Segment, z. b. "Adressen/{State}/{City}".  
  
### <a name="named-wildcard-segments"></a>Benannte Platzhaltersegmente  
 Ein benanntes Platzhalter Segment ist ein beliebiges Pfad Variablen Segment, dessen Variablenname mit dem Platzhalter Zeichen " \* " beginnt. Die folgende Vorlagenzeichenfolge enthält ein benanntes Platzhaltersegment mit dem Namen "Schuh".  
  
`"literal/{*shoe}"`  
  
 Für Platzhaltersegmente gelten die folgenden Regeln:  
  
- Für jede Vorlagenzeichenfolge kann höchstens ein benanntes Platzhaltersegment vorhanden sein.  
  
- Ein benanntes Platzhaltersegment muss sich im am weitesten rechts stehenden Segment des Pfads befinden.  
  
- Ein benanntes Platzhaltersegment kann nicht zusammen mit einem anonymen Platzhaltersegment innerhalb der gleichen Vorlagenzeichenfolge verwendet werden.  
  
- Der Name eines benannten Platzhaltersegments muss eindeutig sein.  
  
- Benannte Platzhaltersegmente können keine Standardwerte besitzen.  
  
- Benannte Platzhalter Segmente dürfen nicht auf "/" enden.  
  
### <a name="default-variable-values"></a>Standardvariablenwerte  
 Standardvariablenwerte ermöglichen das Angeben von Standardwerten für Variablen innerhalb einer Vorlage. Standardvariablen können mit den geschweiften Klammern, durch die die Variable deklariert wird, oder durch eine an den UriTemplate-Konstruktor weitergegebene Sammlung angegeben werden. Die folgende Vorlage zeigt zwei Möglichkeiten, eine <xref:System.UriTemplate> mit Variablen mit Standardwerten anzugeben:  
  
```csharp
UriTemplate t = new UriTemplate("/test/{a=1}/{b=5}");  
```  
  
 In dieser Vorlage werden die Variable `a` mit dem Standardwert `1` und die Variable `b` mit dem Standardwert `5` deklariert.  
  
> [!NOTE]
> Nur Pfadsegmentvariablen können Standardwerte besitzen. Bei Abfragezeichenfolgenvariablen, zusammengesetzten Segmentvariablen sowie bei benannten Platzhaltervariablen sind Standardwerte nicht zulässig.  
  
 Im folgenden Code wird die Behandlung von Standardvariablenwerten beim Abgleichen eines möglichen URI gezeigt:  
  
```csharp
Uri baseAddress = new Uri("http://localhost:8000/");

UriTemplate t = new UriTemplate("/{state=WA}/{city=Redmond}/", true);
Uri candidate = new Uri("http://localhost:8000/OR");

UriTemplateMatch m1 = t.Match(baseAddress, candidate);

Console.WriteLine($"Template: {t}");
Console.WriteLine($"Candidate URI: {candidate}");

// Display contents of BoundVariables
Console.WriteLine("BoundVariables:");
foreach (string key in m1.BoundVariables.AllKeys)
{
    Console.WriteLine($"\t{key}={m1.BoundVariables[key]}");
}
// The output of the above code is  
// Template: /{state=WA}/{city=Redmond}/
// Candidate URI: http://localhost:8000/OR
// BoundVariables:
//         STATE=OR
//         CITY=Redmond
```  
  
> [!NOTE]
> Ein URI, wie z `http://localhost:8000///` . b., stimmt nicht mit der im vorangehenden Code aufgelisteten Vorlage, jedoch mit einem URI wie z `http://localhost:8000/` . b..  
  
 Im folgenden Code wird die Behandlung von Standardvariablenwerten beim Erstellen eines URI mit einer Vorlage veranschaulicht:  
  
```csharp
Uri baseAddress = new Uri("http://localhost:8000/");  
Dictionary<string,string> defVals = new Dictionary<string,string> {{"a","1"}, {"b", "5"}};  
UriTemplate t = new UriTemplate("/test/{a}/{b}", defVals);  
NameValueCollection vals = new NameValueCollection();  
vals.Add("a", "10");  
  
Uri boundUri = t.BindByName(baseAddress, vals);  
Console.WriteLine("BaseAddress: {0}", baseAddress);  
Console.WriteLine("Template: {0}", t.ToString());  
  
Console.WriteLine("Values: ");  
foreach (string key in vals.AllKeys)  
{  
    Console.WriteLine("\tKey = {0}, Value = {1}", key, vals[key]);  
}  
Console.WriteLine("Bound URI: {0}", boundUri);  
  
// The output of the preceding code is  
// BaseAddress: http://localhost:8000/  
// Template: /test/{a}/{b}  
// Values:  
//     Key = a, Value = 10  
// Bound URI: http://localhost:8000/test/10/5  
```  
  
Erhält eine Variable den Standardwert `null`, gelten einige zusätzliche Einschränkungen. Eine Variable kann den Standardwert `null` besitzen, wenn sich die Variable im am weitesten rechts befindlichen Segment der Vorlagenzeichenfolge befindet oder wenn alle Segmente rechts des Segments jeweils den Standardwert `null` besitzen. Im Folgenden finden Sie gültige Vorlagenzeichenfolgen mit dem Standardwert `null`:  
  
- `UriTemplate t = new UriTemplate("shoe/{boat=null}");`

- `UriTemplate t = new UriTemplate("{shoe=null}/{boat=null}");`
  
- `UriTemplate t = new UriTemplate("{shoe=1}/{boat=null}");`

 Im folgenden sind ungültige Vorlagen Zeichenfolgen mit den Standardwerten von aufgeführt `null` :  
  
- `UriTemplate t = new UriTemplate("{shoe=null}/boat"); // null default must be in the right most path segment`
  
- `UriTemplate t = new UriTemplate("{shoe=null}/{boat=x}/{bed=null}"); // shoe cannot have a null default because boat does not have a default null value`

### <a name="default-values-and-matching"></a>Standardwerte und Vergleich  
 Beim Vergleichen eines möglichen URI mit einer Vorlage mit Standardwerten werden die Standardwerte in der <xref:System.UriTemplateMatch.BoundVariables%2A>-Sammlung platziert, wenn im möglichen URI keine Werte angegeben sind.  
  
### <a name="template-equivalence"></a>Vorlagenäquivalenz  
 Zwei Vorlagen werden als *strukturell äquivalent* bezeichnet, wenn alle Literale der Vorlage übereinstimmen und Sie Variablen in denselben Segmenten aufweisen. Beispielsweise sind die folgenden Vorlagen strukturell äquivalent:  
  
- /a/{var1}/b b/{var2}? x = 1&y = 2  
  
- a/{x}/b% 20b/{var1}? y = 2&x = 1  
  
- a/{y}/B% 20b/{z}/? y = 2&x = 1  
  
 Hierbei müssen noch einige Punkte beachtet werden:  
  
- Wenn eine Vorlage führende Schrägstriche enthält, wird nur der erste ignoriert.  
  
- Wenn Vorlagenzeichenfolgen auf strukturelle Äquivalenz verglichen werden, wird die Groß-/Kleinschreibungen bei den Variablennamen und Pfadsegmenten ignoriert; bei den Abfragezeichenfolgen muss sie beachtet werden.  
  
- Abfragezeichenfolgen sind unsortiert.  
  
## <a name="uritemplatetable"></a>UriTemplateTable  
 Die Klasse <xref:System.UriTemplateTable> stellt eine assoziative Tabelle aus <xref:System.UriTemplate>-Objekten dar, die an ein Objekt nach Wahl des Entwicklers gebunden sind. <xref:System.UriTemplateTable> muss vor Aufruf von <xref:System.UriTemplate> mindestens eine <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> enthalten. Der Inhalt einer <xref:System.UriTemplateTable> kann geändert werden, bis <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> aufgerufen wird. Die Überprüfung wird ausgeführt, wenn <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> aufgerufen wird. Der Typ der ausgeführten Validierung hängt vom Wert des Parameters `allowMultiple` zur <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> ab.  
  
 Wenn <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> bei Übergabe in `false` aufgerufen wird, überprüft die <xref:System.UriTemplateTable>, dass sich keine Vorlagen in der Tabelle befinden. Wenn strukturell äquivalente Vorlagen gefunden werden, wird eine Ausnahme ausgelöst. Dies wird zusammen mit <xref:System.UriTemplateTable.MatchSingle%28System.Uri%29> verwendet, wenn sichergestellt werden soll, dass nur eine Vorlage einem eingehenden URI entspricht.  
  
 Wenn <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> bei der Übergabe von `true` aufgerufen wird, lässt <xref:System.UriTemplateTable> mehrere strukturell äquivalente Vorlagen in einer <xref:System.UriTemplateTable> zu.  
  
 Wenn ein Satz <xref:System.UriTemplate>-Objekte, die einer <xref:System.UriTemplateTable> hinzugefügt sind, Abfragezeichenfolgen enthält, dürfen sie nicht mehrdeutig sein. Identische Abfragezeichenfolgen sind zulässig.  
  
> [!NOTE]
> Zwar lässt die <xref:System.UriTemplateTable> Basisadressen mit HTTP-fremden Schemas zu, Schema und Portnummer werden beim Vergleichen möglicher URIs mit Vorlagen jedoch ignoriert.  
  
### <a name="query-string-ambiguity"></a>Abfragezeichenfolgenmehrdeutigkeit  
 Vorlagen, die einen äquivalenten Pfad teilen, enthalten mehrdeutige Abfragezeichenfolgen, wenn es einen URI gibt, der mehr als einer Vorlage entspricht.  
  
 Die folgenden Sätze von Abfragezeichenfolgen sind in sich selbst eindeutig:  
  
- ?x=1  
  
- ?x=2  
  
- ?x=3  
  
- ? x = 1&y = {var}  
  
- ? x = 2&z = {var}  
  
- ?x=3  
  
- ?x=1  
  
- ?  
  
- ? x={var}  
  
- ?  
  
- ? m = Get&c = RSS  
  
- ? m = Put&c = RSS  
  
- ? m = Get&c = Atom  
  
- ? m = Put&c = Atom  
  
 Die folgenden Abfragezeichenfolgenvorlagen sind in sich selbst mehrdeutig:  
  
- ?x=1  
  
- ?x={var}  
  
 "x=1" – passt zu beiden Vorlagen.  
  
- ?x=1  
  
- ?y=2  
  
 "x = 1&y = 2" entspricht beiden Vorlagen. Das liegt daran, dass eine Abfragezeichenfolge mehr Abfragezeichenfolgen-Variablen enthalten kann als die Vorlage, zu der sie passt.  
  
- ?x=1  
  
- ? x = 1&y = {var}  
  
 "x = 1&y = 3" entspricht beiden Vorlagen.  
  
- ? x = 3&y = 4  
  
- ? x = 3&z = 5  
  
> [!NOTE]
> Die Zeichen "á" und "Á" gelten als unterschiedliche Zeichen, wenn sie als Teil eines URI-Pfads oder eines <xref:System.UriTemplate>-Pfadsegmentliterals verwendet werden. (Die Zeichen "a" und "A" gelten hingegen als gleich.) Die Zeichen á und Á gelten als gleiche Zeichen, wenn sie als Teil einer <xref:System.UriTemplate> {Variablenname} oder einer Abfragezeichenfolge erscheinen (a und A gelten ebenfalls als gleiche Zeichen).  
  
## <a name="see-also"></a>Weitere Informationen

- [Überblick über WCF-Web-HTTP-Programmiermodelle](wcf-web-http-programming-model-overview.md)
- [Objektmodell für WCF-Web-HTTP-Programmierung](wcf-web-http-programming-object-model.md)
- [UriTemplate](../samples/uritemplate-sample.md)
- [UriTemplate-Tabelle](../samples/uritemplate-table-sample.md)
- [UriTemplate-Tabellenverteiler](../samples/uritemplate-table-dispatcher-sample.md)
