---
title: "Grundlagen des generierten Clientcodes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c3f6e4b0-1131-4c94-aa39-a197c5c2f2ca
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Grundlagen des generierten Clientcodes
Mit dem [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) werden Clientcode und eine Clientanwendungs\-Konfigurationsdatei zum Erstellen von Clientanwendungen generiert. Dieses Thema bietet Beispiele für generierten Code für standardmäßige Dienstvertragszenarien.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Erstellen einer Clientanwendung mit dem generierten Code finden Sie unter [Übersicht über den WCF\-Client](../../../../docs/framework/wcf/wcf-client-overview.md).  
  
## Übersicht  
 Wenn Sie [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] zum Generieren von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Clienttypen für Ihr Projekt verwenden, müssen Sie den generierten Clientcode normalerweise nicht untersuchen. Wenn Sie keine Entwicklungsumgebung verwenden, die die gleichen Dienste für Sie ausführt, können Sie mit einem Tool wie Svcutil.exe Clientcode generieren und dann mithilfe dieses Codes die Clientanwendung erstellen.  
  
 Da Svcutil.exe über mehrere Optionen zum Ändern der generierten Typinformationen verfügt, werden in diesem Thema nicht alle Szenarien erläutert. Die folgenden Standardaufgaben schließen jedoch die Suche nach generiertem Code ein:  
  
-   Das Identifizieren von Dienstvertragsschnittstellen.  
  
-   Das Identifizieren der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientklasse.  
  
-   Das Identifizieren von Datentypen.  
  
-   Das Identifizieren von Rückrufverträgen für Duplexdienste.  
  
-   Das Identifizieren der Hilfsdienstvertrag\-Kanalschnittstelle.  
  
