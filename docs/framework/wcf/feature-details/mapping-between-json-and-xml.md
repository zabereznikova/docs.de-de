---
title: Zuordnung zwischen JSON und XML
ms.date: 03/30/2017
ms.assetid: 22ee1f52-c708-4024-bbf0-572e0dae64af
ms.openlocfilehash: 0dbe37a07024ae70e574b92582715d2d2ef52e5c
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212086"
---
# <a name="mapping-between-json-and-xml"></a>Zuordnung zwischen JSON und XML
Die von der <xref:System.Runtime.Serialization.Json.JsonReaderWriterFactory> erzeugten Reader und Writer stellen eine XML API über JSON (JavaScript Object Notation)-Inhalte bereit. JSON codiert Daten mit einer Teilmenge der Objektliterale von JavaScript. Die von dieser Factory erstellten Reader und Writer werden auch verwendet, wenn JSON-Inhalte von Windows Communication Foundation (WCF)-Anwendungen mithilfe der <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement> oder des <xref:System.ServiceModel.WebHttpBinding>gesendet oder empfangen werden.

Wenn der JSON-Reader mit JSON-Inhalten initialisiert wird, verhält er sich so wie ein XML-Reader bei XML-Inhalten. Wenn dem JSON-Writer eine Aufruffolge übergeben wird, die bei einem textbasierten XML-Reader eine bestimmte XML-Instanz erzeugt, wird JSON-Inhalt ausgegeben. Die Zuordnung zwischen dieser XML-Instanz und dem JSON-Inhalt wird in diesem Thema für die Verwendung in fortgeschrittenen Szenarios beschrieben.

Intern wird JSON als XML-Infoset dargestellt, wenn es von WCF verarbeitet wird. Normalerweise müssen Sie sich nicht mit dieser internen Darstellung befassen, da es sich lediglich um eine logische Zuordnung handelt: JSON wird normalerweise nicht im physischen Speicher in XML konvertiert bzw. XML wird nicht physisch in JSON umgewandelt. Diese Zuordnung bedeutet, dass über XML-APIs auf JSON-Inhalte zugegriffen wird.

Wenn WCF JSON verwendet, besteht das übliche Szenario darin, dass die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> automatisch durch das <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> Verhalten oder das <xref:System.ServiceModel.Description.WebHttpBehavior> Verhalten bei Bedarf eingebunden wird. Der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> kennt die Zuordnung zwischen JSON und dem XML-Infoset und gibt vor, den JSON-Inhalt direkt zu verarbeiten. (Der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> kann mit jedem beliebigen XML-Reader oder -Writer verwendet werden, sofern der XML-Inhalt der folgenden Zuordnung entspricht.)

In fortgeschrittenen Szenarios wird es möglicherweise notwendig, direkt auf die folgende Zuordnung zuzugreifen. Diese Szenarios sind gegeben, wenn Sie JSON mit einem benutzerdefinierten Verfahren serialisieren und deserialisieren möchten, ohne auf den <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> zurückzugreifen, oder wenn der <xref:System.ServiceModel.Channels.Message>-Typ bei Nachrichten, die JSON enthalten, direkt verarbeitet wird. Die JSON-XML-Zuordnung wird auch zur Nachrichtenprotokollierung verwendet. Wenn das Nachrichten Protokollierungs Feature in WCF verwendet wird, werden JSON-Nachrichten gemäß der im nächsten Abschnitt beschriebenen Zuordnung als XML protokolliert.

Das folgende Beispiel eines JSON-Dokuments soll zur Klärung dessZuordnungskonzepts dienen:

```json
{"product":"pencil","price":12}
```

Um dieses JSON-Dokument mit einem der oben erwähnten Reader zu lesen, verwenden Sie die gleiche Sequenz von <xref:System.Xml.XmlDictionaryReader>-Aufrufen, die Sie zum Lesen des folgenden XML-Dokuments verwenden würden:

```xml
<root type="object">
    <product type="string">pencil</product>
    <price type="number">12</price>
</root>
```

Wenn außerdem die JSON-Nachricht im Beispiel von WCF empfangen und protokolliert wird, wird das XML-Fragment im vorangehenden Protokoll angezeigt.

