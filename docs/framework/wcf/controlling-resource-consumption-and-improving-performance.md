---
title: Kontrollieren des Ressourcenverbrauchs und Verbessern der Leistung
ms.date: 03/30/2017
ms.assetid: 9a829669-5f76-4c88-80ec-92d0c62c0660
ms.openlocfilehash: 7210f71287a2ec763b67dfa033cd9f4dadf6bd34
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543068"
---
# <a name="controlling-resource-consumption-and-improving-performance"></a>Kontrollieren des Ressourcenverbrauchs und Verbessern der Leistung
In diesem Thema werden verschiedene Eigenschaften in verschiedenen Bereichen der Windows Communication Foundation (WCF)-Architektur beschrieben, die zum Steuern des Ressourcenverbrauchs und beeinflussen der Leistungsmetriken verwendet werden.

## <a name="properties-that-constrain-resource-consumption-in-wcf"></a>Eigenschaften, die den Ressourcenverbrauch in WCF einschränken
 Windows Communication Foundation (WCF) wendet Einschränkungen für bestimmte Arten von Prozessen entweder zu Sicherheits-oder Leistungs Zwecken an. Diese Einschränkungen treten in zwei Hauptformen auf, jeweils als Kontingente und Drosselungen. *Kontingente* sind Grenzwerte, die zu einem bestimmten Zeitpunkt im System eine unmittelbare Ausnahme ausgelöst haben, wenn erreicht oder überschritten wird. *Drosselungen* sind Limits, die nicht sofort bewirken, dass eine Ausnahme ausgelöst wird. Stattdessen wird beim Erreichen einer Drosselungsbeschränkung der Prozess fortgesetzt, jedoch innerhalb der durch den Drosselungswert festgelegten Grenzen. Diese eingeschränkte Verarbeitung löst möglicherweise an anderer Stelle eine Ausnahme aus, dies hängt jedoch von der jeweiligen Anwendung ab.

 Zusätzlich zu der Unterscheidung zwischen Kontingenten und Drosselungen befinden sich einige einschränkende Eigenschaften auf der Serialisierungsebene, auf der Transportebene und auf der Anwendungsebene. Beispielsweise wird das Kontingent <xref:System.ServiceModel.Channels.TransportBindingElement.MaxReceivedMessageSize%2A?displayProperty=nameWithType>, das von allen vom System bereitgestellten Transportbindungselementen implementiert wird, standardmäßig auf 65.536 Byte festgelegt, um böswillige Clients daran zu hindern, Denial-of-Service-Angriffe gegen einen bestimmten Dienst zu starten und dadurch einen überhöhten Speicherbedarf zu verursachen. (I. d. R. können Sie die Leistung erhöhen, indem Sie diesen Wert herabsetzen.)

 Ein Beispiel für ein Serialisierungskontingent ist die <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A?displayProperty=nameWithType>-Eigenschaft, die die maximale Anzahl an Objekten angibt, die das Serialisierungsprogramm in einem einzigen <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A>-Methodenaufruf serialisiert oder deserialisiert. Ein Beispiel für eine Drosselung auf Anwendungsebene ist die <xref:System.ServiceModel.Dispatcher.ServiceThrottle.MaxConcurrentSessions%2A?displayProperty=nameWithType>-Eigenschaft, die standardmäßig die Anzahl der gleichzeitigen sitzungsbasierten Kanalverbindungen auf "10" beschränkt. (Anders als bei den Kontingenten setzt die Anwendung die Verarbeitung fort, wenn dieser Drosselungswert erreicht ist, jedoch akzeptiert sie keine neuen sitzungsbasierten Kanäle, was bedeutet, dass neue Clients erst dann eine Verbindung herstellen können, wenn einer der anderen sitzungsbasierten Kanäle beendet wurde.)

 Diese Steuerelemente wurden dafür entwickelt, eine übliche Entschärfung gegen bestimmte Arten von Angriffen einzuleiten oder die Leistungsmetriken wie Speicherbeanspruchung, Startzeit usw. zu verbessern. Jedoch können diese Steuerelemente, je nach Anwendung, auch eine Beeinträchtigung der Anwendungsleistung zur Folge haben oder dazu führen, dass die Anwendung gar nicht mehr funktioniert. Zum Beispiel kann eine Anwendung, die für das Videostreaming entworfen wurde, die standardmäßige <xref:System.ServiceModel.Channels.TransportBindingElement.MaxReceivedMessageSize%2A?displayProperty=nameWithType>-Eigenschaft leicht überschreiten. Dieses Thema bietet einen Überblick über die verschiedenen Steuerelemente, die auf allen Ebenen von WCF auf Anwendungen angewendet werden, und beschreibt verschiedene Möglichkeiten, weitere Informationen dazu zu erhalten, ob eine Einstellung Ihre Anwendung behindert und wie verschiedene Probleme behoben werden können. Die meisten Drosselungen und einige Kontingente sind auf der Anwendungsebene verfügbar, auch wenn die Basiseigenschaft eine Serialisierungs- oder Transportbeschränkung ist. So können Sie z. B. die <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A?displayProperty=nameWithType>-Eigenschaft mithilfe der <xref:System.ServiceModel.ServiceBehaviorAttribute.MaxItemsInObjectGraph%2A?displayProperty=nameWithType>-Eigenschaft der Dienstklasse festlegen.

