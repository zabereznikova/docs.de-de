---
title: "XML IntelliSense in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic code, XML"
  - "XML IntelliSense [Visual Basic]"
  - "XML [Visual Basic], IntelliSense"
  - "IntelliSense [Visual Basic], XML"
ms.assetid: 59506ce9-d64e-417e-90fc-e9fe19f0a8fa
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# XML IntelliSense in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Der Code\-Editor von Visual Basic enthält IntelliSense\-Features für XML, die Wortvervollständigungen für in einem XML\-Schema definierte Elemente bereitstellen.  Wenn Sie einem Projekt eine XSD \(XML Schema Definition\)\-Datei hinzufügen und mit der `Imports`\-Anweisung den Zielnamespace des Schemas importieren, werden Elemente aus dem XSD\-Schema vom Code\-Editor in die IntelliSense\-Liste der gültigen Membervariablen für <xref:System.Xml.Linq.XElement>\-Objekte und <xref:System.Xml.Linq.XDocument>\-Objekte aufgenommen.  Die folgende Abbildung zeigt die IntelliSense\-Memberliste für ein <xref:System.Xml.Linq.XElement>\-Objekt.  
  
 ![XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/media/xml-intellisense.png "XML\_Intellisense")  
IntelliSense für XML  
  
## Aktivieren von IntelliSense für XML in Visual Basic  
 Um IntelliSense für XML in Visual Basic zu aktivieren, müssen Sie Ihrem Visual Basic\-Projekt eine XSD\-Schemadatei hinzufügen.  Außerdem müssen Sie den Zielnamespace für das XSD\-Schema mit der `Imports`\-Anweisung in die Codedatei importieren.  Wahlweise können Sie den Zielnamespace mithilfe der Seite **Verweise** des Projekt\-Designers von Visual Basic der projektweiten Namespaceliste hinzufügen.  Beispiele finden Sie unter [How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).  Weitere Informationen finden Sie unter [Imports Statement \(XML Namespace\)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) und unter [Seite "Verweise", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic).  
  
 Beachten Sie, dass in Visual Basic\-Projekten standardmäßig keine XSD\-Schemadateien angezeigt werden.  Möglicherweise müssen Sie zum Auswählen einer XSD\-Datei, die dem Projekt hinzugefügt werden soll, auf die Schaltfläche **Alle Dateien anzeigen** klicken.  
  
### Generieren einer Schemadatei \(Schemarückschluss\)  
 Sie können ein XSD\-Schema für eine vorhandene XML\-Datei erstellen, indem Sie das XSD\-Schema mit den XML\-Tools von Visual Studio ableiten.  
  
-   Ab SP1 können Sie mit dem XML\-zu\-Schema\-Assistenten ein XML\-Schemaset erstellen, das aus einem oder aus mehreren XML\-Dokumenten abgeleitet wird, und es in das Projekt integrieren.  Es kann eine beliebige Kombination von XML\-Dokumenten in Form von Textdateien, XML aus HTTP\-Internetadressen oder in den XML\-zu\-Schema\-Assistenten eingegebene oder eingefügte XML verwendet werden.  Klicken Sie zum Aufrufen des XML\-zu\-Schema\-Assistenten im Menü **Projekt** auf **Neues Element hinzufügen**, und fügen Sie aus der Vorlagengruppe **Daten** oder **Gemeinsame Elemente** eine Vorlage **XML zu Schema** hinzu.  Wenn Sie alle XML\-Dokumentquellen angegeben haben, aus denen Sie das XML\-Schemaset ableiten möchten, klicken Sie zum Erstellen des abgeleiteten XML\-Schemasets auf **OK**.  Weitere Informationen finden Sie unter [XML to Schema Wizard](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md).  
  
-   Sie können ein XSD\-Schemaset auch mit dem XML\-Editor von Visual Studio aus einer XML\-Datei ableiten.  Um ein XML\-Schemaset mit dem XML\-Editor zu erstellen, öffnen Sie die XML\-Datei im XML\-Designer von Visual Studio, und klicken Sie dann im Menü **XML** auf **Schema erstellen**.  Nachdem Sie das XSD\-Schemaset erstellt haben, können Sie es in einer oder in mehreren XSD\-Dateien speichern und diese Dateien dem Projekt hinzufügen.  Weitere Informationen finden Sie unter[How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).  
  
 Beachten Sie, dass verschiedene XSD\-Schemasets von mehreren XML\-Dokumenten abgeleitet sein können, die über dasselbe Schema verfügen sollen.  Dies kann beispielsweise der Fall sein, wenn bestimmte Elemente und Attribute in einer XML\-Datei zu finden sind, in einer anderen jedoch nicht, oder wenn Elemente in verschiedenen Reihenfolgen enthalten sind.  Wenn Sie den XSD\-Schemarückschluss verwenden, sollten Sie die abgeleiteten XSD\-Schemasets auf Vollständigkeit und Richtigkeit überprüfen.  
  