### Das Suchen von Dienstvertragschnittstellen.  
 Suchen Sie bei der Suche nach Schnittstellen für Dienstvertragmodelle mit dem <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=fullName>\-Attribut markierte Schnittstellen. Die Suche nach diesem Attribute mit schnellem Lesen kann wegen des Vorhandenseins anderer Attribute und der für das Attribut selbst festgelegten expliziten Eigenschaften häufig schwierig sein. Beachten Sie, dass die Dienstvertragschnittstelle und die Clientvertragschnittstelle zwei verschiedene Typen sind. Im folgenden Codebeispiel wird der ursprüngliche Dienstvertrag gezeigt.  
  
 [!code-csharp[C_GeneratedCodeFiles#22](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#22)]  
  
 Im folgenden Codebeispiel wird der gleiche Dienstvertrag gezeigt, wie von Svcutil.exe generiert.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Sie können die generierte Dienstvertragschnittstelle zusammen mit der <xref:System.ServiceModel.ChannelFactory?displayProperty=fullName>\-Klasse zum Erstellen eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Kanalobjekts für das Aufrufen von Dienstvorgängen verwenden.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Vorgehensweise: Verwenden der ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md).  
  
### Suchen von WCF\-Clientklassen  
 Suchen Sie bei der Suche nach der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientklasse, die den zu verwendenden Dienstvertrag implementiert, nach einer Erweiterung von <xref:System.ServiceModel.ClientBase%601?displayProperty=fullName>, wobei der Typparameter die Dienstvertragschnittstelle ist, die Sie zuvor gefunden haben und die diese Schnittstelle erweitert. Im folgenden Codebeispiel wird die <xref:System.ServiceModel.ClientBase%601>\-Klasse vom Typ `ISampleService` gezeigt.  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 Sie können diese [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientklasse verwenden, indem Sie eine neue Instanz davon erstellen und die Methoden aufrufen, die sie implementiert. Diese Methoden rufen den Dienstvorgang auf, der für die Interaktion mit ihr konzipiert und konfiguriert ist.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Übersicht über den WCF\-Client](../../../../docs/framework/wcf/wcf-client-overview.md).  
  
> [!NOTE]
>  Wenn SvcUtil.exe eine WCF\-Clientklasse generiert, wird ihr ein <xref:System.Diagnostics.DebuggerStepThroughAttribute> hinzugefügt, das die schrittweise Ausführung der WCF\-Clientklasse durch Debugger verhindert.  
  
### Suchen von Datentypen  
 Die grundlegendste Methode zum Suchen von Datentypen im generierten Code ist die Identifizierung des in einem Vertrag angegebenen Typnamens und die Suche des Codes für diese Typdeklaration. Zum Beispiel gibt der folgende Vertrag an, dass `SampleMethod` einen SOAP\-Fehler des Typs `microsoft.wcf.documentation.SampleFault` zurückgeben kann.  
  
 [!code-csharp[C_GeneratedCodeFiles#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#11)]  
  
 Durch die Suche nach `SampleFault` wird die folgende Typdeklaration gesucht.  
  
 [!code-csharp[C_GeneratedCodeFiles#30](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#30)]  
  
 In diesem Fall ist der Datentyp der durch eine bestimmte Ausnahme auf dem Client ausgelöste Detailtyp, eine <xref:System.ServiceModel.FaultException%601>, wobei der Detailtypparameter `microsoft.wcf.documentation.SampleFault` ist.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Datentypen finden Sie unter [Angeben von Datenübertragung in Dienstverträgen](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Behandeln von Ausnahmen in Clients finden Sie unter [Senden und Empfangen von Fehlern](../../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
### Suchen von Rückrufverträgen für Duplexdienste  
 Wenn Sie einen Dienstvertrag finden, bei dem die Vertragschnittstelle einen Wert für die <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=fullName>\-Eigenschaft angibt, dann gibt dieser Vertrag einen Duplexvertrag an. Duplexverträge erfordern, dass die Clientanwendung eine Rückrufklasse erstellt, die den Rückrufvertrag implementiert und eine Instanz dieser Klasse an <xref:System.ServiceModel.DuplexClientBase%601?displayProperty=fullName> oder <xref:System.ServiceModel.DuplexChannelFactory%601?displayProperty=fullName> zur Kommunikation mit dem Dienst übergibt.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Duplexclients finden Sie unter [Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md).  
  
 Der folgende Vertrag gibt einen Rückrufvertrag vom Typ `SampleDuplexHelloCallback` an.  
  
 [!code-csharp[C_GeneratedCodeFiles#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/duplexproxycode.cs#2)]
 [!code-vb[C_GeneratedCodeFiles#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_generatedcodefiles/vb/duplexproxycode.vb#2)]  
  
 Durch die Suche nach diesem Rückrufvertrag wird die folgende Schnittstelle gesucht, die die Clientanwendung implementieren muss.  
  
 [!code-csharp[C_GeneratedCodeFiles#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/duplexproxycode.cs#4)]
 [!code-vb[C_GeneratedCodeFiles#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_generatedcodefiles/vb/duplexproxycode.vb#4)]  
  
### Suchen von Dienstvertrag\-Kanalschnittstellen  
 Beim Verwenden der <xref:System.ServiceModel.ChannelFactory>\-Klasse mit einer Dienstvertragschnittstelle muss diese in eine <xref:System.ServiceModel.IClientChannel?displayProperty=fullName>\-Schnittstelle umgewandelt werden, um den Kanal explizit zu öffnen, zu schließen oder abzubrechen. Zum Erleichtern der Arbeit generiert das Tool Svcutil.exe auch eine Hilfsschnittstelle, die die Dienstvertragschnittstelle und <xref:System.ServiceModel.IClientChannel> implementiert, wodurch die Interaktion mit der Clientkanalinfrastruktur ohne Umwandlung ermöglicht wird. Im folgenden Code wird die Definition eines Hilfsclientkanals, der den vorangehenden Dienstvertrag implementiert, veranschaulicht.  
  
 [!code-csharp[C_GeneratedCodeFiles#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#13)]  
  
## Siehe auch  
 [Übersicht über den WCF\-Client](../../../../docs/framework/wcf/wcf-client-overview.md)