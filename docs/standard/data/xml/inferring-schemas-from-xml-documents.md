---
title: Herleiten von Schemata aus XML-Dokumenten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
ms.assetid: f3d97d53-614d-4a04-a174-87965b7405f6
ms.openlocfilehash: 4540e1706cbd3dad9490f100d7e8fa58e80a9206
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733437"
---
# <a name="inferring-schemas-from-xml-documents"></a>Herleiten von Schemata aus XML-Dokumenten

In diesem Thema wird beschrieben, wie die <xref:System.Xml.Schema.XmlSchemaInference>-Klasse zum Herleiten eines XSD-Schemas (XML Schema Definition Language) aus der Struktur eines XML-Dokuments verwendet wird.  
  
## <a name="the-schema-inference-process"></a>Der Schemarückschlussprozess  

 Die <xref:System.Xml.Schema.XmlSchemaInference>-Klasse des <xref:System.Xml.Schema?displayProperty=nameWithType>-Namespaces wird verwendet, um mindestens ein XSD-Schema (XML Schema Definition Language) aus der Struktur eines XML-Dokuments herzuleiten. Die generierten Schemata können zum Validieren des ursprünglichen XML-Dokuments verwendet werden.  
  
 Da ein XML-Dokument von der <xref:System.Xml.Schema.XmlSchemaInference>-Klasse verarbeitet wird, bestehen seitens der <xref:System.Xml.Schema.XmlSchemaInference>-Klasse Einschränkungen hinsichtlich der Schemakomponenten, die die Elemente und Attribute im XML-Dokument beschreiben. Die <xref:System.Xml.Schema.XmlSchemaInference>-Klasse leitet Schemakomponenten auch nur eingeschränkt her, indem sie für ein bestimmtes Element oder Attribut den eingeschränktesten Typ herleitet. Da weitere Informationen zum XML-Dokument erfasst werden, werden die Einschränkungen zunehmend aufgehoben, indem weniger eingeschränkte Typen hergeleitet werden. Der Typ mit der geringsten Einschränkung, der hergeleitet wird, ist `xs:string`.  
  
 Betrachten Sie beispielsweise den folgenden Teil eines XML-Dokuments.  
  
```xml  
<parent attribute1="6">  
    <child>One</child>  
    <child>Two</child>  
</parent>  
<parent attribute1="A" />
```  
  
 Im obigen Beispiel wird angenommen, dass das Attribut dem Typ `attribute1` angehört, wenn der `6`-Prozess das <xref:System.Xml.Schema.XmlSchemaInference>-Attribut mit dem Wert `xs:unsignedByte` ermittelt. Wenn das zweite `parent`-Element vom <xref:System.Xml.Schema.XmlSchemaInference>-Prozess ermittelt wird, wird die Einschränkung zunehmend aufgehoben, indem der Typ `xs:string` geändert wird, da der Wert des `attribute1`-Attributs jetzt `A` ist. Das `minOccurs`-Attribut für alle im Schema hergeleiteten `child`-Elemente wird in ähnlicher Weise bis zu `minOccurs="0"` gelockert, da das zweite direkt übergeordnete Element nicht über direkt untergeordnete Elemente verfügt.  
  