## <a name="mapping-between-json-and-the-xml-infoset"></a>Zuordnung zwischen JSON und dem XML-Infoset

Formal erfolgt die Zuordnung zwischen JSON, wie in [RFC 4627](https://www.ietf.org/rfc/rfc4627.txt) beschrieben (es sei denn, bestimmte Einschränkungen sind gelockert und bestimmte weitere Einschränkungen hinzugefügt), und das XML-Infoset (und nicht der Text-XML), wie in [XML-Informations Satz](https://www.w3.org/TR/2004/REC-xml-infoset-20040204/)beschrieben. Informationen zu den Definitionen von *Informations Elementen* und Feldern in [eckige Klammern] finden Sie in diesem Thema.

Ein leeres JSON-Dokument wird einem leeren XML-Dokument zugeordnet, und ein leeres XML-Dokument wird einem leeren JSON-Dokument zugeordnet. Bei der Zuordnung von XML zu JSON sind vorangehende Leerräume und nachfolgende Leerzeichen nach dem Dokument nicht zulässig.

Die Zuordnung wird zwischen einem Dokumentinformationselement (Document Information Item, DII) oder einem Elementinformationselement (Element Information Item, EII) und JSON definiert. Das EII bzw. die [document element]-Eigenschaft des DII wird als JSON-Stammelement bezeichnet. Beachten Sie das, dass Dokumentfragmente (XML mit mehreren Stammelementen) nicht von dieser Zuordnung unterstützt werden.

Beispiel: Sowohl für das folgende Dokument:

```xml
<?xml version="1.0"?>
<root type="number">42</root>
```

als auch für das folgende Element:

```xml
<root type="number">42</root>
```

ist eine Zuordnung zu JSON definiert. Das <`root`>-Element ist in beiden Fällen das JSON-Stamm Element.

Weiterhin ist im Fall eines DII Folgendes zu berücksichtigen:

- Einige Elemente dürfen in der [children]-Liste nicht vorhanden sein. Verlassen Sie sich beim Lesen von XML, das aus einer Zuordnung von JSON stammt, nicht auf diese Tatsache.

- Die [children]-Liste enthält keine Kommentarinformationselemente.

- Die [children]-Liste enthält keine DTD-Informationselemente.

- Die [children]-Liste enthält keine Informationselemente (Personal Information, PI) (die `<?xml…>` Deklaration wird nicht als PI-Informationselement angesehen).

- Der [notations]-Satz ist leer.

- Der [unparsed entities]-Satz ist leer.

Beispiel: Das folgende Dokument kann JSON nicht zugeordnet werden, weil die [children]-Liste ein PI und einen Kommentar enthält.

```xml
<?xml version="1.0"?>
<!--comment--><?pi?>
<root type="number">42</root>
```

Das EII für das JSON-Stammelement verfügt über folgende Eigenschaften:

- [local name] hat den Wert "root".

- [namespace name] hat keinen Wert.

- [prefix] hat keinen Wert.

- [children] kann entweder EIIs (die innere Elemente darstellen, die an späterer Stelle näher beschrieben werden) oder CIIs (Character Information Items (Zeicheninformationselemente, die an späterer Stelle näher beschrieben werden) oder keines dieser Elemente enthalten, jedoch nicht beide Elementtypen.

- [Attribute] kann die folgenden optionalen Attributinformationselemente (AIIs) enthalten.

- Das JSON-Typattribut ("type"), das an späterer Stelle näher beschrieben wird. Dieses Attribut wird verwendet, um den JSON-Typ (String, Zahl, Boolean, Objekt, Array oder NULL) im zugeordneten XML beizubehalten.

- Das Name-Attribut des Daten Vertrags ("\_\_Type"), wie weiter unten beschrieben. Dieses Attribut kann nur angegeben werden, wenn auch das JSON-Typattribut angegeben wurde und dessen [normalized value] gleich "object" ist. Dieses Attribut wird vom `DataContractJsonSerializer` verwendet, um die Typinformationen des Datenvertrags beizubehalten, beispielsweise in polymorphen Fällen, in denen ein abgeleiteter Typ serialisiert und ein Basistyp erwartet wird. Wenn Sie nicht mit dem `DataContractJsonSerializer` arbeiten, wird dieses Attribut wird meist ignoriert.

- [in-scope-Namespaces] enthält die Bindung von "XML", die von der Infosetspezifikation als vorgeschrieben `http://www.w3.org/XML/1998/namespace` wird.

- [children], [attributes] und [in-scope namespaces] dürfen keine anderen Elemente als die oben genannten enthalten, und [namespace attributes] darf keine Member enthalten. Sie dürfen sich beim Lesen von XML, das aus einer Zuordnung von JSON erzeugt wurde, aber nicht darauf verlassen, dass dies zutrifft.

Beispiel: Das folgende Dokument lässt sich JSON nicht zuordnen, weil [namespace attributes] nicht leer ist.

```xml
<?xml version="1.0"?>
<root xmlns:a="myattributevalue">42</root>
```

Das AII für das JSON-Typattribut verfügt über folgende Eigenschaften:

- [namespace name] hat keinen Wert.
- [prefix] hat keinen Wert.
- [local name] lautet "type".
- [normalized value] enthält einen der möglichen Typwerte, die im folgenden Abschnitt beschrieben werden.
- [specified] hat den Wert `true`.
- [attribute type] hat keinen Wert.
- [references] hat keinen Wert.

Das AII für das Datenvertragsnamensattribut verfügt über folgende Eigenschaften:

- [namespace name] hat keinen Wert.
- [prefix] hat keinen Wert.
- [local name] ist "\_\_Type" (zwei Unterstriche und dann "Type").
- [normalized value] kann jede gültige Unicode-Zeichenfolge enthalten. Die Zuordnung dieser Zeichenfolge zu JSON wird im folgenden Abschnitt beschrieben.
- [specified] hat den Wert `true`.
- [attribute type] hat keinen Wert.
- [references] hat keinen Wert.

Innere Elemente innerhalb des JSON-Stammelements oder andere innere Elemente verfügen über die folgenden Eigenschaften:

- [local name] kann einen beliebigen Wert aufweisen, wie weiter unten beschrieben.
- Für [namespace name], [prefix], [children], [attributes], [namespace attributes] und [in-scope namespaces] gelten die gleichen Regeln wie für das JSON-Stammelement.

Sowohl im JSON-Stammelement als auch in den inneren Elementen definiert das JSON-Typattribut die Zuordnung zu JSON und den möglichen [children]-Elementen und deren Interpretation. Beim [normalized value] des Attributs muss die Groß-/Kleinschreibung beachtet werden, und es muss ein Kleinbuchstabe und kein Leerraum enthalten sein.

|[normalisierter Wert] des JSON-typattributs AII|Zulässige [children]-Elemente des entsprechenden EII|Zuordnung zu JSON|
|---------------------------------------------------------|---------------------------------------------------|---------------------|
|`string` (oder Fehlen des JSON-Typs AII)<br /><br /> Ein `string` und das Fehlen des JSON- TypsAII sind gleichbedeutend, und somit ist `string` der Standard.<br /><br /> Deshalb wird `<root> string1</root>``string` in JSON dem  "string1" zugeordnet.|0 (null) oder mehr CIIs|Eine `string` in JSON (JSON RFC, Abschnitt 2.5). Jedes `char` ist ein Zeichen, das dem im CII angegebenen [character code] entspricht. Wenn keine CIIs vorhanden sind, wird eine leere JSON-`string` zugeordnet.<br /><br /> Beispiel: Das folgende Element wird einem JSON-Fragment zugeordnet.<br /><br /> `<root type="string">42</root>`<br /><br /> Das JSON-Fragment lautet "42".<br /><br /> Bei der Zuordnung von XML zu JSON müssen Zeichen, denen ein Escapezeichen vorangestellt werden muss, Escapezeichen zugeordnet werden. Alle anderen Zeichen werden Zeichen zugeordnet, denen keine Escapezeichen voransteht. Das Zeichen "/" ist eine besondere – es wird mit Escapezeichen versehen, auch wenn es nicht als "\\/" geschrieben werden muss.<br /><br /> Beispiel: Das folgende Element wird einem JSON-Fragment zugeordnet.<br /><br /> `<root type="string">the "da/ta"</root>`<br /><br /> Das JSON-Fragment ist "The \\" da\\/Ta\\"".<br /><br /> Bei der Zuordnung von JSON zu XML werden Zeichen, denen ein Escapezeichen vorangestellt ist, und andere Zeichen ohne Escapezeichen dem entsprechenden [character code] richtig zugeordnet.<br /><br /> Beispiel: Das JSON-Fragment "\u0041BC" entspricht dem folgenden XML-Element.<br /><br /> `<root type="string">ABC</root>`<br /><br /> Die Zeichenfolge kann von Leerraum (' WS ' in Abschnitt 2 der JSON-RFC) umgeben werden, der nicht XML zugeordnet wird.<br /><br /> Beispiel: Das JSON-Fragment           "ABC", (es enthält Leerräume vor dem ersten Anführungszeichen), entspricht dem folgenden XML-Element.<br /><br /> `<root type="string">ABC</root>`<br /><br /> Alle Leerzeichen in XML werden Leerzeichen in JSON zugeordnet.<br /><br /> Beispiel: Das folgende XML-Element wird einem JSON-Fragment zugeordnet.<br /><br /> `<root type="string">  A BC      </root>`<br /><br /> Das JSON-Fragment lautet " A BC ".|
|`number`|1 oder mehr CIIs|Eine JSON-`number` (JSON RFC, Abschnitt 2,4), die möglicherweise von Leerraum umgeben ist. Jedes Zeichen in der Kombination aus Anzahl und Leerzeichen ist ein Zeichen, das dem [Zeichencode] aus dem CII entspricht.<br /><br /> Beispiel: Das folgende Element wird einem JSON-Fragment zugeordnet.<br /><br /> `<root type="number">    42</root>`<br /><br /> Das JSON-Fragment lautet    42.<br /><br /> (Leerraum wird beibehalten).|
|`boolean`|4 oder 5 CIIs (entspricht `true` oder `false`), möglicherweise umgeben von zusätzlichen Leerraum-CIIs.|Eine CII-Folge, die der Zeichenfolge TRUE entspricht, wird dem Literal `true` zugeordnet, und eine CII-Folge, die der Zeichenfolge FALSE entspricht, wird dem Literal `false` zugeordnet. Umgebende Leerraum wird beibehalten.<br /><br /> Beispiel: Das folgende Element wird einem JSON-Fragment zugeordnet.<br /><br /> `<root type="boolean"> false</root>`<br /><br /> Der JSON-Fragement lautet `false`.|
|`null`|Keine Elemente zulässig.|Das Literal `null`. Bei der Zuordnung von JSON zu XML kann die `null` von Leerraum ("WS" in Abschnitt 2) umgeben sein, der nicht XML zugeordnet wird.<br /><br /> Beispiel: Das folgende Element wird einem JSON-Fragment zugeordnet.<br /><br /> `<root type="null"/>`<br /><br /> oder<br /><br /> `<root type="null"></root>`<br /><br /> :<br /><br /> In beiden Fällen lautet das JSON-Fragement `Null`.|
|`object`|0 oder mehr EIIs.|Eine `begin-object` (linke geschweifte Klammer) wie in Abschnitt&#160;2.2 des JSON RFC definiert, gefolgt von einem Memberdatensatz für jedes EII, wie an späterer Stelle näher beschrieben wird. Wenn mehr als ein EII vorhanden ist, werden die Memberdatensätze durch Trennzeichen (Kommas) voneinander getrennt. Abgeschlossen wird die Angabe durch ein end-object (rechte geschweifte Klammer).<br /><br /> Beispiel: Das folgende Element wird dem JSON-Fragment zugeordnet.<br /><br /> `<root type="object">`<br /><br /> `<type1 type="string">aaa\</type1>`<br /><br /> `<type2 type="string">bbb\</type2>`<br /><br /> `</root >`<br /><br /> Der JSON-Fragement lautet `{"type1":"aaa","type2":"bbb"}`.<br /><br /> Wenn das Attribut für den Datenvertragstyp in der Zuordnung von XML zu JSON angegeben wird, dann wird am Anfang ein zusätzlicher Memberdatensatz hinzugefügt. Der Name ist der [local name] des Daten Vertrags Type-Attributs ("\_\_Type"), und sein Wert ist der [normalisierte Wert] des Attributs. Umgekehrt ist bei der Zuordnung von JSON zu XML, wenn der Name des ersten Element Datentyps der [local name] des Daten Vertragstyp-Attributs ist (d. h. "\_\_-Typ"), ein entsprechendes Daten Vertragstyp Attribut in der zugeordneten XML-Datei vorhanden, aber ein entsprechendes EII ist nicht vorhanden. Beachten Sie, dass dieser Memberdatensatz als erster Datensatz im JSON-Objekt enthalten sein muss, damit diese spezielle Zuordnung erfolgen kann. Dies stellt eine Abweichung von der üblichen JSON-Verarbeitung dar, in der die Reihenfolge von Memberdatensätzen nicht von Bedeutung ist.<br /><br /> Beispiel:<br /><br /> Das folgende JSON-Fragment wird XML zugeordnet.<br /><br /> `{"__type":"Person","name":"John"}`<br /><br /> Der folgende Code stellt das XML dar:<br /><br /> `<root type="object" __type="Person">   <name type="string">John</name> </root>`<br /><br /> Beachten Sie, dass der \_\_Typ AII vorhanden ist, aber es gibt keine \_\_Typ EII.<br /><br /> Wenn die Reihenfolge in JSON umgekehrt wird, wie im folgenden Beispiel gezeigt,<br /><br /> `{"name":"John","\_\_type":"Person"}`<br /><br /> lautet das entsprechende XML wie folgt:<br /><br /> `<root type="object">   <name type="string">John</name>   <__type type="string">Person</__type> </root>`<br /><br /> Dies bedeutet, dass \__Type keine besondere Bedeutung hat und wie üblich einer EII zugeordnet ist, nicht AII.<br /><br /> Für das [normalized value]-Element von AII gelten für die Verwendung von Escapezeichen bei der Zuordnung zu JSON-Werten die gleichen Regeln wie bei der Zuordnung zu JSON-Zeichenfolgen. Diese Regeln sind in der Zeile "string" dieser Tabelle angegeben.<br /><br /> Beispiel:<br /><br /> `<root type="object" __type="\abc" />`<br /><br /> aus dem vorigen Beispiel kann dem folgenden JSON zugeordnet werden.<br /><br /> `{"__type":"\\abc"}`<br /><br /> Bei einer XML-zu-JSON-Zuordnung darf der erste EII [local name] nicht "\_\_Type" lauten.<br /><br /> Leerräume (`ws`) werden nie bei der Zuordnung von XML zu JSON für-Objekte generiert und bei der Zuordnung von JSON zu XML ignoriert.<br /><br /> Beispiel: Das folgende JSON-Fragment wird einem XML-Element zugeordnet.<br /><br /> `{ "ccc" : "aaa", "ddd" :"bbb"}`<br /><br /> Das XML-Element wird im folgenden Code dargestellt.<br /><br /> `<root type="object">    <ccc type="string">aaa</ccc>    <ddd type="string">bbb</bar> </root >`|
|-Array|0 oder mehr EIIs|Ein begin-Array (linke eckige Klammer) entsprechend Abschnitt&#160;2.3 des JSON&#160;RFC, gefolgt von einem Arraydatensatz für jedes EII, wie an späterer Stelle näher beschrieben wird. Wenn mehr als ein EII vorhanden ist, werden die Arraydatensätze durch Trennzeichen (Kommas) voneinander getrennt. Abgeschlossen wird dies durch ein end-Array.<br /><br /> Beispiel: Das folgende XML-Element wird einem JSON-Fragment zugeordnet.<br /><br /> `<root type="array"/>    <item type="string">aaa</item>    <item type="string">bbb</item> </root >`<br /><br /> Das JSON-Fragment ist `["aaa","bbb"]`<br /><br /> Leerräume (`ws`) werden nie bei der Zuordnung von XML zu JSON für Arrays generiert und bei der Zuordnung von JSON zu XML ignoriert.<br /><br /> Beispiel: ein JSON-Fragment.<br /><br />`["aaa", "bbb"]`<br /><br /> Das XML-Element, das ihm zugeordnet wird.<br /><br /> `<root type="array"/>    <item type="string">aaa</item>    <item type="string">bbb</item> </root >`|

Memberdatensätze werden wie folgt verarbeitet:

- Das [local name]-Element des inneren Elements wird entsprechend Abschnitt&#160;2.2 des JSON&#160;RFC dem `string`-Teil des `member` zugeordnet.

Beispiel: Das folgende Element wird einem JSON-Fragment zugeordnet.

```xml
<root type="object"/>
<myLocalName type="string">aaa</myLocalName>
</root >
```

Das folgende JSON-Fragment wird angezeigt:

```json
{"myLocalName":"aaa"}
```

- Bei der Zuordnung von XML zu JSON müssen Zeichen, denen in JSON ein Escapezeichen vorangestellt werden muss, Escapezeichen zugeordnet werden. Alle anderen Zeichen werden Zeichen zugeordnet, denen kein Escapezeichen voransteht. Das Zeichen "/" ist ein Sonderfall. Ihm wird ein Escapezeichen vorangestellt, obwohl dies nicht notwendig ist. (Bei der Zuordnung von JSON zu XML muss ihm kein Escapezeichen vorangestellt werden.) Dies ist erforderlich, damit das ASP.NET&#160;AJAX-Format für `DateTime`-Daten in JSON unterstützt wird.

- Bei einer Zuordnung von JSON zu XML werden alle Zeichen (einschließlich der Zeichen ohne Escapezeichen, falls erforderlich) zur Bildung eines `string`-Werts herangezogen, der ein [local name]-Element ergibt.

- Innere Elemente [children] werden entsprechend dem `JSON Type Attribute` ebenso wie beim `Root JSON Element` dem Wert in Abschnitt&#160;2.2 zugeordnet. Es sind mehrere Schachtelungsebenen von EIIs (einschließlich der Schachtelung innerhalb von Arrays) zulässig.

Beispiel: Das folgende Element wird einem JSON-Fragment zugeordnet.

```xml
<root type="object">
    <myLocalName1 type="string">myValue1</myLocalName1>
    <myLocalName2 type="number">2</myLocalName2>
    <myLocalName3 type="object">
        <myNestedName1 type="boolean">true</myNestedName1>
        <myNestedName2 type="null"/>
    </myLocalName3>
</root >
```

Das folgende JSON-Fragment resultiert aus dieser Zuordnung:

```json
{"myLocalName1":"myValue1","myLocalName2":2,"myLocalName3":{"myNestedName1":true,"myNestedName2":null}}
```

> [!NOTE]
> Die vorangehende Zuordnung umfasst keinen XML-Codierungsschritt. Daher unterstützt WCF nur JSON-Dokumente, in denen alle Zeichen in Schlüsselnamen gültige Zeichen in XML-Elementnamen sind. Beispielsweise wird das JSON-Dokument {"<": "a"} nicht unterstützt, da < kein gültiger Name für ein XML-Element ist.

Der umgekehrte Fall (Zeichen, die in XML, aber nicht in JSON zulässig sind) stellt kein Problem dar, weil die vorangehende Zuordnung Schritte für das Voranstellen bzw. Entfernen von Escapezeichen in JSON beinhaltet.

Arraydatensätze werden wie folgt verarbeitet:

- [local name] des inneren Elements lautet "item".

- Das [children]-Element des inneren Elements wird entsprechend dem JSON-Attribut ebenso wie beim JSON-Stammelement dem Wert in Abschnitt&#160;2.3 zugeordnet. Es sind mehrere Schachtelungsebenen von EIIs (einschließlich der Schachtelung innerhalb von Objekten) zulässig.

Beispiel: Das folgende Element wird einem JSON-Fragment zugeordnet.

```xml
<root type="array"/>
    <item type="string">myValue1</item>
    <item type="number">2</item>
    <item type="array">
    <item type="boolean">true</item>
    <item type="null"/></item>
</root >
```

Nachfolgend wird das JSON-Fragment dargestellt.

```json
["myValue1",2,[true,null]]
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Serialization.Json.JsonReaderWriterFactory>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>
- [Eigenständige JSON-Serialisierung.](stand-alone-json-serialization.md)
