---
title: Zuordnung zwischen JSON und XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22ee1f52-c708-4024-bbf0-572e0dae64af
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9bf104af8c88413298412d3ec3a29cd934558e2d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="mapping-between-json-and-xml"></a>Zuordnung zwischen JSON und XML
Die von der <xref:System.Runtime.Serialization.Json.JsonReaderWriterFactory> erzeugten Reader und Writer stellen eine XML API über JSON (JavaScript Object Notation)-Inhalte bereit. JSON codiert Daten mit einer Teilmenge der Objektliterale von JavaScript. Die von dieser Factory erzeugten Reader und Writer werden auch verwendet, wenn JSON-Inhalte von einer [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Anwendung über ein <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement> oder eine <xref:System.ServiceModel.WebHttpBinding> gesendet oder empfangen werden.  
  
 Wenn der JSON-Reader mit JSON-Inhalten initialisiert wird, verhält er sich so wie ein XML-Reader bei XML-Inhalten. Wenn dem JSON-Writer eine Aufruffolge übergeben wird, die bei einem textbasierten XML-Reader eine bestimmte XML-Instanz erzeugt, wird JSON-Inhalt ausgegeben. Die Zuordnung zwischen dieser XML-Instanz und dem JSON-Inhalt wird in diesem Thema für die Verwendung in fortgeschrittenen Szenarios beschrieben.  
  
 Bei der Verarbeitung durch [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] wird JSON intern als XML-Infoset dargestellt. Normalerweise müssen Sie sich nicht mit dieser internen Darstellung befassen, da es sich lediglich um eine logische Zuordnung handelt: JSON wird normalerweise nicht im physischen Speicher in XML konvertiert bzw. XML wird nicht physisch in JSON umgewandelt. Diese Zuordnung bedeutet, dass über XML-APIs auf JSON-Inhalte zugegriffen wird.  
  
 Wenn JSON in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet wird, wird im üblichen Szenario gegebenenfalls <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> automatisch vom <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>-Verhalten bzw. vom <xref:System.ServiceModel.Description.WebHttpBehavior>-Verhalten eingebunden. Der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> kennt die Zuordnung zwischen JSON und dem XML-Infoset und gibt vor, den JSON-Inhalt direkt zu verarbeiten. (Der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> kann mit jedem beliebigen XML-Reader oder -Writer verwendet werden, sofern der XML-Inhalt der folgenden Zuordnung entspricht.)  
  
 In fortgeschrittenen Szenarios wird es möglicherweise notwendig, direkt auf die folgende Zuordnung zuzugreifen. Diese Szenarios sind gegeben, wenn Sie JSON mit einem benutzerdefinierten Verfahren serialisieren und deserialisieren möchten, ohne auf den <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> zurückzugreifen, oder wenn der <xref:System.ServiceModel.Channels.Message>-Typ bei Nachrichten, die JSON enthalten, direkt verarbeitet wird. Die JSON-XML-Zuordnung wird auch zur Nachrichtenprotokollierung verwendet. Bei Verwendung der Nachrichtenprotokollierungsfunktion von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] werden JSON-Nachrichten entsprechend der im nächsten Abschnitt beschriebenen Zuordnung als XML protokolliert.  
  
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
  
 Wenn die JSON-Nachricht aus dem Beispiel von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] empfangen und protokolliert wird, würde das vorstehende Protokoll folgendes XML-Fragment enthalten.  
  
