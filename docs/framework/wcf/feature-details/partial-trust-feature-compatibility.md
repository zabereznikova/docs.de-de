---
title: Funktionskompatibilität für teilweise Vertrauenswürdigkeit
ms.date: 03/30/2017
ms.assetid: a36a540b-1606-4e63-88e0-b7c59e0e6ab7
ms.openlocfilehash: 3e0f1c2f673d4ba603df7da431d10c211cf779ac
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212125"
---
# <a name="partial-trust-feature-compatibility"></a>Funktionskompatibilität für teilweise Vertrauenswürdigkeit
Windows Communication Foundation (WCF) unterstützt eine begrenzte Teilmenge von Funktionen, wenn Sie in einer teilweise vertrauenswürdigen Umgebung ausgeführt werden. Die in einer teilweise vertrauenswürdigen Umgebung unterstützten Funktionen sind, wie im Thema [Supported Deployment Scenarios](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md) beschrieben, für einen speziellen Satz von Szenarios konzipiert.  
  
## <a name="minimum-permission-requirements"></a>Minimal erforderliche Berechtigungen  
 WCF unterstützt eine Teilmenge von Funktionen in Anwendungen, die unter einem der folgenden benannten Standard Berechtigungs Sätze ausgeführt werden:  
  
- Berechtigungen für mittlere Vertrauenswürdigkeit  
  
- Internetzonenberechtigungen  
  
 Der Versuch, WCF in teilweise vertrauenswürdigen Anwendungen mit restriktiveren Berechtigungen zu verwenden, kann zur Laufzeit zu Sicherheits Ausnahmen führen.  
  
## <a name="contracts"></a>Verträge  
 Beim Ausführen in teilweise vertrauenswürdigen Umgebungen unterliegen Verträge den folgenden Einschränkungen:  
  
- Die Dienstklasse, durch die die `[ServiceContract]` -Schnittstelle implementiert wird, muss `public` sein und über einen `public` -Konstruktor verfügen. Werden `[OperationContract]` -Methoden definiert, müssen diese `public`sein. Wird stattdessen eine `[ServiceContract]` -Schnittstelle implementiert, können diese Methodenimplementierungen explizit oder `private`sein, vorausgesetzt, die `[ServiceContract]` -Schnittstelle ist `public`.  
  
- Bei Verwendung des `[ServiceKnownType]` -Attributs muss die angegebene Methode `public`sein.  
  
- `[MessageContract]` -Klassen und ihre Member können `public`sein. Ist in der Anwendungsassembly die `[MessageContract]` -Klasse definiert, kann diese `internal` sein und Member vom Typ `internal` besitzen.  
  
## <a name="system-provided-bindings"></a>Vom System bereitgestellte Bindungen  
 Sowohl <xref:System.ServiceModel.BasicHttpBinding> als auch <xref:System.ServiceModel.WebHttpBinding> werden in einer teilweise vertrauenswürdigen Umgebung vollständig unterstützt. <xref:System.ServiceModel.WSHttpBinding> wird nur für den Transportsicherheitsmodus unterstützt.  
  
 Bindungen, die andere Transportoptionen als HTTP verwenden, etwa <xref:System.ServiceModel.NetTcpBinding>, <xref:System.ServiceModel.NetNamedPipeBinding>oder <xref:System.ServiceModel.NetMsmqBinding>, werden in einer teilweise vertrauenswürdigen Umgebung nicht unterstützt.  
  
## <a name="custom-bindings"></a>Benutzerdefinierte Bindungen  
 Benutzerdefinierte Bindungen können in einer teilweise vertrauenswürdigen Umgebung erstellt und verwendet werden. Für sie gelten jedoch die in diesem Abschnitt genannten Einschränkungen.  
  
### <a name="transports"></a>Transporte  
 Die einzigen zulässigen Transportbindungselemente sind <xref:System.ServiceModel.Channels.HttpTransportBindingElement> und <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.  
  
