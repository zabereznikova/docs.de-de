---
title: "IntelliSense für XML in Visual Basic | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, XML
- XML IntelliSense [Visual Basic]
- XML [Visual Basic], IntelliSense
- IntelliSense [Visual Basic], XML
ms.assetid: 59506ce9-d64e-417e-90fc-e9fe19f0a8fa
caps.latest.revision: 27
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8c43db3d2010e4fa92eebeec8a973c50052b1340
ms.lasthandoff: 03/13/2017

---
# <a name="xml-intellisense-in-visual-basic"></a>XML IntelliSense in Visual Basic
Der Visual Basic-Code-Editor enthält die IntelliSense-Funktionen für XML, die Word-Abschluss in ein XML-Schema definierte Elemente bereitstellen. Wenn Sie eine XML-Schema Definition (XSD)-Datei in Ihrem Projekt hinzugefügt, und importieren den Zielnamespace des Schemas mithilfe der `Imports` -Anweisung, die Code-Editor enthält Elemente aus dem XSD-Schema in der IntelliSense-Liste der gültigen Membervariablen für <xref:System.Xml.Linq.XElement>und <xref:System.Xml.Linq.XDocument>Objekte.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> Die folgende Abbildung zeigt die IntelliSense-Memberliste für ein <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement>  
  
 ![IntelliSense für XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/media/xml_intellisense.png "XML_Intellisense")  
IntelliSense für XML  
  
## <a name="enabling-xml-intellisense-in-visual-basic"></a>Aktivieren von IntelliSense für XML in Visual Basic  
 Um IntelliSense für XML in Visual Basic zu aktivieren, müssen Sie in Visual Basic-Projekt eine XSD-Schemadatei einschließen. Sie müssen auch den Zielnamespace für das XSD-Schema in die Codedatei importieren, mit der `Imports` Anweisung. Alternativ können Sie den Zielnamespace auch die Liste der Namespaces auf Projektebene hinzufügen, mit der **Verweise** im Visual Basic-Projekt-Designer auf der Seite. Beispiele finden Sie unter [How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md). Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) und [Seite "Verweise", Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).  
  
 Beachten Sie, die standardmäßig nicht XSD-Schemadateien in Visual Basic-Projekte angezeigt. Möglicherweise müssen Sie klicken Sie auf die **alle Dateien anzeigen** klicken, um eine XSD-Datei in Ihr Projekt aufnehmen auszuwählen.  
  
### <a name="generating-a-schema-file-schema-inference"></a>Generieren einer Schemadatei (Schemarückschluss)  
 Sie können ein XSD-Schema für eine vorhandene XML-Datei anhand des XSD-Schemas mithilfe von Visual Studio-XML-Tools erstellen.  
  
-   Ab SP1 können Sie das XML to Schema-Assistenten ein XML-Schemaset abgeleitet wird von ein oder mehrere XML-Dokumente erstellen und es in das Projekt integrieren. Sie können eine beliebige Kombination von XML-Dokumenten in Form von Textdateien, XML aus HTTP-Internetadressen oder XML, das Eingabe oder beim Einfügen in das XML-Schema-Assistenten verwenden. Um das XML to Schema-Assistenten zuzugreifen, klicken Sie auf **neues Element hinzufügen** auf der **Projekt** Menü und fügen eine **XML zu Schema** Vorlage aus der **Daten** oder **gemeinsame Elemente** Vorlagengruppe. Nachdem Sie alle der XML-Dokumentquellen aus der XML-Schemaset hinzugefügt haben, klicken Sie auf **OK** das hergeleitete Schema zu erstellen. Weitere Informationen finden Sie unter [XML-Schema-Assistenten](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md).  
  
-   Sie können auch XML-Editor von Visual Studio verwenden, Herleiten ein XSD-Schemas aus einer XML-Datei festgelegt. Um ein XML-Schemaset im XML-Editor zu erstellen, öffnen Sie eine XML-Datei im XML-Designer von Visual Studio, und klicken Sie dann auf **Create Schema** auf der **XML** Menü. Nachdem Sie die XSD-Schema erstellen, können Sie erstellte Schemaset in eine oder mehrere XSD-Dateien speichern und in Ihr Projekt einbinden. Weitere Informationen finden Sie unter[How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).  
  
 Beachten Sie, dass unterschiedliche Sätze von XSD-Schemas von mehreren XML-Dokumenten abgeleitet sein können, die das gleiche Schema aufweisen sollen. Dies kann auftreten, wenn bestimmte Elemente und Attribute in einer XML-Datei und nicht in einem anderen gefunden werden, oder wenn Elemente in verschiedenen Reihenfolgen enthalten sind, z. B.. Wenn Sie XSD-Schemarückschluss verwenden, sollten Sie abgeleiteten XSD-Schemasets auf Vollständigkeit und Richtigkeit überprüfen.  
  
