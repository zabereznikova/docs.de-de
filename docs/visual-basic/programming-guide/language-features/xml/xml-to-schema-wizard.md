---
title: "XML to Schema Wizard (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.XmlToSchemaWizard"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML IntelliSense [Visual Basic]"
  - "XML [Visual Basic], IntelliSense"
  - "IntelliSense [Visual Basic], XML"
  - "XML schemas, creating"
ms.assetid: 98c495ba-8f37-4517-a0db-aa738611ab76
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML to Schema Wizard (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Mit dem XML\-zu\-Schema\-Assistenten können Sie ein XML\-Schemaset erstellen, das aus einem oder aus mehreren XML\-Dokumenten abgeleitet wird, und es in das Projekt integrieren.  Es kann eine beliebige Kombination von XML\-Dokumenten in Form von Textdateien, XML aus HTTP\-Internetadressen oder in den XML\-zu\-Schema\-Assistenten eingegebene oder eingefügte XML verwendet werden.  
  
 Durch XML\-Schemas wird IntelliSense für XML\-Eigenschaften in Visual Basic bereitgestellt.  Weitere Informationen finden Sie unter [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) und [XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md).  
  
> [!NOTE]
>  Bevor Sie den XML\-zu\-Schema\-Assistenten ausführen, sollten Sie alle vorhandenen XSD\-Dateien, die bereits von dem Assistenten erstellt wurden, aus dem Projekt entfernen.  Wenn Sie ein XML\-Schemaset ableiten, das mit einem vorhandenen Schemaset übereinstimmt, verursacht dies einen Konflikt. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] ist in diesem Fall nicht in der Lage, IntelliSense für XML\-Eigenschaften bereitzustellen.  
  
 Der XML\-zu\-Schema\-Assistent verwendet die <xref:System.Xml.Schema.XmlSchemaInference>\-Klasse, um das Schema für das angegebene XML zu erstellen.  Hierdurch werden u. U. mehrere Schemadateien für das Schemaset erstellt.  Für jeden XML\-Namespace im angegebenen XML wird eine XSD\-Datei \(Extensible Schema Definition\) erstellt.  Weitere Informationen finden Sie unter der <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>\-Methode.  
  
 Klicken Sie zum Aufrufen des XML\-zu\-Schema\-Assistenten im Menü **Projekt** auf **Neues Element hinzufügen**, und fügen Sie aus der Vorlagengruppe **Daten** oder **Gemeinsame Elemente** eine Vorlage **XML zu Schema** hinzu.  Wenn Sie alle XML\-Dokumentquellen angegeben haben, aus denen Sie das XML\-Schemaset ableiten möchten, klicken Sie zum Erstellen des abgeleiteten XML\-Schemasets auf **OK**.  
  
 **Quelltyp**  
 Diese Spalte zeigt den Typ der XML\-Dokumentquelle an: **Datei**, **URL** oder **XML**.  
  
 **Speicherort des XML\-Dokuments**  
 Diese Spalte zeigt den Pfad des XML\-Dokuments an.  Bei eingegebenen oder eingefügten XML\-Dokumenten wird der Inhalt des XML\-Dokuments angezeigt.  
  
 **Aus Datei hinzufügen**  
 Klicken Sie auf diese Schaltfläche, um XML\-Dokumenten\-Dateien hinzuzufügen, indem Sie Datei\-Explorer verwenden.  
  
 **Aus Web hinzufügen**  
 Klicken Sie auf diese Schaltfläche, um die HTTP\-Adresse eines XML\-Dokuments anzugeben.  
  
 **XML eingeben oder einfügen**  
 Klicken Sie auf diese Schaltfläche, um ein XML\-Dokument in das Dialogfeld einzugeben oder einzufügen.  
  
## Siehe auch  
 <xref:System.Xml.Schema.XmlSchemaInference>   
 [XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)