### <a name="encoders"></a>Encoder  
 Folgende Encoder sind zulässig:  
  
- Der Textencoder (<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>).  
  
- Der binäre Encoder (<xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>).  
  
- Der Webnachrichtenencoder (<xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>).  
  
 MTOM (Message Transmission Optimization Mechanism)-Encoder werden nicht unterstützt.  
  
### <a name="security"></a>Sicherheit  
 Teilweise vertrauenswürdige Anwendungen können zum Schutz Ihrer Kommunikation WCF-Sicherheitsfeatures auf Transport Ebene verwenden. Sicherheit auf Nachrichtenebene wird nicht unterstützt. Wird eine Bindung für die Verwendung von Sicherheit auf Nachrichtenebene konfiguriert, löst dies zur Laufzeit eine Ausnahme aus.  
  
### <a name="unsupported-bindings"></a>Nicht unterstützte Bindungen  
 Bindungen, die zuverlässiges Messaging, Transaktionen oder Sicherheit auf Nachrichtenebene verwenden, werden nicht unterstützt.  
  
## <a name="serialization"></a>Serialization  
 Sowohl <xref:System.Runtime.Serialization.DataContractSerializer> als auch <xref:System.Xml.Serialization.XmlSerializer> werden in einer teilweise vertrauenswürdigen Umgebung unterstützt. Allerdings unterliegt die Verwendung von <xref:System.Runtime.Serialization.DataContractSerializer> den folgenden Bedingungen:  
  
- Alle serialisierbaren `[DataContract]` -Typen müssen als `public`deklariert sein.  
  
