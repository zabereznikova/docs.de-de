---
title: Sicherheitsaspekte für Nachrichtenprotokollierung
ms.date: 03/30/2017
ms.assetid: 21f513f2-815b-47f3-85a6-03c008510038
ms.openlocfilehash: bb1a6ab84ceba27b398d397b4407a55aa02c4cae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185772"
---
# <a name="security-concerns-for-message-logging"></a>Sicherheitsaspekte für Nachrichtenprotokollierung
In diesem Thema wird beschrieben, wie Sie vertrauliche Daten davor schützen, in Nachrichtenprotokollen verfügbar gemacht zu werden, wie auch Ereignisse, die von der Nachrichtenprotokollierung generiert werden.  
  
## <a name="security-concerns"></a>Sicherheitsaspekte  
  
### <a name="logging-sensitive-information"></a>Protokollieren vertraulicher Informationen  
 Windows Communication Foundation (WCF) ändert keine Daten in anwendungsspezifischen Headern und Textkörpern. WCF verfolgt auch keine persönlichen Informationen in anwendungsspezifischen Headern oder Textkörperdaten.  
  
 Bei aktivierter Nachrichtenprotokollierung sind persönliche Informationen in anwendungsspezifischen Headern, wie z. B. eine Abfragezeichenfolge, und Textdaten, wie z. B. eine Kreditkartennummer, u. U. in den Protokollen sichtbar. Der Anwendungsbereitsteller ist für das Erzwingen einer Zugriffssteuerung für die Konfigurations- und Protokolldateien verantwortlich. Wenn Informationen dieser Art nicht sichtbar sein sollen, sollten Sie die Protokollierung deaktivieren, oder filtern Sie einen Teil der Daten heraus, wenn Sie die Protokolle freigeben möchten.  
  
 Mithilfe der folgenden Tipps können Sie verhindern, dass der Inhalt einer Protokolldatei unbeabsichtigt verfügbar gemacht wird:  
  
- Stellen Sie sicher, dass die Protokolldateien durch Access Control Lists (ACL oder Zugriffssteuerungslisten) sowohl bei im Internet gehosteten als auch bei selbst gehosteten Szenarien geschützt werden.  
  
- Wählen Sie eine Dateierweiterung aus, die nicht leicht mit einer Webanforderung ausgegeben werden kann. Die Dateierweiterung .xml ist z. B. nicht sicher. Sie finden im Administratorhandbuch von IIS (Internet Information Services) eine Liste aller Erweiterungen, die bereitgestellt werden können.  
  
- Geben Sie einen absoluten Pfad für den Protokolldateispeicherort an, der sich außerhalb des öffentlichen vroot-Verzeichnisses des Webhosts befinden sollte, um einen Zugriff von externer Seite mithilfe eines Webbrowsers zu verhindern.  
  
 Standardmäßig werden Schlüssel und personenbezogene Informationen (PII, personally identifiable information), wie z. B. Benutzername und Passwort, nicht in Ablaufverfolgungen und protokollierten Nachrichten protokolliert. Ein Computeradministrator kann jedoch das `enableLoggingKnownPII`-Attribut im `machineSettings`-Element der Datei Machine.config verwenden, um Anwendungen, die auf dem Computer ausgeführt werden, das Protokollieren personenbezogener Informationen (PII) zu ermöglichen. Die folgende Konfiguration veranschaulicht diesen Vorgang:  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <machineSettings enableLoggingKnownPii="true"/>  
   </system.serviceModel>  
</configuration>
```  
  
 Ein Anwendungsbereitsteller kann daraufhin das `logKnownPii`-Attribut entweder in der Datei App.config oder in der Datei Web.config verwenden, um die PII-Protokollierung wie folgt zu ermöglichen:  
  
```xml  
<system.diagnostics>  
  <sources>  
      <source name="System.ServiceModel.MessageLogging"  
        logKnownPii="true">  
        <listeners>  
                 <add name="messages"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="c:\logs\messages.svclog" />  
          </listeners>  
      </source>  
    </sources>  
</system.diagnostics>  
```  
  
 Nur wenn beide Einstellungen auf `true` festgelegt sind, wird die PII-Protokollierung aktiviert. Die Kombination von zwei Schaltern ermöglicht, bekannte PII für jede Anwendung zu protokollieren.  
  
> [!IMPORTANT]
> In [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] müssen das `logEntireMessage`-Flag und das `logKnownPii`-Flag in der Datei Web.config oder der Datei App.config auch auf `true` festgelegt werden, um die PII-Protokollierung zu ermöglichen, wie im folgenden Beispiel gezeigt: `<system.serviceModel><messageLogging logEntireMessage="true" logKnownPii="true" …`.  
  
 Sie müssen berücksichtigen, dass nur die Attribute der ersten Quelle gelesen werden, wenn Sie zwei oder mehr benutzerdefinierte Quellen in einer Konfigurationsdatei angeben. Die anderen werden ignoriert. Dies bedeutet, dass PII für die folgende Datei App.config nicht für beide Quellen protokolliert wird, obwohl die PII-Protokollierung explizit für die zweite Quelle aktiviert worden ist.  
  
```xml  
<system.diagnostics>  
   <sources>  
      <source name="System.ServiceModel.MessageLogging"  
              logKnownPii="false">  
              <listeners>  
                 <add name="messages"  
                      type="System.Diagnostics.XmlWriterTraceListener"  
                      initializeData="c:\logs\messages.svclog" />  
              </listeners>  
            </source>  
      <source name="System.ServiceModel"
              logKnownPii="true">  
              <listeners>  
                 <add name="traces"  
                      type="System.Diagnostics.XmlWriterTraceListener"  
                      initializeData="c:\logs\traces.svclog" />  
              </listeners>  
      </source>  
   </sources>  
