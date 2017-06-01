---
title: "Gewusst wie: Ver&#246;ffentlichen von Metadaten f&#252;r einen Dienst &#252;ber den Code | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 51407e6d-4d87-42d5-be7c-9887b8652006
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# Gewusst wie: Ver&#246;ffentlichen von Metadaten f&#252;r einen Dienst &#252;ber den Code
Dies ist eines der beiden "Gewusst wie"\-Themen, in denen erläutert wird, wie Sie Metadaten für einen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienst veröffentlichen.Es gibt zwei Möglichkeiten für einen Dienst zum Veröffentlichen von Metadaten: mit einer Konfigurationsdatei und mit Code.In diesem Thema wird das Veröffentlichen von Metadaten für einen Dienst mithilfe von Code dargestellt.  
  
> [!CAUTION]
>  In diesem Thema wird das Veröffentlichen von Metadaten auf unsichere Weise dargestellt.Jeder Client kann Metadaten vom Dienst abrufen.Informationen zum sicheren Veröffentlichen von Metadaten.finden Sie unter [Benutzerdefinierter sicherer Metadatenendpunkt](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Veröffentlichen von Metadaten in einer Konfigurationsdatei finden Sie unter [Gewusst wie: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).Die Veröffentlichung von Metadaten ermöglicht Clients, Metadaten über eine WS\-Transfer\-GET\-Anforderung oder eine HTTP\/GET\-Anforderung mithilfe einer `?wsdl`\-Abfragezeichenfolge abzurufen.Erstellen Sie einen grundlegenden WCF\-Dienst, um sicherzustellen, dass der Code funktioniert.Im folgenden Code wird ein grundlegender, selbst gehosteter Dienst bereitgestellt:  
  
 [!code-csharp[htPublishMetadataCode#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#0)]
 [!code-vb[htPublishMetadataCode#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#0)]  
  
### So veröffentlichen Sie Metadaten im Code  
  
1.  Instanziieren Sie in der Hauptmethode einer Konsolenanwendung ein <xref:System.ServiceModel.ServiceHost>\-Objekt, indem Sie den Diensttyp und die Basisadresse übergeben.  
  
     [!code-csharp[htPublishMetadataCode#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#1)]
     [!code-vb[htPublishMetadataCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#1)]  
  
2.  Erstellen Sie unmittelbar unter dem Code für Schritt 1 einen try\-Block, um alle Ausnahmen abzufangen, die während der Ausführung des Diensts ausgelöst werden.  
  
     [!code-csharp[htPublishMetadataCode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#2)]
     [!code-vb[htPublishMetadataCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#2)]  
  
     [!code-csharp[htPublishMetadataCode#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#3)]
     [!code-vb[htPublishMetadataCode#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#3)]  
  
3.  Überprüfen Sie, ob der Diensthost bereits ein <xref:System.ServiceModel.Description.ServiceMetadataBehavior> enthält. Ist dies nicht der Fall, erstellen Sie eine neue <xref:System.ServiceModel.Description.ServiceMetadataBehavior>\-Instanz.  
  
     [!code-csharp[htPublishMetadataCode#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#4)]
     [!code-vb[htPublishMetadataCode#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#4)]  
  
4.  Legen Sie die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A>\-Eigenschaft auf `true.` fest.  
  
     [!code-csharp[htPublishMetadataCode#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#5)]
     [!code-vb[htPublishMetadataCode#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#5)]  
  
5.  Das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>\-Objekt enthält die <xref:System.ServiceModel.Description.MetadataExporter>\-Eigenschaft.Das <xref:System.ServiceModel.Description.MetadataExporter>\-Objekt enthält die <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>\-Eigenschaft.Legen Sie den Wert der <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>\-Eigenschaft auf <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> fest.Die <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>\-Eigenschaft kann auch auf <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A> festgelegt werden.Nach dem Festlegen auf <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> erstellt das Metadatenexportprogramm Richtlinieninformationen mit Metadaten gemäß der WS\-Richtlinie 1.5.Nach dem Festlegen auf <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A> erstellt das Metadatenexportprogramm Richtlinieninformationen gemäß der WS\-Richtlinie 1.2.  
  
     [!code-csharp[htPublishMetadataCode#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#6)]
     [!code-vb[htPublishMetadataCode#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#6)]  
  
6.  Fügen Sie die <xref:System.ServiceModel.Description.ServiceMetadataBehavior>\-Instanz der Verhaltensauflistung des Diensthosts hinzu.  
  
     [!code-csharp[htPublishMetadataCode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#7)]
     [!code-vb[htPublishMetadataCode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#7)]  
  
7.  Fügen Sie dem Diensthost den Endpunkt für den Metadatenaustausch hinzu.  
  
     [!code-csharp[htPublishMetadataCode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#8)]
     [!code-vb[htPublishMetadataCode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#8)]  
  
8.  Fügen Sie dem Diensthost einen Anwendungsendpunkt hinzu.  
  
     [!code-csharp[htPublishMetadataCode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#9)]
     [!code-vb[htPublishMetadataCode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#9)]  
  
    > [!NOTE]
    >  Wenn Sie dem Dienst keine Endpunkte hinzufügen, werden von der Runtime automatisch Standardendpunkte hinzugefügt.Da in diesem Beispiel das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> des Diensts auf `true` festgelegt ist, ist für den Dienst die Veröffentlichung von Metadaten aktiviert.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Standardendpunkten finden Sie unter [Vereinfachte Konfiguration](../../../../docs/framework/wcf/simplified-configuration.md) und [Vereinfachte Konfiguration für WCF\-Dienste](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
9. Öffnen Sie den Diensthost, und warten Sie auf eingehende Aufrufe.Schließen Sie den Diensthost, wenn der Benutzer die Eingabetaste drückt.  
  
     [!code-csharp[htPublishMetadataCode#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#10)]
     [!code-vb[htPublishMetadataCode#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#10)]  
  
10. Erstellen Sie die Konsolenanwendung, und führen Sie sie aus.  
  
11. Rufen Sie mithilfe des Internet Explorers die Basisadresse des Diensts auf \(in diesem Beispiel http:\/\/localhost:8001\/MetadataSample\), und stellen Sie sicher, dass die Metadatenveröffentlichung aktiviert ist.Es sollte eine Webseite angezeigt werden, die am oberen Rand den Text "Einfacher Dienst" und unmittelbar darunter den Text "Sie haben einen Dienst erstellt" enthält. Wenn nicht, wird oben auf der Ergebnisseite folgende Meldung angezeigt: "Das Veröffentlichen von Metadaten für diesen Dienst ist derzeit deaktiviert."  
  
## Beispiel  
 Im folgenden Codebeispiel wird die Implementierung eines einfachen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensts veranschaulicht, der Metadaten für diesen Dienst im Code veröffentlicht.  
  
 [!code-csharp[htPublishMetadataCode#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#11)]
 [!code-vb[htPublishMetadataCode#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#11)]  
  
## Siehe auch  
 [Gewusst wie: Hosten eines WCF\-Diensts in einer verwalteten Anwendung](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)   
 [Selbst gehostete Dienste](../../../../docs/framework/wcf/samples/self-host.md)   
 [Übersicht über die Metadatenarchitektur](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)   
 [Verwenden von Metadaten](../../../../docs/framework/wcf/feature-details/using-metadata.md)   
 [Gewusst wie: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)