## <a name="member-list"></a>Mitgliederliste  
 Nach der Eingabe von eines Punkts (.) zum Trennen von einer Instanz von einer <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XDocument>Objekt (oder eine Instanz von `IEnumerable(Of XElement)` oder `IEnumerable(Of XDocument)`), Visual Basic IntelliSense zeigt eine Liste der möglichen Objektmember.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> Die anfängliche Liste enthält drei Optionen, die XML-Achseneigenschaften darstellen, wie in der folgenden Liste beschrieben.  
  
|Option|Beschreibung|  
|---|---|  
|**\< >**|Wählen Sie diese Option, um eine Liste der möglichen untergeordneten Elemente anzuzeigen. Weitere Informationen finden Sie unter [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) und der <xref:System.Xml.Linq.XContainer.Elements%2A>-Methode.</xref:System.Xml.Linq.XContainer.Elements%2A>|  
|**@**|Wählen Sie diese Option, um eine Liste der möglichen Attribute anzuzeigen. Weitere Informationen finden Sie unter [XML-Achseneigenschaften](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md). Diese Option steht nur für Objekte vom Typ <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement>|  
|**…\< >**|Wählen Sie diese Option, um eine Liste der möglichen untergeordneten Elemente anzuzeigen. Weitere Informationen finden Sie unter [Gewusst wie: Zugriff auf XML-Nachfolger Elemente](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md) und die <xref:System.Xml.Linq.XContainer.Elements%2A>-Methode.</xref:System.Xml.Linq.XContainer.Elements%2A>|  
  
 Wählen Sie aus, oder beginnen Sie, geben Sie die XML-Optionen aus der Liste. Die Memberliste wird potenzielle Member aus dem XML-Schema angezeigt, die für die ausgewählte Option spezifisch sind. Wenn Sie XML-Namespaces importiert, die einem bestimmten XML-Namespace-Präfix zugeordnet sind haben, ist eine Liste der potenziellen XML-Namespacepräfixe in der Memberliste enthalten.  
  
 Betrachten Sie beispielsweise das folgende XSD-Schema.  
  
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
  
 Gültiges XML für das XSD-Schema würde wie folgt aussehen.  
  
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
  
 Wenn Sie diese XSD-Schema-Datei in einem Projekt einschließen und den Zielnamespace aus dem XSD-Schema in die Codedatei oder das Projekt importieren, werden Visual Basic IntelliSense während der Eingabe von Visual Basic-Code Member aus dem Schema angezeigt. Wenn der Zielnamespace für das XSD-Schema als Standardnamespace importiert wird, und geben Sie Folgendes ein, zeigt IntelliSense eine Liste der möglichen untergeordneten Elemente für die `PurchaseOrder` -XML-Element.  
  
```  
Dim po = <PurchaseOrder />  
po.<  
```  
  
 Die Liste besteht aus den Elementen Adresse, Kommentieren und Elemente.  
  
### <a name="certainty-levels-for-intellisense-list-items"></a>Wahrscheinlichkeitsstufen für IntelliSense-Listenelemente  
 Bestimmen die XSD-Typ für IntelliSense ist nicht exakt. Daher wird IntelliSense für XML häufig eine umfangreichere Liste der möglichen Elemente angezeigt. Als Hilfe für das Auswählen eines Elements aus der IntelliSense-Memberliste werden Elemente mit einem Indikator für die Wahrscheinlichkeit angezeigt, die XML IntelliSense für einen bestimmten Member verfügt.  
  
 Manchmal kann IntelliSense für XML einen bestimmten Typ aus dem XSD-Schema identifizieren. In diesen Fällen wird mögliche untergeordnete Elemente, Attribute oder Nachfolgerelemente für diesen XSD-Typ mit hoher Wahrscheinlichkeit angezeigt. Diese Elemente werden mit einem Häkchen gekennzeichnet.  
  
 Allerdings kann manchmal XML IntelliSense nicht zur Identifizierung eines bestimmten Typs aus dem XSD-Schema. In diesen Fällen wird eine umfangreichere Liste der möglichen untergeordneten Elemente, Attribute oder untergeordneten Elemente aus dem XSD-Schema für das Projekt mit einer geringeren Wahrscheinlichkeit angezeigt. Diese Elemente werden mit einem Fragezeichen gekennzeichnet.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Aktivieren von XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md)   
 [XML-Schema-Assistenten](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md)   
 [Imports-Anweisung (XML-Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [XML-Elementliteral](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML-Attributachseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)   
 [XML-Achseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)   
 [Seite „Verweise“, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)
