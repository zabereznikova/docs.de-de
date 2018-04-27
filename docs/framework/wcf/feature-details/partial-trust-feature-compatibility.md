---
title: Funktionskompatibilität für teilweise Vertrauenswürdigkeit
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a36a540b-1606-4e63-88e0-b7c59e0e6ab7
caps.latest.revision: 75
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 20cb6c1cd7a3b06b57bce02d5c3caacc7e2e42b7
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="partial-trust-feature-compatibility"></a>Funktionskompatibilität für teilweise Vertrauenswürdigkeit
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] unterstützt in einer teilweise vertrauenswürdigen Umgebung eine eingeschränkte Teilmenge seiner Funktionalität. Die in einer teilweise vertrauenswürdigen Umgebung unterstützten Funktionen sind, wie im Thema [Supported Deployment Scenarios](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md) beschrieben, für einen speziellen Satz von Szenarios konzipiert.  
  
## <a name="minimum-permission-requirements"></a>Minimal erforderliche Berechtigungen  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt eine Teilmenge von Funktionen in Anwendungen, die unter einem der beiden folgenden benannten Standardberechtigungssätze ausgeführt werden:  
  
-   Berechtigungen für mittlere Vertrauenswürdigkeit  
  
-   Internetzonenberechtigungen  
  
 Der Versuch, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in teilweise vertrauenswürdigen Anwendungen mit strikteren Berechtigungen zu verwenden, kann zur Laufzeit zu Sicherheitsausnahmen führen.  
  
## <a name="contracts"></a>Verträge  
 Beim Ausführen in teilweise vertrauenswürdigen Umgebungen unterliegen Verträge den folgenden Einschränkungen:  
  
-   Die Dienstklasse, durch die die `[ServiceContract]` -Schnittstelle implementiert wird, muss `public` sein und über einen `public` -Konstruktor verfügen. Werden `[OperationContract]` -Methoden definiert, müssen diese `public`sein. Wird stattdessen eine `[ServiceContract]` -Schnittstelle implementiert, können diese Methodenimplementierungen explizit oder `private`sein, vorausgesetzt, die `[ServiceContract]` -Schnittstelle ist `public`.  
  
-   Bei Verwendung des `[ServiceKnownType]` -Attributs muss die angegebene Methode `public`sein.  
  
-   `[MessageContract]` -Klassen und ihre Member können `public`sein. Ist in der Anwendungsassembly die `[MessageContract]` -Klasse definiert, kann diese `internal` sein und Member vom Typ `internal` besitzen.  
  
## <a name="system-provided-bindings"></a>Vom System bereitgestellte Bindungen  
 Sowohl <xref:System.ServiceModel.BasicHttpBinding> als auch <xref:System.ServiceModel.WebHttpBinding> werden in einer teilweise vertrauenswürdigen Umgebung vollständig unterstützt. <xref:System.ServiceModel.WSHttpBinding> wird nur für den Transportsicherheitsmodus unterstützt.  
  
 Bindungen, die andere Transportoptionen als HTTP verwenden, etwa <xref:System.ServiceModel.NetTcpBinding>, <xref:System.ServiceModel.NetNamedPipeBinding>oder <xref:System.ServiceModel.NetMsmqBinding>, werden in einer teilweise vertrauenswürdigen Umgebung nicht unterstützt.  
  
## <a name="custom-bindings"></a>Benutzerdefinierte Bindungen  
 Benutzerdefinierte Bindungen können in einer teilweise vertrauenswürdigen Umgebung erstellt und verwendet werden. Für sie gelten jedoch die in diesem Abschnitt genannten Einschränkungen.  
  
### <a name="transports"></a>Transportprotokolle  
 Die einzigen zulässigen Transportbindungselemente sind <xref:System.ServiceModel.Channels.HttpTransportBindingElement> und <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.  
  
### <a name="encoders"></a>Encoder  
 Folgende Encoder sind zulässig:  
  
