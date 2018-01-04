---
title: Kontrollieren des Ressourcenverbrauchs und Verbessern der Leistung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a829669-5f76-4c88-80ec-92d0c62c0660
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ecb8ae5edfb35ccaffecbfb4e960d3f4a46bad0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="controlling-resource-consumption-and-improving-performance"></a>Kontrollieren des Ressourcenverbrauchs und Verbessern der Leistung
In diesem Thema werden verschiedene Eigenschaften in unterschiedlichen Bereichen der [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Architektur beschrieben, die den Ressourcenverbrauch kontrollieren und Einfluss auf die Leistungsmetriken haben.  
  
## <a name="properties-that-constrain-resource-consumption-in-wcf"></a>Eigenschaften, die den Ressourcenverbrauch in WCF einschränken  
 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] wendet Einschränkungen auf bestimmte Typen von Prozessen an, entweder zum Zwecke der Sicherheit oder der Leistung. Diese Einschränkungen treten in zwei Hauptformen auf, jeweils als Kontingente und Drosselungen. *Kontingente* sind Beschränkungen, die sobald Sie erreicht oder überschritten eine sofortige Ausnahme irgendwann im System verursachen. *Schränkt* sind Beschränkungen, die nicht sofort durch eine Ausnahme ausgelöst werden können. Stattdessen wird beim Erreichen einer Drosselungsbeschränkung der Prozess fortgesetzt, jedoch innerhalb der durch den Drosselungswert festgelegten Grenzen. Diese eingeschränkte Verarbeitung löst möglicherweise an anderer Stelle eine Ausnahme aus, dies hängt jedoch von der jeweiligen Anwendung ab.  
  
 Zusätzlich zu der Unterscheidung zwischen Kontingenten und Drosselungen befinden sich einige einschränkende Eigenschaften auf der Serialisierungsebene, auf der Transportebene und auf der Anwendungsebene. Beispielsweise wird das Kontingent <xref:System.ServiceModel.Channels.TransportBindingElement.MaxReceivedMessageSize%2A?displayProperty=nameWithType>, das von allen vom System bereitgestellten Transportbindungselementen implementiert wird, standardmäßig auf 65.536 Byte festgelegt, um böswillige Clients daran zu hindern, Denial-of-Service-Angriffe gegen einen bestimmten Dienst zu starten und dadurch einen überhöhten Speicherbedarf zu verursachen. (I. d. R. können Sie die Leistung erhöhen, indem Sie diesen Wert herabsetzen.)  
  
 Ein Beispiel für ein Serialisierungskontingent ist die <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A?displayProperty=nameWithType>-Eigenschaft, die die maximale Anzahl an Objekten angibt, die das Serialisierungsprogramm in einem einzigen <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A>-Methodenaufruf serialisiert oder deserialisiert. Ein Beispiel für eine Drosselung auf Anwendungsebene ist die <xref:System.ServiceModel.Dispatcher.ServiceThrottle.MaxConcurrentSessions%2A?displayProperty=nameWithType>-Eigenschaft, die standardmäßig die Anzahl der gleichzeitigen sitzungsbasierten Kanalverbindungen auf "10" beschränkt. (Anders als bei den Kontingenten setzt die Anwendung die Verarbeitung fort, wenn dieser Drosselungswert erreicht ist, jedoch akzeptiert sie keine neuen sitzungsbasierten Kanäle, was bedeutet, dass neue Clients erst dann eine Verbindung herstellen können, wenn einer der anderen sitzungsbasierten Kanäle beendet wurde.)  
  
 Diese Steuerelemente wurden dafür entwickelt, übliche Gegenmaßnahmen gegen bestimmte Arten von Angriffen einzuleiten oder die Leistungsmetriken wie Speicherbeanspruchung, Startzeit usw. zu verbessern. Jedoch können diese Steuerelemente, je nach Anwendung, auch eine Beeinträchtigung der Anwendungsleistung zur Folge haben oder dazu führen, dass die Anwendung gar nicht mehr funktioniert. Zum Beispiel kann eine Anwendung, die für das Videostreaming entworfen wurde, die standardmäßige <xref:System.ServiceModel.Channels.TransportBindingElement.MaxReceivedMessageSize%2A?displayProperty=nameWithType>-Eigenschaft leicht überschreiten. Dieses Thema liefert einen Überblick über die verschiedenen Steuerelemente für Anwendungen aller [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Ebenen. Außerdem werden verschiedene Methoden beschrieben, Informationen darüber anzufordern, ob eine Einstellung Ihre Anwendung behindert, und es wird erklärt, wie unterschiedliche Probleme behoben werden können. Die meisten Drosselungen und einige Kontingente sind auf der Anwendungsebene verfügbar, auch wenn die Basiseigenschaft eine Serialisierungs- oder Transportbeschränkung ist. So können Sie z. B. die <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A?displayProperty=nameWithType>-Eigenschaft mithilfe der <xref:System.ServiceModel.ServiceBehaviorAttribute.MaxItemsInObjectGraph%2A?displayProperty=nameWithType>-Eigenschaft der Dienstklasse festlegen.  
  
> [!NOTE]
>  Wenn Sie ein bestimmtes Problem haben, lesen Sie zuerst die [Schnelleinstieg zur Problembehandlung in WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) um festzustellen, ob das Problem (und eine Lösung) dort aufgeführt ist.  
  
 Eigenschaften, mit denen Serialisierungsprozesse eingeschränkt sind in aufgeführt [Sicherheitsüberlegungen zu Daten](../../../docs/framework/wcf/feature-details/security-considerations-for-data.md). Eigenschaften, die den Verbrauch von Ressourcen, die im Zusammenhang mit Transporte einschränken in aufgelisteten [Transportkontingente](../../../docs/framework/wcf/feature-details/transport-quotas.md). Eigenschaften, die den Verbrauch von Ressourcen auf der Anwendungsschicht einschränken, gehören zur <xref:System.ServiceModel.Dispatcher.ServiceThrottle>-Klasse.  
  
## <a name="detecting-application-and-performance-issues-related-to-quota-settings"></a>Erkennen von Anwendungs- und Leistungsproblemen in Zusammenhang mit den Kontingenteinstellungen  
 Die Standardeinstellungen für die vorangehenden Werte wurden ausgewählt, um eine grundlegende Funktionalität für viele verschiedene Anwendungstypen zu ermöglichen und gleichzeitig einen Schutz vor häufig auftretenden Sicherheitsproblemen zu bieten. Jedoch überschreiten die verschiedenen Anwendungs-Designs möglicherweise eine oder mehrere Drosselungseinstellungen, obwohl die Anwendung ansonsten sicher ist und wie gewünscht funktionieren würde. In einem solchen Fall müssen Sie feststellen, welche Drosselungswerte auf welcher Ebene überschritten werden. Legen Sie anschließend angemessene Maßnahmen zur Erhöhung des Anwendungsdurchsatzes fest.  
  
 In der Regel wird beim Schreiben und Debuggen der Anwendung die <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType>-Eigenschaft in der Konfigurationsdatei oder programmgesteuert auf `true` festgelegt. Dies weist [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] an, Dienstausnahmestapelüberwachungen zum Anzeigen an die Clientanwendung zurückzugeben. Diese Funktion meldet die meisten Ausnahmen auf Anwendungsebene so, dass angezeigt wird, welche Kontingenteinstellungen möglicherweise beteiligt sind, falls das Problem hierdurch verursacht wurde.  
  
 Einige Ausnahmen treten während der Laufzeit außerhalb der Sichtbarkeit der Anwendungsschicht auf und werden nicht mithilfe dieses Mechanismus zurückgegeben. Möglicherweise werden sie auch nicht von einer benutzerdefinierten <xref:System.ServiceModel.Dispatcher.IErrorHandler?displayProperty=nameWithType>-Implementierung gehandhabt. Wenn Sie in einer Entwicklungsumgebung wie Microsoft Visual Studio arbeiten, werden die meisten dieser Ausnahmen automatisch angezeigt. Allerdings können einige Ausnahmen maskiert werden, durch die Entwicklung von umgebungseinstellungen wie z. B. die [nur mein Code](http://go.microsoft.com/fwlink/?LinkId=82174) Einstellungen in Visual Studio 2005.  
  
 Unabhängig von den Fähigkeiten Ihrer Entwicklungsumgebung können Sie die Funktionen der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Ablaufverfolgung und -Nachrichtenprotokollierung verwenden, um alle Ausnahmen zu debuggen und die Leistung Ihrer Anwendung zu verbessern. Weitere Informationen finden Sie unter [Using an Ihre Anwendung beheben Tracing](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).  
  
## <a name="performance-issues-and-xmlserializer"></a>Leistungsprobleme und XmlSerializer  
 Dienste und Clientanwendungen, die Datentypen verwenden, die mit dem <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können, generieren und kompilieren für diese Datentypen während der Laufzeit Code, was zu einem verlangsamten Start führen kann.  
  
> [!NOTE]
>  Vorab generierter Serialisierungscode kann nur in Clientanwendungen und nicht in Diensten verwendet werden.  
  
 Die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) können startleistung für diese Anwendungen durch Generieren der erforderlichen Serialisierungscode aus den kompilierten Assemblys für die Anwendung zu verbessern. Weitere Informationen finden Sie unter [wie: Verbessern der Start Time des WCF-Clientanwendungen mit dem XmlSerializer](../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md).  
  
## <a name="performance-issues-when-hosting-wcf-services-under-aspnet"></a>Leistungsprobleme beim Hosten von WCF-Diensten unter ASP.NET  
 Wird ein WCF-Dienst unter IIS und ASP.NET gehostet, können sich die Konfigurationseinstellungen von IIS und ASP.NET auf den Durchsatz und die Speicherbeanspruchung des WCF-Diensts auswirken.  [!INCLUDE[crabout](../../../includes/crabout-md.md)]Die Leistung von ASP.NET finden Sie unter [verbessern die Leistung von ASP.NET](http://go.microsoft.com/fwlink/?LinkId=186462).  Eine Einstellung, durch die sich unbeabsichtigte Folgen ergeben können, ist <xref:System.Web.Configuration.ProcessModelSection.MinWorkerThreads%2A>. Hierbei handelt es sich um eine Eigenschaft der <xref:System.Web.Configuration.ProcessModelSection>. Verfügt die Anwendung über eine feste oder über eine geringe Anzahl von Clients, lässt sich durch Festlegen von <xref:System.Web.Configuration.ProcessModelSection.MinWorkerThreads%2A> auf "2" bei einem Computer mit mehreren Prozessoren, dessen CPU-Auslastung sich nahe bei 100 Prozent bewegt, möglicherweise ein Leistungsschub beim Durchsatz erzielen. Dieser Leistungszuwachs bringt jedoch auch einen Nachteil mit sich, da sich dadurch auch eine erhöhte Speicherauslastung ergibt, was zu einer geringeren Skalierbarkeit führt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwaltung und Diagnose](../../../docs/framework/wcf/diagnostics/index.md)  
 [Umfangreiche Daten und Streaming](../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)
