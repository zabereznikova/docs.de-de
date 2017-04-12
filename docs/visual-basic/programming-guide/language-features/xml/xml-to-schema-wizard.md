---
title: XML zu Schema-Assistenten (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vb.XmlToSchemaWizard
dev_langs:
- VB
helpviewer_keywords:
- XML IntelliSense [Visual Basic]
- XML [Visual Basic], IntelliSense
- IntelliSense [Visual Basic], XML
- XML schemas, creating
ms.assetid: 98c495ba-8f37-4517-a0db-aa738611ab76
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: d0c9c0247f3d9934ef973c7322cb098f9b445a5a
ms.lasthandoff: 03/13/2017

---
# <a name="xml-to-schema-wizard-visual-basic"></a>Assistent "XML zu Schema" (Visual Basic)
Mit dem XML-Schema-Assistenten erstellen ein XML-Schemaset abgeleitet wird, die aus einem oder mehreren XML-Dokumenten und das Projekt einzuschließen. Sie können eine beliebige Kombination von XML-Dokumenten in Form von Textdateien, XML aus HTTP-Internetadressen oder XML, das Eingabe oder beim Einfügen in das XML-Schema-Assistenten verwenden.  
  
 XML-Schemas werden verwendet, um IntelliSense für XML-Eigenschaften in Visual Basic bereitzustellen. Weitere Informationen finden Sie unter [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) und [IntelliSense für XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md).  
  
> [!NOTE]
>  Bevor Sie das XML-Schema-Assistenten ausführen, wird empfohlen, dass Sie alle vorhandenen XSD-Dateien aus dem Projekt, die zuvor vom Assistenten generiert wurden entfernt. Ein Konflikt kann auftreten, wenn Sie ein XML-Schemaset, der mit einem vorhandenen Schemaset übereinstimmt ableiten, und [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] wird nicht in der Lage, IntelliSense für XML-Eigenschaften bereitgestellt.  
  
 Das XML to Schema-Assistent verwendet die <xref:System.Xml.Schema.XmlSchemaInference>Klasse, um das Schema für das angegebene XML zu erstellen.</xref:System.Xml.Schema.XmlSchemaInference> Daher können mehrere Schemadateien für das Schemaset erstellt werden. Für jeden XML-Namespace im angegebenen XML wird eine Datei Extensible Schema Definition (XSD) erstellt. Weitere Informationen finden Sie unter der <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>-Methode.</xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>  
  
 Um das XML to Schema-Assistenten zuzugreifen, klicken Sie auf **neues Element hinzufügen** auf der **Projekt** Menü und fügen eine **XML zu Schema** Vorlage aus der **Daten** oder **gemeinsame Elemente** Vorlagengruppe. Nachdem Sie alle der XML-Dokumentquellen aus der XML-Schemaset hinzugefügt haben, klicken Sie auf **OK** das hergeleitete Schema zu erstellen.  
  
 **Quelltyp**  
 Diese Spalte zeigt den Typ des Quell-XML-Dokument: **Datei**, **URL**, oder **XML**.  
  
 **Speicherort des XML-Dokuments**  
 Diese Spalte zeigt den Pfad des XML-Dokuments. Bei eingegebenen oder eingefügten XML-Dokumenten zeigt den Inhalt des XML-Dokuments.  
  
 **Aus Datei hinzufügen**  
 Klicken Sie auf diese Schaltfläche, um XML-Dokumentdateien mithilfe von Datei-Explorer hinzufügen.  
  
 **Hinzufügen von Web**  
 Klicken Sie auf diese Schaltfläche, um die HTTP-Adresse eines XML-Dokuments angeben.  
  
 **Geben oder fügen Sie XML**  
 Klicken Sie auf diese Schaltfläche, um geben oder fügen ein XML-Dokument in das Dialogfeld.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Schema.XmlSchemaInference></xref:System.Xml.Schema.XmlSchemaInference>   
 [IntelliSense für XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)