-   Der Textencoder (<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>).  
  
-   Der binäre Encoder (<xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>).  
  
-   Der Webnachrichtenencoder (<xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>).  
  
 MTOM (Message Transmission Optimization Mechanism)-Encoder werden nicht unterstützt.  
  
### <a name="security"></a>Sicherheit  
 Teilweise vertrauenswürdige Anwendungen können zum Schutz ihrer Kommunikation die Funktionen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]für die Sicherheit auf Transportebene verwenden. Sicherheit auf Nachrichtenebene wird nicht unterstützt. Wird eine Bindung für die Verwendung von Sicherheit auf Nachrichtenebene konfiguriert, löst dies zur Laufzeit eine Ausnahme aus.  
  
### <a name="unsupported-bindings"></a>Nicht unterstützte Bindungen  
 Bindungen, die zuverlässiges Messaging, Transaktionen oder Sicherheit auf Nachrichtenebene verwenden, werden nicht unterstützt.  
  
## <a name="serialization"></a>Serialisierung  
 Sowohl <xref:System.Runtime.Serialization.DataContractSerializer> als auch <xref:System.Xml.Serialization.XmlSerializer> werden in einer teilweise vertrauenswürdigen Umgebung unterstützt. Allerdings unterliegt die Verwendung von <xref:System.Runtime.Serialization.DataContractSerializer> den folgenden Bedingungen:  
  
-   Alle serialisierbaren `[DataContract]` -Typen müssen als `public`deklariert sein.  
  
