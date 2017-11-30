---
title: Schemakompilierung mit "XmlSchemaCollection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 76f28770-7126-428f-9ed5-7b5ae8bad5ee
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 901c3fdc8fdc80cc7c3bf13170646de857a5e009
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xmlschemacollection-schema-compilation"></a>Schemakompilierung mit "XmlSchemaCollection"
Die **"XmlSchemaCollection"** ist ein Cache oder die Bibliothek, wo Schemas für XML-Data Reduced (XDR) und XML Schema Definition Language (XSD) gespeichert und validiert werden können. **Das XmlSchemaCollection-Objekt** verbessert die Leistung durch Zwischenspeichern der Schemata im Arbeitsspeicher anstatt aus einer Datei oder eine URL auf Sie zuzugreifen.  
  
> [!NOTE]
>  Obwohl die **"XmlSchemaCollection"** Klasse speichert XDR-Schemas und XML-Schemas, jede Methode oder Eigenschaft, die akzeptiert bzw. zurückgibt ein **XmlSchema** Objekt unterstützt nur die XML-Schemas.  
  
> [!IMPORTANT]
>  Die <xref:System.Xml.Schema.XmlSchemaCollection>-Klasse ist veraltet und wurde durch die <xref:System.Xml.Schema.XmlSchemaSet>-Klasse ersetzt. Weitere Informationen zu den <xref:System.Xml.Schema.XmlSchemaSet> Klasse finden Sie unter ["XmlSchemaSet" zur Kompilierung von Schemata](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).  
  
## <a name="add-schemas-to-the-collection"></a>Hinzufügen von Schemata zur Auflistung  
 Schemas werden geladen, um die Auflistung mit den **hinzufügen** Methode **"XmlSchemaCollection"**, zu diesem Zeitpunkt das Schema einem Namespace-URI zugeordnet ist. Bei XML-Schemata ist der Namespace-URI normalerweise der Zielnamespace des Schemas. Bei XDR-Schemata ist der Namespace-URI der Namespace, der angegeben wird, wenn ein Schema der Auflistung hinzugefügt wird.  
  
## <a name="check-for-a-schema-in-the-collection"></a>Suche nach einem Schema in der Auflistung  
 Sie können überprüfen, um festzustellen, ob ein Schema in der Auflistung, mithilfe befindet der **Contains** Methode. Die **Contains** -Methode übernimmt entweder ein **XmlSchema** Objekts (nur XML-Schemas) oder eine Zeichenfolge, die den Namespace-URI repräsentiert (bei XML- und XDR-Schemas) Schema zugeordnet.  
  
## <a name="retrieve-a-schema-from-the-collection"></a>Abrufen eines Schemas aus der Auflistung  
 Sie können ein Schema aus der Auflistung abrufen, indem Sie mit der **Element** Eigenschaft. Die **Element** Eigenschaft nimmt eine Zeichenfolge, die den Namespace-URI-Schema, normalerweise den Zielnamespace zugeordnet darstellt, und gibt eine **XmlSchema** Objekt. Die **Element** Eigenschaft gilt nur für XML-Schemas. Der Rückgabewert ist bei XDR-Schemata immer ein NULL-Verweis, da diese kein Objektmodell zur Verfügung haben.  
  
## <a name="validate-xml-documents-using-xmlschemacollection"></a>Validieren von XML-Dokumenten mit "XmlSchemaCollection"  
 Können Sie überprüfen, ein XML-Instanzdokument wird mithilfe einer **"XmlSchemaCollection"** durch das Erstellen der **"XmlSchemaCollection"** Objekt, Ihre Schemas zur Auflistung hinzufügen und Festlegen der **Schemas**  Eigenschaft auf die **XmlValidatingReader** um die erstellte **"XmlSchemaCollection"** auf die **XmlValidatingReader**.  
  
### <a name="improved-performance"></a>Leistungssteigerung  
 Es wird empfohlen, wenn Sie mehr als ein Dokument anhand desselben Schemas überprüfen, verwenden Sie die **"XmlSchemaCollection"** , da es sich um eine bessere Leistung bietet, indem Schemata im Arbeitsspeicher zwischengespeichert.  
  
 Das folgende Codebeispiel erstellt die **"XmlSchemaCollection"** Objekt, fügt der Auflistung Schemas hinzu und legt sie fest der **Schemas** Eigenschaft.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [XDR-Validierung mit "XmlSchemaCollection"](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)  
 [Validierung von XML-Schemas (XSD) mit "XmlSchemaCollection"](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)