## Memberliste  
 Wenn Sie einen Punkt \(.\) eingeben, um eine Instanz eines <xref:System.Xml.Linq.XElement>\-Objekts oder eines <xref:System.Xml.Linq.XDocument>\-Objekts \(oder eine Instanz von `IEnumerable(Of XElement)` oder `IEnumerable(Of XDocument)`\) zu unterteilen, wird von Visual Basic IntelliSense eine Liste der möglichen Objektmember angezeigt.  Die ursprüngliche Liste enthält drei Optionen, die XML\-Achseneigenschaften darstellen, wie in der folgenden Liste beschrieben.  
  
|||  
|-|-|  
|Option|Beschreibung|  
|**\< \>**|Wählen Sie diese Option aus, um eine Liste der möglichen untergeordneten Elemente anzuzeigen.  Weitere Informationen finden Sie unter [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) und der <xref:System.Xml.Linq.XContainer.Elements%2A>\-Methode.|  
|**@**|Wählen Sie diese Option aus, um eine Liste der möglichen Attribute anzuzeigen.  Weitere Informationen finden Sie unter [XML Axis Properties](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md). Diese Option ist nur für Objekte des Typs <xref:System.Xml.Linq.XElement> verfügbar.|  
|**…\< \>**|Wählen Sie diese Option aus, um eine Liste der möglichen Nachfolgerelemente anzuzeigen.  Weitere Informationen finden Sie unter [How to: Access XML Descendant Elements](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md) und der <xref:System.Xml.Linq.XContainer.Elements%2A>\-Methode.|  
  
 Wählen Sie eine der XML\-Optionen aus der Liste aus, oder beginnen Sie mit der Eingabe.  In der Memberliste werden anschließend potenzielle Member aus dem XML\-Schema angezeigt, die nur für die ausgewählte Option gelten.  Wenn Sie XML\-Namespaces importiert haben, denen bestimmte XML\-Namespacepräfixe zugeordnet sind, enthält die Memberliste eine Liste der potenziellen XML\-Namespacepräfixe.  
  
 Beachten Sie beispielsweise das folgende XSD\-Schema.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema attributeFormDefault="unqualified"   
           elementFormDefault="qualified"   
           targetNamespace="http://SamplePurchaseOrder"   
           xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="PurchaseOrders">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="PurchaseOrder">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="Address" />  
              <xs:element name="Items" />  
              <xs:element name="Comment" />  
            </xs:sequence>  
            <xs:attribute name="PurchaseOrderNumber" type="xs:unsignedShort" use="required" />  
            <xs:attribute name="OrderDate" type="xs:string" use="required" />  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 Gültiges XML für das XSD\-Schema würde ungefähr wie folgt aussehen.  
  
```  
<?xml version="1.0"?>  
<PurchaseOrders xmlns="http://SamplePurchaseOrder">  
  <PurchaseOrder PurchaseOrderNumber="12345" OrderDate="2000-1-1">  
    <Address />  
    <Items />  
    <Comment />  
  </PurchaseOrder>  
</PurchaseOrders>  
```  
  
 Wenn Sie diese XSD\-Schemadatei einem Projekt hinzufügen und den Zielnamespace aus dem XSD\-Schema in die Codedatei oder das Projekt importieren, werden von Visual Basic IntelliSense während der Eingabe von Visual Basic\-Code Member aus dem Schema angezeigt.  Wenn der Zielnamespace für das XSD\-Schema als Standardnamespace importiert wird und Sie den folgenden Text eingeben, wird von IntelliSense für das XML\-Element `PurchaseOrder` eine Liste der möglichen untergeordneten Elemente angezeigt.  
  
```  
Dim po = <PurchaseOrder />  
po.<  
```  
  
 Die Liste besteht aus den Elementen Address, Comment und Items.  
  
### Wahrscheinlichkeitsstufen für IntelliSense\-Listenelemente  
 Die Ermittlung des für IntelliSense zu verwendenden XSD\-Typs ist nicht hundertprozentig genau.  Deshalb wird von IntelliSense für XML häufig eine umfangreichere Liste der möglichen Member angezeigt.  Um Sie beim Auswählen eines Elements in der IntelliSense\-Memberliste zu unterstützen, werden Elemente mit einem Indikator für die Wahrscheinlichkeit angezeigt, mit der IntelliSense für XML einen bestimmten Member ermittelt hat.  
  
 Manchmal kann IntelliSense für XML einen bestimmten Typ aus dem XSD\-Schema identifizieren.  In diesen Fällen werden mögliche untergeordnete Elemente, Attribute oder Nachfolgerelemente für diesen XSD\-Typ mit hoher Wahrscheinlichkeit angezeigt.  Diese Elemente werden mit einem Häkchen gekennzeichnet.  
  
 Manchmal ist IntelliSense für XML jedoch nicht in der Lage, einen bestimmten Typ aus dem XSD\-Schema zu ermitteln.  In diesen Fällen wird eine umfangreichere Liste der möglichen untergeordneten Elemente, Attribute oder Nachfolgerelemente aus dem XSD\-Schema für das Projekt mit einer geringeren Wahrscheinlichkeit angezeigt.  Diese Elemente werden mit einem Fragezeichen gekennzeichnet.  
  
## Siehe auch  
 [How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md)   
 [XML to Schema Wizard](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md)   
 [Imports Statement \(XML Namespace\)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)   
 [XML Descendant Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)   
 [Seite "Verweise", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic)