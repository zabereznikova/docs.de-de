---
title: "Vorgehensweise: Konfigurieren eines WCF-Diensts f&#252;r die Zusammenarbeit mit ASP.NET Webdienstclients | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Vorgehensweise: Konfigurieren eines WCF-Diensts f&#252;r die Zusammenarbeit mit ASP.NET Webdienstclients
So konfigurieren Sie eine [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] -Dienstendpunkt, Interoperabilität mit [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Webdienstclients ist, verwenden Sie die <xref:System.ServiceModel.BasicHttpBinding?displayProperty=fullName> Typ als Bindungstyp für den Dienstendpunkt.  
  
 Sie können für die Bindung auch Unterstützung für HTTPS und Clientauthentifizierung auf Transportebene aktivieren. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Webdienstclients unterstützen keine MTOM-nachrichtencodierung, damit der <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=fullName> Eigenschaft sollte den Standardwert bleiben <xref:System.ServiceModel.WSMessageEncoding?displayProperty=fullName>. ASP.NET-Webdienstclients unterstützen keine WS-Security, damit der <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=fullName> sollte festgelegt werden, um <xref:System.ServiceModel.BasicHttpSecurityMode>.  
  
 Zu den Metadaten für eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Dienst zum [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web Service Tools zur Proxygenerierung (, also [Web Services Description Language Tool (Wsdl.exe)](http://go.microsoft.com/fwlink/?LinkId=73833), [Webdienste-Suchtool (Disco.exe)](http://go.microsoft.com/fwlink/?LinkId=73834), und die Funktion "Webverweis hinzufügen" in Visual Studio), Sie sollten einen HTTP/GET-Metadatenendpunkt verfügbar zu machen.  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-code"></a>So fügen Sie einen WCF-Endpunkt hinzu, der im Code mit ASP.NET-Webdienstclients kompatibel ist  
  
1.  Erstellen Sie ein neues <xref:System.ServiceModel.BasicHttpBinding> Instanz  
  
2.  Aktivieren Sie optional transportsicherheit für diese dienstendpunktbindung, indem Festlegen des Sicherheitsmodus für die Bindung an <xref:System.ServiceModel.BasicHttpSecurityMode>. Weitere Informationen finden Sie unter [Transportsicherheit](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3.  Fügen Sie dem Diensthost einen neuen Anwendungsendpunkt mit der Bindungsinstanz hinzu, die Sie soeben erstellt haben. Ausführliche Informationen zum Hinzufügen eines Dienstendpunkts im Code finden Sie unter der [Gewusst wie: Erstellen eines Dienstendpunkts im Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
4.  Aktivieren Sie einen HTTP/GET-Metadatenendpunkt für Ihren Dienst. Weitere Informationen finden Sie [Gewusst wie: Veröffentlichen von Metadaten für einen Dienst mithilfe von Code](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-a-configuration-file"></a>So fügen Sie einen WCF-Endpunkt, der mit ASP.NET-Webdienstclients kompatibel ist, einer Konfigurationsdatei hinzu.  
  
1.  Erstellen Sie ein neues <xref:System.ServiceModel.BasicHttpBinding> Bindungskonfiguration. Weitere Informationen finden Sie unter der [Gewusst wie: Angeben einer Dienstbindung in einer Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
2.  Aktivieren Sie optional transportsicherheit für diese Dienstendpunkt-Bindungskonfiguration durch Festlegen des Sicherheitsmodus für die Bindung an <xref:System.ServiceModel.BasicHttpSecurityMode>. Weitere Informationen finden Sie unter [Transportsicherheit](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3.  Konfigurieren Sie einen neuen Anwendungsendpunkt für Ihren Dienst, indem Sie die Bindungskonfiguration verwenden, die Sie gerade erstellt haben. Ausführliche Informationen zum Hinzufügen eines Dienstendpunkts in einer Konfigurationsdatei finden Sie unter der [Gewusst wie: Erstellen eines Dienstendpunkts in der Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).  
  
4.  Aktivieren Sie einen HTTP/GET-Metadatenendpunkt für Ihren Dienst. Weitere Informationen finden Sie die [Gewusst wie: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Beispielcode zeigt das Hinzufügen eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Endpunkts, der im Code und alternativ in den Konfigurationsdateien kompatibel mit den [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Webdienstclients ist.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
  
 <!-- TODO: review snippet reference [!code[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  -->  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Erstellen eines Dienstendpunkts im Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)   
 [Gewusst wie: Veröffentlichen von Metadaten für einen Dienst mithilfe von Code](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)   
 [Gewusst wie: angeben eine Dienstbindung in einer Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)   
 [Gewusst wie: Erstellen eines Dienstendpunkts in der Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)   
 [Gewusst wie: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)   
 [Transportsicherheit](../../../../docs/framework/wcf/feature-details/transport-security.md)   
 [Mithilfe von Metadaten](../../../../docs/framework/wcf/feature-details/using-metadata.md)