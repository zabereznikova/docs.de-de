---
title: "Vorgehensweise: Abrufen von Metadaten und Implementieren eines kompatiblen Diensts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f6f3a2b9-c8aa-4b0b-832c-ec2927bf1163
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Vorgehensweise: Abrufen von Metadaten und Implementieren eines kompatiblen Diensts
Oftmals werden Dienste nicht von derselben Person entworfen und anschließend implementiert. In Umgebungen, in denen zusammenwirkende Anwendungen wichtig sind, können Verträge in Web Services Description Language (WSDL) entworfen oder beschrieben werden, und ein Entwickler muss einen Dienst implementieren, der mit dem bereitgestellten Vertrag kompatibel ist. Möglicherweise möchten Sie auch einen vorhandenen Dienst an [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] migrieren, das Übertragungsformat jedoch beibehalten. Außerdem werden Aufrufende von Duplexverträgen dazu aufgefordert, auch einen Rückrufvertrag zu implementieren.  
  
 In diesen Fällen müssen Sie verwenden die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) (oder ein vergleichbares Tool) eine dienstvertragsschnittstelle in einer verwalteten Sprache zu generieren, die Sie implementieren können, um die Anforderungen des Vertrags zu erfüllen. In der Regel die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) wird verwendet, um ein Dienstvertrag abgerufen, die mit einer Kanalfactory verwendet wird oder ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Clienttyp sowie mit einer Konfigurationsdatei, die die korrekte Bindung und Adresse eingerichtet. Um die generierte Konfigurationsdatei zu verwenden, müssen Sie diese in eine Dienstkonfigurationsdatei ändern. Sie müssen möglicherweise auch den Dienstvertrag ändern.  
  
### <a name="to-retrieve-data-and-implement-a-compliant-service"></a>So rufen Sie Daten ab und implementieren einen kompatiblen Dienst:  
  
1.  Verwenden der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) mit Metadatendateien oder einen Metadatenendpunkt zum Erzeugen einer Codedatei.  
  
2.  Suchen Sie den Bereich der Ausgabe Codedatei mit der Oberfläche von Interesse sind (im Fall gibt es mehr als eine), die mit der <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=fullName> Attribut. Das folgende Codebeispiel zeigt die beiden Schnittstellen, die von generierten [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Die erste Schnittstelle (`ISampleService`) ist die Dienstvertragsschnittstelle, die zum Erstellen eines kompatiblen Diensts implementiert wird. Die zweite (`ISampleServiceChannel`) ist eine Hilfsschnittstelle für die Clientverwendung, die sowohl die dienstvertragsschnittstelle erweitert und <xref:System.ServiceModel.IClientChannel?displayProperty=fullName> und ist für die Verwendung in einer Clientanwendung.  
  
     [!code-csharp[ClientProxyCodeSample#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#2)]  
  
3.  Wenn die WSDL keine Antwortaktion für alle Vorgänge angibt, die generierten Vorgangsverträge verfügen möglicherweise die <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> -Eigenschaft auf das Platzhalterzeichen (*) festgelegt. Entfernen Sie diese Eigenschafteneinstellung. Andernfalls können die Metadaten bei der Implementierung der Dienstvertragsmetadaten nicht für diese Vorgänge exportiert werden.  
  
4.  Implementieren Sie die Schnittstelle in einer Klasse, und hosten Sie den Dienst. Ein Beispiel finden Sie unter [Gewusst wie: Implementieren eines Dienstvertrags](../../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md), oder eine einfache Implementierung unten im Beispielabschnitt unter.  
  
5.  In der Clientkonfiguration-Datei mit den [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) generiert wird, ändern die [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) Konfigurationsabschnitt, der eine [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) Konfigurationsabschnitt. (Ein Beispiel für eine generierte Clientanwendungs-Konfigurationsdatei finden Sie im folgenden "Beispiel"-Abschnitt.)  
  
6.  Innerhalb der [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) Konfiguration im Abschnitt, erstellen Sie eine `name` -Attribut in der [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) Konfigurationsabschnitt für die dienstimplementierung.  
  
7.  Legen Sie das `name`-Dienstattribut auf den Konfigurationsnamen für die Dienstimplementierung fest.  
  
8.  Fügen Sie die Endpunktkonfigurationselemente hinzu, die den implementierten Dienstvertrag für den Dienstkonfigurationsabschnitt verwenden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, die Mehrheit der einer Codedatei durch Ausführen der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) für Metadaten-Dateien.  
  
 Dies wird im folgenden Code veranschaulicht:  
  
-   Die Dienstvertragsschnittstelle (`ISampleService`), die bei der Implementierung den Vertragsanforderungen entspricht.  
  
-   Die Hilfsschnittstelle für die Clientverwendung, die sowohl die dienstvertragsschnittstelle erweitert und <xref:System.ServiceModel.IClientChannel?displayProperty=fullName> und ist für die Verwendung in einer Clientanwendung (`ISampleServiceChannel`).  
  
-   Die Hilfsklasse, die erweitert <xref:System.ServiceModel.ClientBase%601?displayProperty=fullName> und ist für die Verwendung in einer Clientanwendung (`SampleServiceClient`).  
  
-   Die vom Dienst generierte Konfigurationsdatei.  
  
-   Eine einfache `ISampleService`-Dienstimplementierung.  
  
-   Eine Konvertierung der clientseitigen Konfigurationsdatei in eine dienstseitige Version.  
  
 [!code-csharp[ClientProxyCodeSample#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#1)]  
  
 <!-- TODO: review snippet reference [!code[ClientProxyCodeSample#10](../../../../samples/snippets/common/VS_Snippets_CFX/clientproxycodesample/common/client.exe.config#10)]  -->
 <!-- TODO: review snippet reference [!code-csharp[ClientProxyCodeSample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/client.exe.config#10)]  -->  
  
 [!code-csharp[ClientProxyCodeSample#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.cs#5)]  
  
 <!-- TODO: review snippet reference [!code[ClientProxyCodeSample#20](../../../../samples/snippets/common/VS_Snippets_CFX/clientproxycodesample/common/hostapplication.exe.config#20)]  -->
 <!-- TODO: review snippet reference [!code-csharp[ClientProxyCodeSample#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.exe.config#20)]  -->  
  
## <a name="see-also"></a>Siehe auch  
 [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)