</system.diagnostics>  
```  
  
 Wenn das `<machineSettings enableLoggingKnownPii="Boolean"/>`-Element außerhalb der Datei Machine.config vorhanden ist, löst das System einen <xref:System.Configuration.ConfigurationErrorsException> aus.  
  
 Die Änderungen sind nur wirksam, wenn die Anwendung gestartet oder neu gestartet wird. Ein Ereignis wird beim Start protokolliert, wenn beide Attribute auf `true` festgelegt werden. Ein Ereignis wird außerdem protokolliert, wenn `logKnownPii` auf `true` festgelegt wird, `enableLoggingKnownPii` jedoch `false` ist.  
  
 Der Computeradministrator und der Anwendungsbereitsteller sollten diese beiden Schalter mit großer Vorsicht verwenden. Wenn die PII-Protokollierung aktiviert ist, werden Sicherheitsschlüssel und PII protokolliert. Wenn sie deaktiviert ist, werden vertrauliche und anwendungsspezifische Daten immer noch in Nachrichtenheadern und -texten protokolliert. Eine ausführlichere Diskussion über datenschutz- und den Schutz von personenbezogenen Daten vor der Exposition finden Sie unter [Benutzerdatenschutz](https://docs.microsoft.com/previous-versions/dotnet/articles/aa480490(v=msdn.10)).  
  
> [!CAUTION]
> PII wird nicht in falsch formatierten Nachrichten ausgeblendet. Solche Nachrichten werden ohne Änderung protokolliert. Vorher erwähnte Attribute haben keine Auswirkungen darauf.  
  
### <a name="custom-trace-listener"></a>Benutzerdefinierter Ablaufverfolgungslistener  
 Das Hinzufügen eines benutzerdefinierten Ablaufverfolgungslisteners auf eine Ablaufverfolgungsquelle für Nachrichtenprotokollierung ist ein Recht, das dem Administrator vorbehalten sein sollte. Grund hierfür ist, dass bösartige benutzerdefinierte Listener für das remote Senden von Nachrichten konfiguriert werden können, was zur Offenlegung vertraulicher Informationen führt. Darüber hinaus sollten Sie eine angemessene Zugangskontrolle für die Nachrichtenprotokolle auf einem Remotecomputer erstellen, wenn Sie einen benutzerdefinierten Listener für das Senden von Nachrichten beispielsweise zu einer Remotedatenbank konfigurieren.  
  
## <a name="events-triggered-by-message-logging"></a>Von Nachrichtenprotokollierung ausgelöste Ereignisse  
 Im Folgenden werden alle Ereignisse aufgelistet, die von der Nachrichtenprotokollierung ausgelöst werden.  
  
- Nachrichtenprotokollierung ein: Dieses Ereignis wird ausgegeben, wenn Nachrichtenprotokollierung in der Konfiguration aktiviert wird, oder durch WMI. Der Inhalt des Ereignisses ist "Die Nachrichtenprotokollierung wurde aktiviert". Vertrauliche Informationen werden möglicherweise in Klartext protokolliert, auch wenn sie bei der Übertragung verschlüsselt waren (beispielsweise Nachrichtentext).  
  
- Nachrichtenprotokollierung aus: Dieses Ereignis wird ausgegeben, wenn Nachrichtenprotokollierung durch WMI deaktiviert ist. Der Inhalt des Ereignisses ist "Die Nachrichtenprotokollierung wurde deaktiviert".  
  
- Protokollieren von bekannten PII ein: Dieses Ereignis wird ausgegeben, wenn das Protokollieren von bekanntem PII aktiviert ist. `enableLoggingKnownPii` Dies geschieht, wenn `machineSettings` das Attribut im Element der `true`Datei Machine.config auf festgelegt ist und das `logKnownPii` Attribut des `source` Elements `true`in der Datei App.config oder Web.config auf .  
  
- Protokollieren von bekannten PII nicht zugelassen: Dieses Ereignis wird ausgegeben, wenn das Protokollieren von bekanntem PII nicht zugelassen ist. `logKnownPii` Dies geschieht, wenn `source` das Attribut des Elements in der Datei App.config oder Web.config auf `true`festgelegt ist, das `enableLoggingKnownPii` Attribut im `machineSettings` Element der Datei Machine.config jedoch auf `false`. Es werden keine Ausnahmen ausgelöst.  
  
 Diese Ereignisse können im Windows-integrierten Tool der Ereignisanzeige angezeigt werden. Weitere Informationen hierzu finden Sie unter [Ereignisprotokollierung](./event-logging/index.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Nachrichtenprotokollierung](message-logging.md)
- [Sicherheitsaspekte und nützliche Tipps für die Ablaufverfolgung](./tracing/security-concerns-and-useful-tips-for-tracing.md)
