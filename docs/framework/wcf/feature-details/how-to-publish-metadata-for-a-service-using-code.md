---
title: 'Gewusst wie: Veröffentlichen von Metadaten für einen Dienst über den Code'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 51407e6d-4d87-42d5-be7c-9887b8652006
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c3d2fd1222539ec8017846069e7eda9a2c503f22
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-publish-metadata-for-a-service-using-code"></a>Gewusst wie: Veröffentlichen von Metadaten für einen Dienst über den Code
Dies ist eines der beiden "Gewusst wie"-Themen, in denen erläutert wird, wie Sie Metadaten für einen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienst veröffentlichen. Es gibt zwei Möglichkeiten, wie ein Dienst Metadaten veröffentlichen kann: mit einer Konfigurationsdatei und mit Code. In diesem Thema wird das Veröffentlichen von Metadaten für einen Dienst mithilfe von Code dargestellt.  
  
> [!CAUTION]
>  In diesem Thema wird das Veröffentlichen von Metadaten auf unsichere Weise dargestellt. Jeder Client kann Metadaten vom Dienst abrufen. Informationen zum sicheren Veröffentlichen von Metadaten für einen Dienst finden Sie unter [benutzerdefinierter sicherer Metadatenendpunkt](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).  
  
 Weitere Informationen zum Veröffentlichen von Metadaten in einer Konfigurationsdatei finden Sie unter [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md). Die Veröffentlichung von Metadaten ermöglicht Clients, Metadaten über eine WS-Transfer-GET-Anforderung oder eine HTTP/GET-Anforderung mithilfe einer `?wsdl`-Abfragezeichenfolge abzurufen. Erstellen Sie einen grundlegenden WCF-Dienst, um sicherzustellen, dass der Code funktioniert. Im folgenden Code wird ein grundlegender, selbst gehosteter Dienst bereitgestellt:  
  
 [!code-csharp[htPublishMetadataCode#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#0)]
 [!code-vb[htPublishMetadataCode#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#0)]  
  
### <a name="to-publish-metadata-in-code"></a>So veröffentlichen Sie Metadaten im Code  
  
1.  Instanziieren Sie in der Hauptmethode einer Konsolenanwendung ein <xref:System.ServiceModel.ServiceHost>-Objekt, indem Sie den Diensttyp und die Basisadresse übergeben.  
  
     [!code-csharp[htPublishMetadataCode#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#1)]
     [!code-vb[htPublishMetadataCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#1)]  
  
2.  Erstellen Sie unmittelbar unter dem Code für Schritt&#160;1 einen try-Block, um alle Ausnahmen abzufangen, die während der Ausführung des Diensts ausgelöst werden.  
  
     [!code-csharp[htPublishMetadataCode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#2)]
     [!code-vb[htPublishMetadataCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#2)]  
  
     [!code-csharp[htPublishMetadataCode#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#3)]
     [!code-vb[htPublishMetadataCode#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#3)]  
  
3.  Überprüfen Sie, ob der Diensthost bereits ein <xref:System.ServiceModel.Description.ServiceMetadataBehavior> enthält. Ist dies nicht der Fall, erstellen Sie eine neue <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Instanz.  
  
     [!code-csharp[htPublishMetadataCode#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#4)]
     [!code-vb[htPublishMetadataCode#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#4)]  
  
4.  Legen Sie die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A>-Eigenschaft auf `true.` fest.  
  
     [!code-csharp[htPublishMetadataCode#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#5)]
     [!code-vb[htPublishMetadataCode#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#5)]  
  
5.  Das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Objekt enthält die <xref:System.ServiceModel.Description.MetadataExporter>-Eigenschaft. Das <xref:System.ServiceModel.Description.MetadataExporter>-Objekt enthält die <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>-Eigenschaft. Legen Sie den Wert der <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>-Eigenschaft auf <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> fest. Die <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>-Eigenschaft kann auch auf <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A> festgelegt werden. Bei Festlegung auf <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> das metadatenexportprogramm Richtlinieninformationen mit Metadaten, die "WS-Policy 1.5 entspricht. Nach dem Festlegen auf <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A> erstellt das Metadatenexportprogramm Richtlinieninformationen gemäß der WS-Richtlinie 1.2.  
  
     [!code-csharp[htPublishMetadataCode#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#6)]
     [!code-vb[htPublishMetadataCode#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#6)]  
  
6.  Fügen Sie die <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Instanz der Verhaltensauflistung des Diensthosts hinzu.  
  
     [!code-csharp[htPublishMetadataCode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#7)]
     [!code-vb[htPublishMetadataCode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#7)]  
  
7.  Fügen Sie dem Diensthost den Endpunkt für den Metadatenaustausch hinzu.  
  
     [!code-csharp[htPublishMetadataCode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#8)]
     [!code-vb[htPublishMetadataCode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#8)]  
  
8.  Fügen Sie dem Diensthost einen Anwendungsendpunkt hinzu.  
  
     [!code-csharp[htPublishMetadataCode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#9)]
     [!code-vb[htPublishMetadataCode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#9)]  
  
    > [!NOTE]
    >  Wenn Sie dem Dienst keine Endpunkte hinzufügen, werden von der Runtime automatisch Standardendpunkte hinzugefügt. Da in diesem Beispiel das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> des Diensts auf `true` festgelegt ist, ist für den Dienst die Veröffentlichung von Metadaten aktiviert. Weitere Informationen zu Standardendpunkte, finden Sie unter [vereinfachte Konfiguration](../../../../docs/framework/wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
9. Öffnen Sie den Diensthost, und warten Sie auf eingehende Aufrufe. Schließen Sie den Diensthost, wenn der Benutzer die Eingabetaste drückt.  
  
     [!code-csharp[htPublishMetadataCode#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#10)]
     [!code-vb[htPublishMetadataCode#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#10)]  
  
10. Erstellen Sie die Konsolenanwendung und führen Sie sie aus.  
  
11. Verwenden Sie Internet Explorer, um die Basisadresse des Diensts zu suchen (http://localhost:8001/MetadataSample in diesem Beispiel) und stellen Sie sicher, dass die Metadatenveröffentlichung aktiviert ist. Es sollte eine Webseite angezeigt werden, die am oberen Rand den Text "Einfacher Dienst" und unmittelbar darunter den Text "Sie haben einen Dienst erstellt" enthält. Wenn nicht, wird oben auf der Ergebnisseite folgende Meldung angezeigt: "Das Veröffentlichen von Metadaten für diesen Dienst ist derzeit deaktiviert."  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die Implementierung eines einfachen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensts veranschaulicht, der Metadaten für diesen Dienst im Code veröffentlicht.  
  
 [!code-csharp[htPublishMetadataCode#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#11)]
 [!code-vb[htPublishMetadataCode#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#11)]  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise Hosten eines WCF-Diensts in einer verwalteten Anwendung](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)  
 [Selbst gehostete Dienste](../../../../docs/framework/wcf/samples/self-host.md)  
 [Übersicht über die Metadatenarchitektur](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)  
 [Verwenden von Metadaten](../../../../docs/framework/wcf/feature-details/using-metadata.md)  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
