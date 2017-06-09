---
title: "Schemakompilierung mit &quot;XmlSchemaCollection&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 76f28770-7126-428f-9ed5-7b5ae8bad5ee
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 4
---
# Schemakompilierung mit &quot;XmlSchemaCollection&quot;
Bei **XmlSchemaCollection** handelt es sich um einen Cache oder eine Bibliothek, worin XDR\-Schemata \(XML\-Data Reduced\) und XSD\-Schemata \(XML Schema Definition Language\) gespeichert und validiert werden können.  **XmlSchemaCollection** erhöht die Leistungsfähigkeit, indem Schemata im Arbeitsspeicher zwischengespeichert werden, anstatt über eine Datei oder eine URL auf sie zuzugreifen.  
  
> [!NOTE]
>  Obwohl in der **XmlSchemaCollection** sowohl XML\-Schemata als auch XDR\-Schemata gespeichert werden, unterstützt jede Methode oder Eigenschaft, die ein **XmlSchema**\-Objekt akzeptiert bzw. zurückgibt, nur XML\-Schemata.  
  
> [!IMPORTANT]
>  Die <xref:System.Xml.Schema.XmlSchemaCollection>\-Klasse ist veraltet und wurde durch die <xref:System.Xml.Schema.XmlSchemaSet>\-Klasse ersetzt.  Weitere Informationen zur <xref:System.Xml.Schema.XmlSchemaSet>\-Klasse finden Sie unter ["XmlSchemaSet" zur Kompilierung von Schemata](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).  
  
## Hinzufügen von Schemata zur Auflistung  
 Durch die **Add**\-Methode von **XmlSchemaCollection** werden Schemata in die Auflistung geladen, sobald das Schema einem Namespace\-URI zugeordnet wird.  Bei XML\-Schemata ist der Namespace\-URI normalerweise der Zielnamespace des Schemas.  Bei XDR\-Schemata ist der Namespace\-URI der Namespace, der angegeben wird, wenn ein Schema der Auflistung hinzugefügt wird.  
  
## Suche nach einem Schema in der Auflistung  
 Mit der **Contains**\-Methode können Sie überprüfen, ob ein Schema in der Auflistung enthalten ist.  Die **Contains**\-Methode übernimmt entweder ein **XmlSchema**\-Objekt \(nur bei XML\-Schemata\) oder eine Zeichenfolge, die den dem Schema zugeordneten Namespace\-URI repräsentiert \(bei XML\- und XDR\-Schemata\).  
  
## Abrufen eines Schemas aus der Auflistung  
 Mit der **Item**\-Eigenschaft kann ein Schema aus der Auflistung abgerufen werden.  Die **Item**\-Eigenschaft übernimmt eine Zeichenfolge, die den dem Schema zugeordneten Namespace\-URI repräsentiert \(normalerweise den Zielnamespace des Schemas\), und gibt ein **XmlSchema**\-Objekt zurück.  Die **Item**\-Eigenschaft wird nur bei XML\-Schemata angewendet.  Der Rückgabewert ist bei XDR\-Schemata immer ein NULL\-Verweis, da diese kein Objektmodell zur Verfügung haben.  
  
## Validieren von XML\-Dokumenten mit "XmlSchemaCollection"  
 Ein XML\-Instanzdokument wird mithilfe von **XmlSchemaCollection** folgendermaßen validiert: Ein **XmlSchemaCollection**\-Objekt wird erstellt, und die jeweiligen Schemata werden der Auflistung hinzugefügt. Anschließend wird die **Schemas**\-Eigenschaft von **XmlValidatingReader** festgelegt, um die erstellte **XmlSchemaCollection** dem **XmlValidatingReader** zuzuordnen.  
  
### Leistungssteigerung  
 Wird mehr als ein Dokument anhand desselben Schemas validiert, ist es ratsam, **XmlSchemaCollection** zu verwenden. Die Leistung wird durch Zwischenspeichern der Schemata im Arbeitsspeicher gesteigert.  
  
 Im folgenden Codebeispiel wird das **XmlSchemaCollection**\-Objekt erstellt, und die Schemata werden der Auflistung hinzugefügt. Anschließend wird die **Schemas**\-Eigenschaft festgelegt.  
  
```vb  
Dim tr as XmlTextReader = new XmlTextReader("Books.xml")  
Dim vr as XmlValidatingReader = new XmlValidatingReader(tr)  
Dim xsc as XmlSchemaCollection = new XmlSchemaCollection  
xsc.Add("urn:bookstore-schema", "Books.xsd")  
vr.Schemas.Add(xsc)  
```  
  
```csharp  
XmlTextReader tr = new XmlTextReader("Books.xml");  
XmlValidatingReader vr = new XmlValidatingReader(tr);  
XmlSchemaCollection xsc = new XmlSchemaCollection();  
xsc.Add("urn:bookstore-schema", "Books.xsd");    
vr.Schemas.Add(xsc);  
```  
  
## Siehe auch  
 [XDR\-Validierung mit "XmlSchemaCollection"](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)   
 [XSD\-Validierung \(XML Schema\) mit "XmlSchemaCollection"](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)