## <a name="inferring-schemas-from-xml-documents"></a>Herleiten von Schemata aus XML-Dokumenten  

 Die <xref:System.Xml.Schema.XmlSchemaInference>-Klasse verwendet zwei überladene <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>-Methoden, um ein Schema aus einem XML-Dokument herzuleiten.  
  
 Die erste <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType>-Methode wird verwendet, um ein auf ein XML-Dokument beruhendes Schema zu erstellen. Die zweite <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType>-Methode wird verwendet, um ein Schema herzuleiten, das mehrere XML-Dokumente beschreibt. Sie können beispielsweise mehrere XML-Dokumente nacheinander an die <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType>-Methode übertragen, um ein Schema zu erstellen, dass die gesamte Gruppe von XML-Dokumenten beschreibt.  
  
 Die erste <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType>-Methode leitet ein Schema aus einem XML-Dokument her, das in einem <xref:System.Xml.XmlReader>-Objekt enthalten ist, und gibt ein <xref:System.Xml.Schema.XmlSchemaSet>-Objekt zurück, das das hergeleitete Schema enthält. Die zweite <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType>-Methode sucht ein <xref:System.Xml.Schema.XmlSchemaSet>-Objekt für ein Schema mit demselben Zielnamespace wie das XML-Dokument, das im <xref:System.Xml.XmlReader>-Objekt enthalten ist. Sie präzisiert das vorhandene Schema und gibt ein <xref:System.Xml.Schema.XmlSchemaSet>-Objekt zurück, das das hergeleitete Schema enthält.  
  
 Die Änderungen am präzisierten Schema beruhen auf der neuen im XML-Dokument gefundenen Struktur. Wenn beispielsweise ein XML-Dokument durchlaufen wird, werden Vermutungen über die gefundenen Datentypen angestellt, und das Schema wird auf der Grundlage dieser Vermutungen erstellt. Wenn jedoch bei einer zweiten Herleitungsübergabe Daten ermittelt werden, die nicht mit der ursprünglichen Vermutung übereinstimmen, wird das Schema präzisiert. Im folgenden Beispiel wird der Präzisierungsvorgang veranschaulicht.  
  
 [!code-cpp[XmlSchemaInferenceExamples#4](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaInferenceExamples/CPP/XmlSchemaInferenceExamples.cpp#4)]
 [!code-csharp[XmlSchemaInferenceExamples#4](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaInferenceExamples/CS/XmlSchemaInferenceExamples.cs#4)]
 [!code-vb[XmlSchemaInferenceExamples#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaInferenceExamples/VB/XmlSchemaInferenceExamples.vb#4)]  
  
 In diesem Beispiel wird die folgende Datei, `item1.xml`, als erste Eingabe verwendet.  
  
 [!code-xml[XmlSchemaInferenceExamples#13](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/item1.xml#13)]  
  
 Im Beispiel wird dann die Datei `item2.xml` als zweite Eingabe verwendet:  
  
 [!code-xml[XmlSchemaInferenceExamples#14](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/item2.xml#14)]  
  
 Wenn das `productID`-Attribut im ersten XML-Dokument ermittelt wird, wird angenommen, dass der Wert `123456789` dem Typ `xs:unsignedInt` angehört. Wenn jedoch das zweite XML-Dokument gelesen und der Wert `A53-246` gefunden wird, kann nicht mehr davon ausgegangen werden, dass es sich um den `xs:unsignedInt`-Typ handelt. Das Schema wird präzisiert, und der Typ `productID` wird in `xs:string` geändert. Außerdem wird das `minOccurs`-Attribut für das `supplierID`-Element auf `0` festgelegt, da das zweite XML-Dokument kein `supplierID`-Element enthält.  
  
 Im Folgenden wird das aus dem ersten XML-Dokument hergeleitete Schema dargestellt.  
  
 [!code-xml[XmlSchemaInferenceExamples#15](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/InferSchema1.xml#15)]  
  
 Im Folgenden wird das Schema dargestellt, das aus dem ersten XML-Dokument hergeleitet und durch das zweite XML-Dokument präzisiert wurde.  
  
 [!code-xml[XmlSchemaInferenceExamples#16](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/InferSchema2.xml#16)]  
  
## <a name="inline-schemas"></a>Inlineschemata  

 Wenn während des <xref:System.Xml.Schema.XmlSchemaInference>-Prozesses ein XSD-Schema (XML Schema Definition Language) ermittelt wurde, wird eine <xref:System.Xml.Schema.XmlSchemaInferenceException> ausgelöst. Das folgende Inlineschema löst beispielsweise eine <xref:System.Xml.Schema.XmlSchemaInferenceException> aus.  
  
```xml  
<root xmlns:ex="http://www.contoso.com" xmlns="http://www.tempuri.org">  
    <xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" targetNamespace="http://www.contoso.com">  
        <xs:element name="Contoso" type="xs:normalizedString" />  
    </xs:schema>  
    <ex:Contoso>Test</ex:Contoso>  
</root>  
```  
  
## <a name="schemas-that-cannot-be-refined"></a>Nicht präzisierbare Schemata  

 Es existieren XML-Schemakonstrukte des W3C, die der <xref:System.Xml.Schema.XmlSchemaInference>-Prozess für das XSD-Schema (XML Schema Definition Language) nicht behandeln kann, wenn ein Typ zum Präzisieren und zum Hervorrufen einer auszulösenden Ausnahme vorhanden ist. Dabei handelt es sich um einen komplexen Typ, dessen Compositor auf der obersten Ebene keine Folge ist. In einem SOM (Schemaobjektmodell) entspricht dies einem <xref:System.Xml.Schema.XmlSchemaComplexType>, dessen <xref:System.Xml.Schema.XmlSchemaComplexType.Particle%2A>-Eigenschaft keine Instanz von <xref:System.Xml.Schema.XmlSchemaSequence> ist.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Schema.XmlSchemaInference>
- [XML Schema Object Model (SOM) (XML-Schemaobjektmodell (SOM))](xml-schema-object-model-som.md)
- [Herleiten eines XML-Schemas](inferring-an-xml-schema.md)
- [Regeln für Rückschlussschemaknotentypen und Struktur](rules-for-inferring-schema-node-types-and-structure.md)
- [Regeln zum Herleiten einfacher Typen](rules-for-inferring-simple-types.md)