> [!NOTE]
> Wenn Sie ein bestimmtes Problem haben, lesen Sie zunächst den [Schnellstart](wcf-troubleshooting-quickstart.md) für die WCF-Problembehandlung, um zu sehen, ob Ihr Problem (und eine Lösung) hier aufgeführt ist.

 Eigenschaften, die Serialisierungsprozesse einschränken, werden unter [Sicherheitsüberlegungen für Daten](./feature-details/security-considerations-for-data.md)aufgeführt. Eigenschaften, die den Verbrauch von Ressourcen einschränken, die sich auf Transporte beziehen, werden unter [Transport Kontingente](./feature-details/transport-quotas.md)aufgeführt. Eigenschaften, die den Verbrauch von Ressourcen auf der Anwendungsschicht einschränken, gehören zur <xref:System.ServiceModel.Dispatcher.ServiceThrottle>-Klasse.

## <a name="detecting-application-and-performance-issues-related-to-quota-settings"></a>Erkennen von Anwendungs- und Leistungsproblemen in Zusammenhang mit den Kontingenteinstellungen
 Die Standardeinstellungen für die vorangehenden Werte wurden ausgewählt, um eine grundlegende Funktionalität für viele verschiedene Anwendungstypen zu ermöglichen und gleichzeitig einen Schutz vor häufig auftretenden Sicherheitsproblemen zu bieten. Jedoch überschreiten die verschiedenen Anwendungs-Designs möglicherweise eine oder mehrere Drosselungseinstellungen, obwohl die Anwendung ansonsten sicher ist und wie gewünscht funktionieren würde. In einem solchen Fall müssen Sie feststellen, welche Drosselungswerte auf welcher Ebene überschritten werden. Legen Sie anschließend angemessene Maßnahmen zur Erhöhung des Anwendungsdurchsatzes fest.

 In der Regel wird beim Schreiben und Debuggen der Anwendung die <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType>-Eigenschaft in der Konfigurationsdatei oder programmgesteuert auf `true` festgelegt. Dies weist WCF an, Dienst Ausnahme Stapel-Ablauf Verfolgungen zur Anzeige an die Client Anwendung zurückzugeben. Diese Funktion meldet die meisten Ausnahmen auf Anwendungsebene so, dass angezeigt wird, welche Kontingenteinstellungen möglicherweise beteiligt sind, falls das Problem hierdurch verursacht wurde.

 Einige Ausnahmen treten während der Laufzeit außerhalb der Sichtbarkeit der Anwendungsschicht auf und werden nicht mithilfe dieses Mechanismus zurückgegeben. Möglicherweise werden sie auch nicht von einer benutzerdefinierten <xref:System.ServiceModel.Dispatcher.IErrorHandler?displayProperty=nameWithType>-Implementierung gehandhabt. Wenn Sie in einer Entwicklungsumgebung wie Microsoft Visual Studio arbeiten, werden die meisten dieser Ausnahmen automatisch angezeigt. Einige Ausnahmen können jedoch von den Einstellungen der Entwicklungsumgebung wie [nur eigenen Code](/visualstudio/debugger/just-my-code) Visual Studio maskiert werden.

 Unabhängig von den Funktionen der Entwicklungsumgebung können Sie die Funktionen der WCF-Ablauf Verfolgung und der Nachrichten Protokollierung verwenden, um alle Ausnahmen zu Debuggen und die Leistung Ihrer Anwendungen zu optimieren. Weitere Informationen finden Sie unter [Verwenden der Ablauf Verfolgung zum Beheben von Problemen mit Ihrer Anwendung](./diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).

## <a name="performance-issues-and-xmlserializer"></a>Leistungsprobleme und XmlSerializer
 Dienste und Clientanwendungen, die Datentypen verwenden, die mit dem <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können, generieren und kompilieren für diese Datentypen während der Laufzeit Code, was zu einem verlangsamten Start führen kann.

> [!NOTE]
> Vorab generierter Serialisierungscode kann nur in Clientanwendungen und nicht in Diensten verwendet werden.

 Das [Service Model Metadata Utility-Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) kann die Startleistung für diese Anwendungen verbessern, indem der erforderliche Serialisierungscode aus den kompilierten Assemblys für die Anwendung erzeugt wird. Weitere Informationen finden Sie unter Vorgehens [Weise: verbessern der Startzeit von WCF-Client Anwendungen mit dem XmlSerializer](./feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md).

## <a name="performance-issues-when-hosting-wcf-services-under-aspnet"></a>Leistungsprobleme beim Hosten von WCF-Diensten unter ASP.NET

Wird ein WCF-Dienst unter IIS und ASP.NET gehostet, können sich die Konfigurationseinstellungen von IIS und ASP.NET auf den Durchsatz und die Speicherbeanspruchung des WCF-Diensts auswirken.  Weitere Informationen zur ASP.net-Leistung finden Sie unter [verbessern der Leistung von ASP.net](/previous-versions/msp-n-p/ff647787(v=pandp.10)). Eine Einstellung, durch die sich unbeabsichtigte Folgen ergeben können, ist <xref:System.Web.Configuration.ProcessModelSection.MinWorkerThreads%2A>. Hierbei handelt es sich um eine Eigenschaft der <xref:System.Web.Configuration.ProcessModelSection>. Verfügt die Anwendung über eine feste oder über eine geringe Anzahl von Clients, lässt sich durch Festlegen von <xref:System.Web.Configuration.ProcessModelSection.MinWorkerThreads%2A> auf "2" bei einem Computer mit mehreren Prozessoren, dessen CPU-Auslastung sich nahe bei 100 Prozent bewegt, möglicherweise ein Leistungsschub beim Durchsatz erzielen. Dieser Leistungszuwachs bringt jedoch auch einen Nachteil mit sich, da sich dadurch auch eine erhöhte Speicherauslastung ergibt, was zu einer geringeren Skalierbarkeit führt.

## <a name="see-also"></a>Siehe auch

- [Verwaltung und Diagnose](./diagnostics/index.md)
- [Umfangreiche Daten und Streaming](./feature-details/large-data-and-streaming.md)