- Alle serialisierbaren `[DataMember]` -Felder oder -Eigenschaften in einem `[DataContract]` -Typ müssen öffentlich sein und Schreib-/Lesezugriff besitzen. Die Serialisierung und Deserialisierung von [Schreib](https://go.microsoft.com/fwlink/?LinkID=98854) geschützten Feldern wird nicht unterstützt, wenn WCF in einer teilweise vertrauenswürdigen Anwendung ausgeführt wird.  
  
- Das `[Serializable]`/ISerializable- Programmiermodell wird in einer teilweise vertrauenswürdigen Umgebung nicht unterstützt.  
  
- Bekannte Typen müssen im Code oder in einer Konfiguration auf Computerebene (machine.config) angegeben werden. Bekannte Typen können aus Sicherheitsgründen nicht in einer Konfiguration auf Anwendungsebene angegeben werden.  
  
- Typen, die <xref:System.Runtime.Serialization.IObjectReference> implementieren, lösen in einer teilweise-vertrauenswürdigen Umgebung eine Ausnahme aus.  
  
 Im Abschnitt zur Serialisierung finden Sie unter [Partial Trust Best Practices](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md) weitere Informationen zur Sicherheit bei der Verwendung von <xref:System.Runtime.Serialization.DataContractSerializer> in einer teilweise vertrauenswürdigen Umgebung.  
  
### <a name="collection-types"></a>Auflistungstypen  
 Einige Auflistungstypen implementieren sowohl <xref:System.Collections.Generic.IEnumerable%601> als auch <xref:System.Collections.IEnumerable>. Beispiele dafür sind Typen, die <xref:System.Collections.Generic.ICollection%601>implementieren. Solche Typen können eine `public` -Implementierung von `GetEnumerator()`und eine explizite Implementierung von `GetEnumerator()`enthalten. In diesem Fall ruft <xref:System.Runtime.Serialization.DataContractSerializer> die `public` -Implementierung von `GetEnumerator()`auf, und nicht die explizite Implementierung von `GetEnumerator()`. Wenn keine der `GetEnumerator()` -Implementierungen `public` ist, sondern es sich bei allen um explizite Implementierungen handelt, ruft <xref:System.Runtime.Serialization.DataContractSerializer>`IEnumerable.GetEnumerator()`auf.  
  
 Bei Sammlungs Typen, bei denen WCF in einer teilweise vertrauenswürdigen Umgebung ausgeführt wird, wird eine Sicherheits Ausnahme ausgelöst, wenn keine der `GetEnumerator()` Implementierungen `public`ist oder keine der beiden Implementierungen explizite Schnittstellen Implementierungen ist.  
  
### <a name="netdatacontractserializer"></a>NetDataContractSerializer  
 Viele .NET Framework-Auflistungstypen (wie <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ArrayList>, <xref:System.Collections.Generic.Dictionary%602> und <xref:System.Collections.Hashtable> ) werden vom <xref:System.Runtime.Serialization.NetDataContractSerializer> in teilweise vertrauenswürdigen Umgebungen nicht unterstützt. Für diese Typen ist das `[Serializable]` -Attribut festgelegt. Wie bereits im Abschnitt zur Serialisierung erwähnt, wird dieses Attribut in teilweise vertrauenswürdigen Umgebungen nicht unterstützt. Der <xref:System.Runtime.Serialization.DataContractSerializer> behandelt Auflistungen auf besondere Weise, weshalb diese Einschränkung von ihm umgangen werden kann, <xref:System.Runtime.Serialization.NetDataContractSerializer> verfügt jedoch über keine Möglichkeit zum Umgehen dieser Einschränkung.  
  
 Der <xref:System.DateTimeOffset> -Typ wird vom <xref:System.Runtime.Serialization.NetDataContractSerializer> in teilweiser vertrauenswürdigen Umgebungen nicht unterstützt.  
  
 Beim Ausführen in teilweise vertrauenswürdigen Umgebungen kann mit dem <xref:System.Runtime.Serialization.NetDataContractSerializer> (unter Verwendung des <xref:System.Runtime.Serialization.SurrogateSelector> -Mechanismus) kein Ersatzzeichen verwendet werden. Beachten Sie, dass diese Einschränkung für die Verwendung (und nicht für die Serialisierung) eines Ersatzzeichens gilt.  
  
## <a name="enabling-common-behaviors-to-run"></a>Aktivieren von gemeinsamem Verhalten für die Ausführung  
 Dienst-oder Endpunkt Verhaltensweisen, die nicht mit dem <xref:System.Security.AllowPartiallyTrustedCallersAttribute>-Attribut (APTCA) markiert sind, die dem [\<commonverhaltens>](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) -Abschnitt einer Konfigurationsdatei hinzugefügt werden, werden nicht ausgeführt, wenn die Anwendung in einer teilweise vertrauenswürdigen Umgebung ausgeführt wird. wenn dies auftritt, wird keine Ausnahme ausgelöst. Um die Ausführung gemeinsamer Verhalten zu erzwingen, müssen Sie einen der beiden folgenden Schritte ausführen:  
  
- Markieren Sie das gemeinsame Verhalten mit dem <xref:System.Security.AllowPartiallyTrustedCallersAttribute> -Attribut, damit es ausgeführt werden kann, wenn es als teilweise vertrauenswürdige Anwendung bereitgestellt wird. Beachten Sie, dass auf dem Computer ein Registrierungseintrag festgelegt werden kann, um die Ausführung von mit APTCA markierten Assemblys zu verhindern. .  
  
- Wenn die Anwendung als voll vertrauenswürdige Anwendung bereitgestellt wird, stellen Sie sicher, dass die Benutzer die Sicherheitseinstellungen für den Codezugriff nicht dahingehend ändern können, dass die Anwendung in einer teilweise vertrauenswürdigen Umgebung ausgeführt werden kann. Wenn sie dies können, dann wird das Verhalten nicht ausgeführt, und es wird keine Ausnahme ausgelöst. Um dies sicherzustellen, sehen Sie sich die Option **LevelFinal** mit [Caspol. exe (Code Zugriffs-Sicherheitsrichtlinien Tool)](../../../../docs/framework/tools/caspol-exe-code-access-security-policy-tool.md)an.  
  
 Ein Beispiel für ein häufiges Verhalten finden Sie unter Gewusst [wie: Sperren von Endpunkten im Unternehmen](../../../../docs/framework/wcf/extending/how-to-lock-down-endpoints-in-the-enterprise.md).  
  
## <a name="configuration"></a>-Konfiguration  
 Mit einer Ausnahme kann teilweise vertrauenswürdiger Code nur WCF-Konfigurations Abschnitte in der lokalen `app.config` Datei laden. Zum Laden von WCF-Konfigurations Abschnitten, die auf WCF-Abschnitte in Machine. config oder in einer Web. config-Stammdatei verweisen, ist configurationberechtigung (uneingeschränkt) erforderlich. Ohne diese Berechtigung führen Verweise auf WCF-Konfigurations Abschnitte (Verhalten, Bindungen) außerhalb der lokalen Konfigurationsdatei zu einer Ausnahme, wenn die Konfiguration geladen wird.  
  
 Die Ausnahme ist die Konfiguration für die Serialisierung mit bekannten Typen, wie im Serialisierungsabschnitt dieses Themas beschrieben.  
  
> [!IMPORTANT]
> Konfigurationserweiterungen werden nur bei der Ausführung im Modus "Voll vertrauenswürdig" unterstützt.  
  
## <a name="diagnostics"></a>Diagnose  
  
### <a name="event-logging"></a>Ereignisprotokollierung  
 In teilweise vertrauenswürdigen Umgebungen wird eine eingeschränkte Ereignisprotokollierung unterstützt. Nur Dienstaktivierungsfehler und Fehler bei der Ablaufverfolgung/Nachrichtenprotokollierung werden im Ereignisprotokoll protokolliert. Pro Prozess können maximal fünf Ereignisse protokolliert werden. Dadurch soll vermieden werden, dass zu viele Meldungen in das Ereignisprotokoll geschrieben werden.  
  
### <a name="message-logging"></a>Nachrichtenprotokollierung  
 Die Nachrichten Protokollierung funktioniert nicht, wenn WCF in einer teilweise vertrauenswürdigen Umgebung ausgeführt wird. Wird sie in einer teilweise vertrauenswürdigen Umgebung aktiviert, schlägt zwar die Dienstaktivierung nicht fehl, jedoch wird keine Nachricht protokolliert.  
  
### <a name="tracing"></a>Ablaufverfolgung  
 In einer teilweise vertrauenswürdigen Umgebung ist nur eine eingeschränkte Funktionalität der Ablaufverfolgung verfügbar. Im <`listeners`>-Element in der Konfigurationsdatei sind die einzigen Typen, die Sie hinzufügen können, <xref:System.Diagnostics.TextWriterTraceListener> und die neue <xref:System.Diagnostics.EventSchemaTraceListener>. Die Verwendung des Standardtyps <xref:System.Diagnostics.XmlWriterTraceListener> führt möglicherweise zu unvollständigen oder falschen Protokollen.  
  
 Unterstützte Ablaufverfolgungsquellen sind:  
  
- <xref:System.ServiceModel>  
  
- <xref:System.Runtime.Serialization>  
  
- <xref:System.IdentityModel.Claims>, <xref:System.IdentityModel.Policy>, <xref:System.IdentityModel.Selectors> und <xref:System.IdentityModel.Tokens>.  
  
 Folgende Ablaufverfolgungsquellen werden nicht unterstützt:  
  
- CardSpace  
  
- <xref:System.IO.Log>  

- [System.ServiceModel.Internal.TransactionBridge](https://docs.microsoft.com/previous-versions/aa346556(v=vs.110))]
  
 Die folgenden Member der <xref:System.Diagnostics.TraceOptions> -Enumeration sollten nicht angegeben werden.  
  
- <xref:System.Diagnostics.TraceOptions.Callstack?displayProperty=nameWithType>  
  
- <xref:System.Diagnostics.TraceOptions.ProcessId?displayProperty=nameWithType>  
  
 Wenn Sie die Ablaufverfolgung in einer teilweise vertrauenswürdigen Umgebung verwenden, dann stellen Sie sicher, dass die Anwendung über ausreichende Berechtigungen verfügt, um die Ausgabe des Ablaufverfolgungslisteners speichern zu können. Wenn Sie z.&#160;B. den <xref:System.Diagnostics.TextWriterTraceListener> verwenden, um die Ablaufverfolgungsausgabe in eine Textdatei zu schreiben, müssen Sie sicherstellen, dass die Anwendung über die notwendigen FileIOPermission-Berechtigungen verfügt, die für das Schreiben in die Ablaufverfolgungsdatei erforderlich sind.  
  
> [!NOTE]
> Um die Überflutung der Ablauf Verfolgungs Dateien mit doppelten Fehlern zu vermeiden, deaktiviert WCF die Ablauf Verfolgung der Ressource oder Aktion nach dem ersten Sicherheitsfehler. Es gibt eine Ausnahmeablaufverfolgung für jeden fehlgeschlagenen Ressourcenzugriff, und zwar für den ersten Versuch, auf eine Ressource zuzugreifen oder eine Aktion auszuführen.  
  
## <a name="wcf-service-host"></a>WCF-Diensthost  
 Der WCF-Dienst Host unterstützt keine teilweise Vertrauenswürdigkeit. Wenn Sie einen WCF-Dienst mit teilweiser Vertrauenswürdigkeit verwenden möchten, verwenden Sie nicht die WCF-Dienst Bibliothek-Projektvorlage in Visual Studio, um den Dienst zu erstellen. Erstellen Sie stattdessen eine neue Website in Visual Studio, indem Sie die Vorlage WCF-Dienst Website auswählen, die den Dienst auf einem Webserver hosten kann, auf dem eine teilweise vertrauenswürdige WCF-Verbindung unterstützt wird.  
  
## <a name="other-limitations"></a>Weitere Einschränkungen  

  WCF ist im Allgemeinen auf die Sicherheitsüberlegungen beschränkt, die von der Host Anwendung auferlegt werden. Wenn WCF z. b. in einer XAML-Browser Anwendung (XBAP) gehostet wird, unterliegt sie XBAP-Einschränkungen, wie in [Windows Presentation Foundation teilweise Vertrauens](../../wpf/wpf-partial-trust-security.md)Würdigkeit der Sicherheit beschrieben.  
  
 Die folgenden Zusatzfunktionen stehen nicht zur Verfügung, wenn indigo2 in einer teilweise vertrauenswürdigen Umgebung ausgeführt wird:  
  
- Windows-Verwaltungsinstrumentation (WMI)  
  
- Die Ereignisprotokollierung ist nur teilweise aktiviert (siehe Diskussion im Abschnitt **Diagnose** ).  
  
- Leistungsindikatoren  
  
 Die Verwendung von WCF-Funktionen, die in einer teilweise vertrauenswürdigen Umgebung nicht unterstützt werden, kann zur Laufzeit zu Ausnahmen führen.  
  
## <a name="unlisted-features"></a>Nicht aufgeführte Funktionen  
 Die beste Möglichkeit festzustellen, ob in einer teilweise vertrauenswürdigen Umgebung auf eine bestimmte Ressource zugegriffen oder eine Aktion ausgeführt werden kann, besteht darin, innerhalb eines `try` -Blocks auf die Ressource zuzugreifen oder die Aktion auszuführen, und dann einen möglichen Fehlschlag mit `catch` abzufangen. Um die Überflutung der Ablauf Verfolgungs Dateien mit doppelten Fehlern zu vermeiden, deaktiviert WCF die Ablauf Verfolgung der Ressource oder Aktion nach dem ersten Sicherheitsfehler. Es gibt eine Ausnahmeablaufverfolgung für jeden fehlgeschlagenen Ressourcenzugriff, und zwar für den ersten Versuch, auf eine Ressource zuzugreifen oder eine Aktion auszuführen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>
- [Unterstützte Bereitstellungsszenarien](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md)
- [Partial Trust Best Practices](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md)
