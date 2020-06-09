---
title: 'Vorgehensweise: Exportieren von Metadaten aus Dienstendpunkten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b6c4dfd0-f270-43ec-961a-e16eb6af2f2c
ms.openlocfilehash: 58e86e5566775048e081bfb4ac217a7747b98a35
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579409"
---
# <a name="how-to-export-metadata-from-service-endpoints"></a>Vorgehensweise: Exportieren von Metadaten aus Dienstendpunkten
In diesem Thema wird erklärt, wie Sie Metadaten aus Dienstendpunkten exportieren.  
  
### <a name="to-export-metadata-from-service-endpoints"></a>So exportieren Sie Metadaten aus Dienstendpunkten  
  
1. Erstellen Sie ein neues Visual Studio-Konsolenanwendungsprojekt. Fügen Sie den in den folgenden Schritten gezeigten Code der erzeugten Datei "Program.cs" innerhalb der main()-Methode hinzu.  
  
2. Erstellen Sie eine <xref:System.ServiceModel.Description.WsdlExporter>.  
  
     [!code-csharp[S_UEWsdlExporter#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#1)]
     [!code-vb[S_UEWsdlExporter#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#1)]  
  
3. Legen Sie die <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>-Eigenschaft auf einen der <xref:System.ServiceModel.Description.PolicyVersion>-Enumerationswerte fest. In diesem Beispiel wird der Wert auf <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> festgelegt. Dies entspricht der WS-Richtlinie 1.5.  
  
     [!code-csharp[S_UEWsdlExporter#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#2)]
     [!code-vb[S_UEWsdlExporter#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#2)]  
  
4. Erstellen Sie ein Array mit <xref:System.ServiceModel.Description.ServiceEndpoint>-Objekten.  
  
     [!code-csharp[S_UEWsdlExporter#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#3)]
     [!code-vb[S_UEWsdlExporter#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#3)]  
  
5. Exportieren Sie Metadaten für jeden Dienstendpunkt.  
  
     [!code-csharp[S_UEWsdlExporter#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#4)]
     [!code-vb[S_UEWsdlExporter#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#4)]  
  
6. Stellen Sie sicher, dass während des Exportprozesses keine Fehler aufgetreten sind, und rufen Sie die Metadaten ab.  
  
     [!code-csharp[S_UEWsdlExporter#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#5)]
     [!code-vb[S_UEWsdlExporter#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#5)]  
  
7. Sie können die Metadaten jetzt verwenden, beispielsweise indem Sie sie mithilfe eines Aufrufs der <xref:System.ServiceModel.Description.MetadataSet.WriteTo%28System.Xml.XmlWriter%29>-Methode in eine Datei schreiben.  
  
## <a name="example"></a>Beispiel  
 Unten ist die vollständige Codeauflistung für dieses Beispiel angegeben.  
  
 [!code-csharp[S_UEWsdlExporter#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#0)]
 [!code-vb[S_UEWsdlExporter#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#0)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Verweisen Sie beim Kompilieren der Datei "Program.cs" auf "System.ServiceModel.dll".  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die Metadatenarchitektur](metadata-architecture-overview.md)
- [Verwenden von Metadaten](using-metadata.md)
- [Endpunkte: Adressen, Bindungen und Verträge](endpoints-addresses-bindings-and-contracts.md)