-   Alle serialisierbaren `[DataMember]` -Felder oder -Eigenschaften in einem `[DataContract]` -Typ müssen öffentlich sein und Schreib-/Lesezugriff besitzen. Die Serialisierung und die Deserialisierung von [readonly](http://go.microsoft.com/fwlink/?LinkID=98854) -Feldern wird nicht unterstützt, wenn [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in einer teilweise vertrauenswürdigen Anwendung ausgeführt wird.  
  
-   Das `[Serializable]`/ISerializable- Programmiermodell wird in einer teilweise vertrauenswürdigen Umgebung nicht unterstützt.  
  
-   Bekannte Typen müssen im Code oder in einer Konfiguration auf Computerebene (machine.config) angegeben werden. Bekannte Typen können aus Sicherheitsgründen nicht in einer Konfiguration auf Anwendungsebene angegeben werden.  
  
-   Typen, die <xref:System.Runtime.Serialization.IObjectReference> implementieren, lösen in einer teilweise-vertrauenswürdigen Umgebung eine Ausnahme aus.  
  
 Im Abschnitt zur Serialisierung finden Sie unter [Partial Trust Best Practices](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md) weitere Informationen zur Sicherheit bei der Verwendung von <xref:System.Runtime.Serialization.DataContractSerializer> in einer teilweise vertrauenswürdigen Umgebung.  
  
### <a name="collection-types"></a>Auflistungstypen  
 Einige Auflistungstypen implementieren sowohl <xref:System.Collections.Generic.IEnumerable%601> als auch <xref:System.Collections.IEnumerable>. Beispiele dafür sind Typen, die <xref:System.Collections.Generic.ICollection%601>implementieren. Solche Typen können eine `public` -Implementierung von `GetEnumerator()`und eine explizite Implementierung von `GetEnumerator()`enthalten. In diesem Fall ruft <xref:System.Runtime.Serialization.DataContractSerializer> die `public` -Implementierung von `GetEnumerator()`auf, und nicht die explizite Implementierung von `GetEnumerator()`. Wenn keine der `GetEnumerator()` -Implementierungen `public` ist, sondern es sich bei allen um explizite Implementierungen handelt, ruft <xref:System.Runtime.Serialization.DataContractSerializer> `IEnumerable.GetEnumerator()`auf.  
  
 Wird [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in einer teilweise vertrauenswürdigen Umgebung ausgeführt, und ist keine der `GetEnumerator()` -Implementierungen `public`oder ist keine von ihnen eine explizite Schnittstellenimplementierung, wird eine Sicherheitsausnahme ausgelöst.  
  
### <a name="netdatacontractserializer"></a>NetDataContractSerializer  
 Viele .NET Framework-Auflistungstypen (wie <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ArrayList>, <xref:System.Collections.Generic.Dictionary%602> und <xref:System.Collections.Hashtable> ) werden vom <xref:System.Runtime.Serialization.NetDataContractSerializer> in teilweise vertrauenswürdigen Umgebungen nicht unterstützt. Für diese Typen ist das `[Serializable]` -Attribut festgelegt. Wie bereits im Abschnitt zur Serialisierung erwähnt, wird dieses Attribut in teilweise vertrauenswürdigen Umgebungen nicht unterstützt. Der <xref:System.Runtime.Serialization.DataContractSerializer> behandelt Auflistungen auf besondere Weise, weshalb diese Einschränkung von ihm umgangen werden kann, <xref:System.Runtime.Serialization.NetDataContractSerializer> verfügt jedoch über keine Möglichkeit zum Umgehen dieser Einschränkung.  
  
 Der <xref:System.DateTimeOffset> -Typ wird vom <xref:System.Runtime.Serialization.NetDataContractSerializer> in teilweiser vertrauenswürdigen Umgebungen nicht unterstützt.  
  
 Beim Ausführen in teilweise vertrauenswürdigen Umgebungen kann mit dem <xref:System.Runtime.Serialization.NetDataContractSerializer> (unter Verwendung des <xref:System.Runtime.Serialization.SurrogateSelector> -Mechanismus) kein Ersatzzeichen verwendet werden. Beachten Sie, dass diese Einschränkung für die Verwendung (und nicht für die Serialisierung) eines Ersatzzeichens gilt.  
  
## <a name="enabling-common-behaviors-to-run"></a>Aktivieren von gemeinsamem Verhalten für die Ausführung  
 Dienst- oder Endpunktverhaltensweisen nicht gekennzeichnet werden, mit der <xref:System.Security.AllowPartiallyTrustedCallersAttribute> -Attribut (APTCA), die hinzugefügt werden, die [ \<CommonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) Abschnitt einer Konfigurationsdatei werden nicht ausgeführt, wenn in einer teilweise vertrauenswürdigen Anwendung ausgeführt wird Umgebung und keine Ausnahme wird ausgelöst, wenn in diesem Fall. Um die Ausführung gemeinsamer Verhalten zu erzwingen, müssen Sie einen der beiden folgenden Schritte ausführen:  
  
-   Markieren Sie das gemeinsame Verhalten mit dem <xref:System.Security.AllowPartiallyTrustedCallersAttribute> -Attribut, damit es ausgeführt werden kann, wenn es als teilweise vertrauenswürdige Anwendung bereitgestellt wird. Beachten Sie, dass auf dem Computer ein Registrierungseintrag festgelegt werden kann, um die Ausführung von mit APTCA markierten Assemblys zu verhindern. sein.  
  
-   Wenn die Anwendung als voll vertrauenswürdige Anwendung bereitgestellt wird, stellen Sie sicher, dass die Benutzer die Sicherheitseinstellungen für den Codezugriff nicht dahingehend ändern können, dass die Anwendung in einer teilweise vertrauenswürdigen Umgebung ausgeführt werden kann. Wenn sie dies können, dann wird das Verhalten nicht ausgeführt, und es wird keine Ausnahme ausgelöst. Um dies sicherzustellen, finden Sie unter der **Levelfinal** -Option [Caspol.exe (Code Access Security Policy-Tool)](../../../../docs/framework/tools/caspol-exe-code-access-security-policy-tool.md).  
  
 Ein Beispiel für ein gemeinsames Verhalten, finden Sie unter [Vorgehensweise: Sperren Sie die Endpunkte im Unternehmen](../../../../docs/framework/wcf/extending/how-to-lock-down-endpoints-in-the-enterprise.md).  
  
## <a name="configuration"></a>Konfiguration  
 Bis auf eine Ausnahme kann teilweise vertrauenswürdiger Code nur [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Konfigurationsabschnitte in der lokalen `app.config` -Datei laden. Um [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Konfigurationsabschnitte laden zu können, die auf [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Abschnitte in der Datei machine.config oder in einer Stammdatei web.config verweisen, ist die Berechtigung ConfigurationPermission(Unrestricted) erforderlich. Ohne diese Berechtigung führen Verweise auf [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Konfigurationsabschnitte (Verhalten, Bindungen) außerhalb der lokalen Konfigurationsdatei zu einer Ausnahme, wenn die Konfiguration geladen wird.  
  
 Die Ausnahme ist die Konfiguration für die Serialisierung mit bekannten Typen, wie im Serialisierungsabschnitt dieses Themas beschrieben.  
  
> [!IMPORTANT]
>  Konfigurationserweiterungen werden nur bei der Ausführung im Modus "Voll vertrauenswürdig" unterstützt.  
  
## <a name="diagnostics"></a>Diagnose  
  
### <a name="event-logging"></a>Ereignisprotokollierung  
 In teilweise vertrauenswürdigen Umgebungen wird eine eingeschränkte Ereignisprotokollierung unterstützt. Nur Dienstaktivierungsfehler und Fehler bei der Ablaufverfolgung/Nachrichtenprotokollierung werden im Ereignisprotokoll protokolliert. Pro Prozess können maximal fünf Ereignisse protokolliert werden. Dadurch soll vermieden werden, dass zu viele Meldungen in das Ereignisprotokoll geschrieben werden.  
  
### <a name="message-logging"></a>Nachrichtenprotokollierung  
 Die Nachrichtenprotokollierung funktioniert nicht, wenn [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in einer teilweise vertrauenswürdigen Umgebung ausgeführt wird. Wird sie in einer teilweise vertrauenswürdigen Umgebung aktiviert, schlägt zwar die Dienstaktivierung nicht fehl, jedoch wird keine Nachricht protokolliert.  
  
### <a name="tracing"></a>Ablaufverfolgung  
 In einer teilweise vertrauenswürdigen Umgebung ist nur eine eingeschränkte Funktionalität der Ablaufverfolgung verfügbar. Dem <`listeners`>-Element der Konfigurationsdatei können Sie nur den <xref:System.Diagnostics.TextWriterTraceListener>-Typ und den neuen <xref:System.Diagnostics.EventSchemaTraceListener>-Typ hinzufügen. Die Verwendung des Standardtyps <xref:System.Diagnostics.XmlWriterTraceListener> führt möglicherweise zu unvollständigen oder falschen Protokollen.  
  
 Unterstützte Ablaufverfolgungsquellen sind:  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.Runtime.Serialization>  
  
-   <xref:System.IdentityModel.Claims>, <xref:System.IdentityModel.Policy>, <xref:System.IdentityModel.Selectors>und <xref:System.IdentityModel.Tokens>.  
  
 Folgende Ablaufverfolgungsquellen werden nicht unterstützt:  
  
-   CardSpace  
  
-   <xref:System.IO.Log>  

-   [System.ServiceModel.Internal.TransactionBridge](https://msdn.microsoft.com/library/system.servicemodel.internal.transactionbridge.aspx)]
  
 Die folgenden Member der <xref:System.Diagnostics.TraceOptions> -Enumeration sollten nicht angegeben werden.  
  
-   <xref:System.Diagnostics.TraceOptions.Callstack?displayProperty=nameWithType>  
  
-   <xref:System.Diagnostics.TraceOptions.ProcessId?displayProperty=nameWithType>  
  
 Wenn Sie die Ablaufverfolgung in einer teilweise vertrauenswürdigen Umgebung verwenden, dann stellen Sie sicher, dass die Anwendung über ausreichende Berechtigungen verfügt, um die Ausgabe des Ablaufverfolgungslisteners speichern zu können. Wenn Sie z.&amp;#160;B. den <xref:System.Diagnostics.TextWriterTraceListener> verwenden, um die Ablaufverfolgungsausgabe in eine Textdatei zu schreiben, müssen Sie sicherstellen, dass die Anwendung über die notwendigen FileIOPermission-Berechtigungen verfügt, die für das Schreiben in die Ablaufverfolgungsdatei erforderlich sind.  
  
> [!NOTE]
>  Damit die Ablaufverfolgungsdatei nicht mit doppelten Fehlermeldungen überflutet wird, deaktiviert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die Ablaufverfolgung der Ressource oder der Aktion nach dem ersten Sicherheitsfehler. Es gibt eine Ausnahmeablaufverfolgung für jeden fehlgeschlagenen Ressourcenzugriff, und zwar für den ersten Versuch, auf eine Ressource zuzugreifen oder eine Aktion auszuführen.  
  
## <a name="wcf-service-host"></a>WCF-Diensthost  
 Der[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Diensthost unterstützt keine teilweise vertrauenswürdigen Umgebungen. Wenn Sie verwenden möchten eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service unter teilweiser Vertrauenswürdigkeit, verwenden Sie nicht die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -dienstbibliotheksprojektvorlage in Visual Studio zur Erstellung des Diensts. Erstellen Sie stattdessen eine neue Website in Visual Studio durch Auswählen der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Website Dienstvorlage, die den Dienst auf einem Webserver, auf dem hosten kann [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] teilweise Vertrauenswürdigkeit unterstützt.  
  
## <a name="other-limitations"></a>Weitere Einschränkungen  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] wird allgemein von den Sicherheitsüberlegungen eingeschränkt, die von der Hostanwendung auferlegt werden. Wird [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] z.B. in einer XAML-Browseranwendung (XBAP) gehostet, gelten die XBAP-Einschränkungen, die unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](http://go.microsoft.com/fwlink/?LinkId=89138)beschrieben sind.  
  
 Die folgenden Zusatzfunktionen stehen nicht zur Verfügung, wenn indigo2 in einer teilweise vertrauenswürdigen Umgebung ausgeführt wird:  
  
-   Windows Management Instrumentation (WMI)  
  
-   Die Ereignisprotokollierung ist nur teilweise aktiviert (siehe Diskussion im Abschnitt **Diagnose** ).  
  
-   Leistungsindikatoren  
  
 Die Verwendung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Funktionen in einer teilweise vertrauenswürdigen Umgebung kann dazu führen, dass zur Laufzeit Ausnahmen ausgelöst werden.  
  
## <a name="unlisted-features"></a>Nicht aufgeführte Funktionen  
 Die beste Möglichkeit festzustellen, ob in einer teilweise vertrauenswürdigen Umgebung auf eine bestimmte Ressource zugegriffen oder eine Aktion ausgeführt werden kann, besteht darin, innerhalb eines `try` -Blocks auf die Ressource zuzugreifen oder die Aktion auszuführen, und dann einen möglichen Fehlschlag mit `catch` abzufangen. Damit die Ablaufverfolgungsdatei nicht mit doppelten Fehlermeldungen überflutet wird, deaktiviert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die Ablaufverfolgung der Ressource oder der Aktion nach dem ersten Sicherheitsfehler. Es gibt eine Ausnahmeablaufverfolgung für jeden fehlgeschlagenen Ressourcenzugriff, und zwar für den ersten Versuch, auf eine Ressource zuzugreifen oder eine Aktion auszuführen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>  
 [Unterstützte Bereitstellungsszenarien](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md)  
 [Bewährte Methoden für teilweise Vertrauenswürdigkeit](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md)
