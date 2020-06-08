---
title: 'Vorgehensweise: Migrieren des XslTransform-Codes'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 910beb2f-cfb3-4e8e-9936-f7e0c5f4064a
ms.openlocfilehash: 42ca884c269611ebf7dae3b4e7aa8a39ba96b521
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287739"
---
# <a name="how-to-migrate-your-xsltransform-code"></a>Vorgehensweise: Migrieren des XslTransform-Codes
Die neuen XSLT-Klassen entsprechen weitgehend den bereits vorhandenen Klassen. Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse ersetzt die <xref:System.Xml.Xsl.XslTransform>-Klasse. Stylesheets werden mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>-Methode kompiliert. Transformationen erfolgen mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode. In den folgenden Verfahren werden allgemeine XSLT-Aufgaben veranschaulicht, und der Code wird anhand der <xref:System.Xml.Xsl.XslTransform>-Klasse und der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse verglichen.  
  
### <a name="to-transform-a-file-and-output-to-a-uri"></a>So transformieren Sie eine Datei und geben sie an einen URI aus  
  
- Code, der die Klasse <xref:System.Xml.Xsl.XslTransform> verwendet.  
  
     [!code-csharp[XML_Migration#9](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#9)]
     [!code-vb[XML_Migration#9](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#9)]  
  
- Code, der die Klasse <xref:System.Xml.Xsl.XslCompiledTransform> verwendet.  
  
     [!code-csharp[XML_Migration#10](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#10)]
     [!code-vb[XML_Migration#10](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#10)]  
  
### <a name="to-compile-a-style-sheet-and-use-a-resolver-with-default-credentials"></a>So kompilieren Sie ein Stylesheet und verwenden einen Resolver mit Standardanmeldeinformationen  
  
- Code, der die Klasse <xref:System.Xml.Xsl.XslTransform> verwendet.  
  
     [!code-csharp[XML_Migration#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#11)]
     [!code-vb[XML_Migration#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#11)]  
  
- Code, der die Klasse <xref:System.Xml.Xsl.XslCompiledTransform> verwendet.  
  
     [!code-csharp[XML_Migration#12](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#12)]
     [!code-vb[XML_Migration#12](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#12)]  
  
### <a name="to-use-an-xslt-parameter"></a>So verwenden Sie einen XSLT-Parameter  
  
- Code, der die Klasse <xref:System.Xml.Xsl.XslTransform> verwendet.  
  
     [!code-csharp[XML_Migration#13](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#13)]
     [!code-vb[XML_Migration#13](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#13)]  
  
- Code, der die Klasse <xref:System.Xml.Xsl.XslCompiledTransform> verwendet.  
  
     [!code-csharp[XML_Migration#14](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#14)]
     [!code-vb[XML_Migration#14](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#14)]  
  
### <a name="to-enable-xslt-scripting"></a>So aktivieren Sie die XSLT-Skripterstellung  
  
- Code, der die Klasse <xref:System.Xml.Xsl.XslTransform> verwendet.  
  
     [!code-csharp[XML_Migration#15](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#15)]
     [!code-vb[XML_Migration#15](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#15)]  
  
- Code, der die Klasse <xref:System.Xml.Xsl.XslCompiledTransform> verwendet.  
  
     [!code-csharp[XML_Migration#16](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#16)]
     [!code-vb[XML_Migration#16](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#16)]  
  
### <a name="to-load-the-results-into-a-dom-object"></a>So laden Sie die Ergebnisse in ein DOM-Objekt  
  
- Code, der die Klasse <xref:System.Xml.Xsl.XslTransform> verwendet.  
  
     [!code-csharp[XML_Migration#19](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#19)]
     [!code-vb[XML_Migration#19](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#19)]  
  
- Code, der die Klasse <xref:System.Xml.Xsl.XslCompiledTransform> verwendet.  
  
    > [!NOTE]
    > Die <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse weist keine Methode auf, die die Ergebnisse der XSLT-Transformationen als <xref:System.Xml.XmlReader>-Objekt zurückgibt. Sie können diese jedoch in eine XML-Datei ausgeben und diese XML-Datei in ein anderes Objekt laden.  
  
     [!code-csharp[XML_Migration#20](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#20)]
     [!code-vb[XML_Migration#20](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#20)]  
  
### <a name="to-stream-the-results-into-another-data-store"></a>So geben Sie die Ergebnisse in einem Datenstream in einen anderen Datenspeicher aus  
  
- Code, der die Klasse <xref:System.Xml.Xsl.XslTransform> verwendet.  
  
     [!code-csharp[XML_Migration#17](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#17)]
     [!code-vb[XML_Migration#17](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#17)]  
  
- Code, der die Klasse <xref:System.Xml.Xsl.XslCompiledTransform> verwendet.  
  
     [!code-csharp[XML_Migration#18](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#18)]
     [!code-vb[XML_Migration#18](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#18)]  
  
## <a name="see-also"></a>Siehe auch

- [Migrieren von der XslTransform-Klasse](migrating-from-the-xsltransform-class.md)
- [Verwenden der XslCompiledTransform-Klasse](using-the-xslcompiledtransform-class.md)