## <a name="mapping-between-json-and-the-xml-infoset"></a>Zuordnung zwischen JSON und dem XML-Infoset  
 Formal, die Zuordnung zwischen JSON wie im ist [RFC 4627](http://go.microsoft.com/fwlink/?LinkId=98808) (außer mit bestimmten Einschränkungen gelockerte und bestimmte andere Einschränkungen hinzugefügt) und die XML-Infoset (und nicht Text-XML) als in der beschriebenen [XML-Informationen Legen Sie](http://go.microsoft.com/fwlink/?LinkId=98809) . Finden Sie in diesem Thema für die Definitionen der *Informationselementen* und Feldern in [eckigen Klammern].  
  
 Ein leeres JSON-Dokument wird einem leeren XML-Dokument zugeordnet, und ein leeres XML-Dokument wird einem leeren JSON-Dokument zugeordnet. In der Zuordnung von XML zu JSON sind weder Leerräume vor noch Leerräume nach dem Dokument zulässig.  
  
 Die Zuordnung wird zwischen einem Dokumentinformationselement (Document Information Item, DII) oder einem Elementinformationselement (Element Information Item, EII) und JSON definiert. Das EII bzw. die [document element]-Eigenschaft des DII wird als JSON-Stammelement bezeichnet. Beachten Sie das, dass Dokumentfragmente (XML mit mehreren Stammelementen) nicht von dieser Zuordnung unterstützt werden.  
  
 Beispiel: Sowohl für das folgende Dokument:  
  
 `<?xml version="1.0"?>`  
  
 `<root type="number">42</root>`  
  
 als auch für das folgende Element:  
  
 `<root type="number">42</root>`  
  
 ist eine Zuordnung zu JSON definiert. Die <`root`>-Element ist das JSON-Stammelement in beiden Fällen.  
  
 Weiterhin ist im Fall eines DII Folgendes zu berücksichtigen:  
  
-   Einige Elemente dürfen in der [children]-Liste nicht vorhanden sein. Verlassen Sie sich beim Lesen von XML, das aus einer Zuordnung von JSON stammt, nicht auf diese Tatsache.  
  
-   Die [children]-Liste enthält keine Kommentarinformationselemente.  
  
-   Die [children]-Liste enthält keine DTD-Informationselemente.  
  
-   Die [Children]-Liste enthält keine persönlichen Informationen (PI)-Informationselemente (die \<? XML… > Deklaration wird nicht als ein PI-Informationselement betrachtet)  
  
-   Der [notations]-Satz ist leer.  
  
-   Der [unparsed entities]-Satz ist leer.  
  
 Beispiel: Das folgende Dokument kann JSON nicht zugeordnet werden, weil die [children]-Liste ein PI und einen Kommentar enthält.  
  
 `<?xml version="1.0"?>`  
  
 `<!--comment--><?pi?>`  
  
 `<root type="number">42</root>`  
  
 Das EII für das JSON-Stammelement verfügt über folgende Eigenschaften:  
  
-   [local name] hat den Wert "root".  
  
-   [namespace name] hat keinen Wert.  
  
-   [prefix] hat keinen Wert.  
  
-   [children] kann entweder EIIs (die innere Elemente darstellen, die an späterer Stelle näher beschrieben werden) oder CIIs (Character Information Items (Zeicheninformationselemente, die an späterer Stelle näher beschrieben werden) oder keines dieser Elemente enthalten, jedoch nicht beide Elementtypen.  
  
-   [Attribute] kann die folgenden optionalen Attributinformationselemente (AIIs) enthalten.  
  
-   Das JSON-Typattribut ("type"), das an späterer Stelle näher beschrieben wird. Dieses Attribut wird verwendet, um den JSON-Typ (String, Zahl, Boolean, Objekt, Array oder NULL) im zugeordneten XML beizubehalten.  
  
-   Das Datenvertrags-Namensattribut ("__type"), das an späterer Stelle näher beschrieben wird. Dieses Attribut kann nur angegeben werden, wenn auch das JSON-Typattribut angegeben wurde und dessen [normalized value] gleich "object" ist. Dieses Attribut wird vom `DataContractJsonSerializer` verwendet, um die Typinformationen des Datenvertrags beizubehalten, beispielsweise in polymorphen Fällen, in denen ein abgeleiteter Typ serialisiert und ein Basistyp erwartet wird. Wenn Sie nicht mit dem `DataContractJsonSerializer` arbeiten, wird dieses Attribut wird meist ignoriert.  
  
-   [in-scope namespaces] enthält die Bindung zwischen "XML" und "http://www.w3.org/XML/1998/namespace" entsprechend der Infosetspezifikation.  
  
-   [children], [attributes] und [in-scope namespaces] dürfen keine anderen Elemente als die oben genannten enthalten, und [namespace attributes] darf keine Member enthalten. Sie dürfen sich beim Lesen von XML, das aus einer Zuordnung von JSON erzeugt wurde, aber nicht darauf verlassen, dass dies zutrifft.  
  
 Beispiel: Das folgende Dokument lässt sich JSON nicht zuordnen, weil [namespace attributes] nicht leer ist.  
  
 `<?xml version="1.0"?>`  
  
 `<root  xmlns:a="myattributevalue">42</root>`  
  
 Das AII für das JSON-Typattribut verfügt über folgende Eigenschaften:  
  
-   [namespace name] hat keinen Wert.  
  
-   [prefix] hat keinen Wert.  
  
-   [local name] lautet "type".  
  
-   [normalized value] enthält einen der möglichen Typwerte, die im folgenden Abschnitt beschrieben werden.  
  
-   [specified] hat den Wert `true`.  
  
-   [attribute type] hat keinen Wert.  
  
-   [references] hat keinen Wert.  
  
 Das AII für das Datenvertragsnamensattribut verfügt über folgende Eigenschaften:  
  
-   [namespace name] hat keinen Wert.  
  
-   [prefix] hat keinen Wert.  
  
-   [local name] lautet "__type" (zwei Unterstriche und dann "type").  
  
-   [normalized value] kann jede gültige Unicode-Zeichenfolge enthalten. Die Zuordnung dieser Zeichenfolge zu JSON wird im folgenden Abschnitt beschrieben.  
  
-   [specified] hat den Wert `true`.  
  
-   [attribute type] hat keinen Wert.  
  
-   [references] hat keinen Wert.  
  
 Innere Elemente innerhalb des JSON-Stammelements oder andere innere Elemente verfügen über die folgenden Eigenschaften:  
  
-   [local name] kann jeden beliebigen Wert enthalten, wie an späterer Stelle näher beschrieben wird.  
  
-   Für [namespace name], [prefix], [children], [attributes], [namespace attributes] und [in-scope namespaces] gelten die gleichen Regeln wie für das JSON-Stammelement.  
  
 Sowohl im JSON-Stammelement als auch in den inneren Elementen definiert das JSON-Typattribut die Zuordnung zu JSON und den möglichen [children]-Elementen und deren Interpretation. Im Element [normalized value] des Elements wird zwischen Groß- und Kleinschreibung unterschieden. Es darf nur Kleinbuchstaben und keinen Leerraum enthalten.  
  
|[normalized value] des AII von `JSON Type Attribute`|Zulässige [children]-Elemente des entsprechenden EII|Zuordnung zu JSON|  
|---------------------------------------------------------|---------------------------------------------------|---------------------|  
|`string` (oder Fehlen des JSON-Typs AII)<br /><br /> Ein `string` und das Fehlen des JSON- TypsAII sind gleichbedeutend, und somit ist `string` der Standard.<br /><br /> Deshalb wird `<root> string1</root>``string` in JSON dem  "string1" zugeordnet.|0 oder mehr CIIs|Eine `string` in JSON (JSON RFC, Abschnitt 2.5). Jedes `char` ist ein Zeichen, das dem im CII angegebenen [character code] entspricht. Wenn keine CIIs vorhanden sind, wird eine leere JSON-`string` zugeordnet.<br /><br /> Beispiel: Das folgende Element wird einem JSON-Fragment zugeordnet.<br /><br /> `<root type="string">42</root>`<br /><br /> Das JSON-Fragment lautet "42".<br /><br /> Bei der Zuordnung von XML zu JSON müssen Zeichen, denen ein Escapezeichen vorangestellt werden muss, Escapezeichen zugeordnet werden. Alle anderen Zeichen werden Zeichen zugeordnet, denen keine Escapezeichen voransteht. Das Zeichen "/" Sonderregeln – es wird eine Escapezeichenfolge umgewandelt, auch wenn sie keinen werden (ausgeschrieben "\\/").<br /><br /> Beispiel: Das folgende Element wird einem JSON-Fragment zugeordnet.<br /><br /> `<root type="string">the "da/ta"</root>`<br /><br /> Die JSON-Fragment lautet "die \\" da\\/TA\\"".<br /><br /> Bei der Zuordnung von JSON zu XML werden Zeichen, denen ein Escapezeichen vorangestellt ist, und andere Zeichen ohne Escapezeichen dem entsprechenden [character code] richtig zugeordnet.<br /><br /> Beispiel: Das JSON-Fragment "\u0041BC" entspricht dem folgenden XML-Element.<br /><br /> `<root type="string">ABC</root>`<br /><br /> Die Zeichenfolge kann in Leerräume ('ws' im Abschnitt&#160;2 des JSON RFC) eingeschlossen werden, die nicht in XML dargestellt werden.<br /><br /> Beispiel: Das JSON-Fragment           "ABC", (es enthält Leerräume vor dem ersten Anführungszeichen), entspricht dem folgenden XML-Element.<br /><br /> `<root type="string">ABC</root>`<br /><br /> Alle im XML vorhandenen Leerräume werden Leerräumen in JSON zugeordnet.<br /><br /> Beispiel: Das folgende XML-Element wird einem JSON-Fragment zugeordnet.<br /><br /> `<root type="string">  A BC      </root>`<br /><br /> Das JSON-Fragment lautet " A BC ".|  
|`number`|1 oder mehr CIIs|Eine JSON-`number` (JSON-RFC, Abschnitt 2.4), die von Leerraum umgeben sein kann. Jedes Zeichen in der Zahl-/Leerraum-Kombination ist ein Zeichen, das dem [character code] vom CII entspricht.<br /><br /> Beispiel: Das folgende Element wird einem JSON-Fragment zugeordnet.<br /><br /> `<root type="number">    42</root>`<br /><br /> Das JSON-Fragment lautet    42.<br /><br /> (Leerräume werden beibehalten.)|  
|`boolean`|4 oder 5 CIIs (die `true` bzw. `false` entsprechen) und möglicherweise von weiteren Leerraum-CIIs umgeben sein können.|Eine CII-Folge, die der Zeichenfolge "true" entspricht, wird dem Literal `true` zugeordnet, und eine CII-Folge, die der Zeichenfolge "false" entspricht, wird dem Literal `false` zugeordnet. Die Zeichenfolge umgebende Leerräume werden beibehalten.<br /><br /> Beispiel: Das folgende Element wird einem JSON-Fragment zugeordnet.<br /><br /> `<root type="boolean"> false</root>`<br /><br /> Der JSON-Fragement lautet `false`.|  
|`null`|Keine Elemente zulässig.|Das Literal `null`. Bei der Zuordnung von JSON zu XML kann `null` in Leerräume ('ws' im Abschnitt 2) eingeschlossen werden, die nicht in XML dargestellt werden.<br /><br /> Beispiel: Das folgende Element wird einem JSON-Fragment zugeordnet.<br /><br /> `<root type="null"/>`<br /><br /> oder<br /><br /> `<root type="null"></root>`<br /><br /> :<br /><br /> In beiden Fällen lautet das JSON-Fragement `Null`.|  
|`object`|0 oder mehr EIIs.|Eine `begin-object` (linke geschweifte Klammer) wie in Abschnitt&#160;2.2 des JSON RFC definiert, gefolgt von einem Memberdatensatz für jedes EII, wie an späterer Stelle näher beschrieben wird. Wenn mehr als ein EII vorhanden ist, werden die Memberdatensätze durch Trennzeichen (Kommas) voneinander getrennt. Abgeschlossen wird die Angabe durch ein end-object (rechte geschweifte Klammer).<br /><br /> Beispiel: Das folgende Element wird dem JSON-Fragment zugeordnet.<br /><br /> \<Stammtyp = "object" ><br /><br /> \<Typ1 Type = "String" > aaa\</type1 ><br /><br /> \<Typ2 Type = "String" > "BBB"\</type2 ><br /><br /> \</ root ><br /><br /> Das JSON-Fragment lautet {"type1":"aaa","type2":"bbb"}.<br /><br /> Wenn das Attribut für den Datenvertragstyp in der Zuordnung von XML zu JSON angegeben wird, dann wird am Anfang ein zusätzlicher Memberdatensatz hinzugefügt. Der Datensatz erhält als Namen das [local name]-Element des Datenvertragstypattributs ("__type") und als Wert das [normalized value]-Element des Attributs. Umgekehrt gilt für JSON zu XML-Zuordnung, wenn der Name der ersten memberdatensatzes dem [local Name] Daten Vertrag ein Attribut vom Typ lautet (d. h. "\__geben"), eine entsprechende Datenvertragtypattributs im zugeordneten XML vorhanden ist, aber es ist kein zugehöriges EII vorhanden. Beachten Sie, dass dieser Memberdatensatz als erster Datensatz im JSON-Objekt enthalten sein muss, damit diese spezielle Zuordnung erfolgen kann. Dies stellt eine Abweichung von der üblichen JSON-Verarbeitung dar, in der die Reihenfolge von Memberdatensätzen nicht von Bedeutung ist.<br /><br /> Beispiel:<br /><br /> Das folgende JSON-Fragment wird XML zugeordnet.<br /><br /> `{"__type":"Person","name":"John"}`<br /><br /> Der folgende Code stellt das XML dar:<br /><br /> `<root type="object" __type="Person">   <name type="string">John</name> </root>`<br /><br /> Beachten Sie, dass die \__geben AII vorhanden ist, aber es ist keine \__geben EII.<br /><br /> Wenn die Reihenfolge in JSON umgekehrt wird, wie im folgenden Beispiel gezeigt,<br /><br /> {"Name": "John","\__geben": "Person"}<br /><br /> lautet das entsprechende XML wie folgt:<br /><br /> `<root type="object">   <name type="string">John</name>   <__type type="string">Person</__type> </root>`<br /><br /> D. h. \__geben keine besondere Bedeutung mehr und wird einem eii, wie gewohnt müssen keinem aii zugeordnet.<br /><br /> Für das [normalized value]-Element von AII gelten für die Verwendung von Escapezeichen bei der Zuordnung zu JSON-Werten die gleichen Regeln wie bei der Zuordnung zu JSON-Zeichenfolgen. Diese Regeln sind in der Zeile "string" dieser Tabelle angegeben.<br /><br /> Beispiel:<br /><br /> `<root type="object" __type="\abc" />`<br /><br /> aus dem vorigen Beispiel kann dem folgenden JSON zugeordnet werden.<br /><br /> `{"__type":"\\abc"}`<br /><br /> Das-Element eines EII [lokaler Name] muss auf eine Zuordnung von XML zu JSON nicht sein "\__geben".<br /><br /> In der Zuordnung von Objekten von XML zu JSON wird kein Leerraum (`ws`) erzeugt, und bei der Zuordnung von JSON zu XML wird Leerraum ignoriert.<br /><br /> Beispiel: Das folgende JSON-Fragment wird einem XML-Element zugeordnet.<br /><br /> {   "ccc"   :  "aaa",   "ddd"    :"bbb"}<br /><br /> Das XML-Element wird im folgenden Code dargestellt.<br /><br /> `<root type="object">    <ccc type="string">aaa</ccc>    <ddd type="string">bbb</bar> </root >`|  
Strahl "|0 oder mehr EIIs|Ein begin-Array (linke eckige Klammer) entsprechend Abschnitt&#160;2.3 des JSON&#160;RFC, gefolgt von einem Arraydatensatz für jedes EII, wie an späterer Stelle näher beschrieben wird. Wenn mehr als ein EII vorhanden ist, werden die Arraydatensätze durch Trennzeichen (Kommas) voneinander getrennt. Abgeschlossen wird dies durch ein end-Array.<br /><br /> Beispiel: Das folgende XML-Element wird einem JSON-Fragment zugeordnet.<br /><br /> `<root type="array"/>    <item type="string">aaa</item>    <item type="string">bbb</item> </root >`<br /><br /> Das JSON-Fragment lautet ["aaa","bbb"]<br /><br /> Bei der Zuordnung von Arrays von XML zu JSON werden keine Leerräume (`ws`) erzeugt, und bei der Zuordnung von JSON zu XML werden Leerräume ignoriert.<br /><br /> Beispiel: Ein JSON-Fragment.<br /><br /> [     "aaa",     "bbb"]<br /><br /> Das XML-Element, das ihm zugeordnet wird.<br /><br /> `<root type="array"/>    <item type="string">aaa</item>    <item type="string">bbb</item> </root >`|  
  
 Memberdatensätze werden wie folgt verarbeitet:  
  
-   Das [local name]-Element des inneren Elements wird entsprechend Abschnitt&#160;2.2 des JSON&#160;RFC dem `string`-Teil des `member` zugeordnet.  
  
 Beispiel: Das folgende Element wird einem JSON-Fragment zugeordnet.  
  
 `<root type="object"/>`  
  
 `<myLocalName type="string">aaa</myLocalName>`  
  
 `</root >`  
  
 Das folgende JSON-Fragment wird angezeigt:  
  
 `{"myLocalName":"aaa"}`  
  
-   Bei der Zuordnung von XML zu JSON müssen Zeichen, denen in JSON ein Escapezeichen vorangestellt werden muss, Escapezeichen zugeordnet werden. Alle anderen Zeichen werden Zeichen zugeordnet, denen kein Escapezeichen voransteht. Das Zeichen "/" ist ein Sonderfall. Ihm wird ein Escapezeichen vorangestellt, obwohl dies nicht notwendig ist. (Bei der Zuordnung von JSON zu XML muss ihm kein Escapezeichen vorangestellt werden.) Dies ist erforderlich, damit das ASP.NET&#160;AJAX-Format für `DateTime`-Daten in JSON unterstützt wird.  
  
-   Bei einer Zuordnung von JSON zu XML werden alle Zeichen (einschließlich der Zeichen ohne Escapezeichen, falls erforderlich) zur Bildung eines `string`-Werts herangezogen, der ein [local name]-Element ergibt.  
  
-   Innere Elemente [children] werden entsprechend dem `JSON Type Attribute` ebenso wie beim `Root JSON Element` dem Wert in Abschnitt&#160;2.2 zugeordnet. Es sind mehrere Schachtelungsebenen von EIIs (einschließlich der Schachtelung innerhalb von Arrays) zulässig.  
  
 Beispiel: Das folgende Element wird einem JSON-Fragment zugeordnet.  
  
 `<root type="object">`  
  
 `<myLocalName1 type="string">myValue1</myLocalName1>`  
  
 `<myLocalName2 type="number">2</myLocalName2>`  
  
 `<myLocalName3 type="object">`  
  
 `<myNestedName1 type="boolean">true</myNestedName1>`  
  
 `<myNestedName2 type="null"/>`  
  
 `</myLocalName3>`  
  
 `</root >`  
  
 Das folgende JSON-Fragment resultiert aus dieser Zuordnung:  
  
 `{"myLocalName1":"myValue1","myLocalName2":2,"myLocalName3":{"myNestedName1":true,"myNestedName2":null}}`  
  
> [!NOTE]
>  Die vorangehende Zuordnung umfasst keinen XML-Codierungsschritt. Daher unterstützt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nur JSON-Dokumente, in denen Schlüsselnamen nur Zeichen enthalten, die auch in XML-Elementnamen zulässig sind. Beispielsweise wird das JSON-Dokument {"<":"a"} nicht unterstützt, weil < kein gültiger Name für ein XML-Element ist.  
  
 Der umgekehrte Fall (Zeichen, die in XML, aber nicht in JSON zulässig sind) stellt kein Problem dar, weil die vorangehende Zuordnung Schritte für das Voranstellen bzw. Entfernen von Escapezeichen in JSON beinhaltet.  
  
 Arraydatensätze werden wie folgt verarbeitet:  
  
-   [local name] des inneren Elements lautet "item".  
  
-   Das [children]-Element des inneren Elements wird entsprechend dem JSON-Attribut ebenso wie beim JSON-Stammelement dem Wert in Abschnitt&#160;2.3 zugeordnet. Es sind mehrere Schachtelungsebenen von EIIs (einschließlich der Schachtelung innerhalb von Objekten) zulässig.  
  
 Beispiel: Das folgende Element wird einem JSON-Fragment zugeordnet.  
  
 `<root type="array"/>`  
  
 `<item type="string">myValue1</item>`  
  
 `<item type="number">2</item>`  
  
 `<item type="array">`  
  
 `<item type="boolean">true</item>`  
  
 `<item type="null"/>`  
  
 `</item>`  
  
 `</root >`  
  
 Nachfolgend wird das JSON-Fragment dargestellt.  
  
 `["myValue1",2,[true,null]]`  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.Serialization.Json.JsonReaderWriterFactory>  
 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>  
 [Eigenständige JSON-Serialisierung](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)
