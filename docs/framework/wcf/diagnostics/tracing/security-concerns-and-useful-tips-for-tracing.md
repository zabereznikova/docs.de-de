---
title: "Sicherheitsaspekte und nützliche Tipps für die Ablaufverfolgung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88bc2880-ecb9-47cd-9816-39016a07076f
caps.latest.revision: "11"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 4c6916333d1efa99ba1c4a9d75d80be2193e8698
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="security-concerns-and-useful-tips-for-tracing"></a>Sicherheitsaspekte und nützliche Tipps für die Ablaufverfolgung
Dieses Thema beschreibt, wie Sie vertrauliche Informationen davor schützen, verfügbar gemacht zu werden, sowie nützliche Tipps zur Verwendung von WebHost.  
  
## <a name="using-a-custom-trace-listener-with-webhost"></a>Verwenden eines benutzerdefinierten Ablaufverfolgungslisteners mit WebHost  
 Wenn Sie einen eigenen Ablaufverfolgungslistener schreiben, sollten Sie beachten, dass Ablaufverfolgungen bei einem im Internet gehosteten Dienst verloren gehen können. Wenn WebHost zur Wiederverwendung genutzt wird, wird der Liveprozess heruntergefahren, während ein Duplikat übernimmt. Die beiden Prozesse müssen jedoch trotzdem, abhängig vom Listenertyp, eine Zeit lang Zugriff auf dieselbe Ressource haben. In diesem Fall erstellt `XmlWriterTraceListener` eine neue Ablaufverfolgungsdatei für den zweiten Prozess, während die Windows-Ereignisablaufverfolgung mehrere Prozesse innerhalb derselben Sitzung verwaltet und Zugriff auf dieselbe Datei gewährt. Wenn Ihr Listener keine ähnlichen Funktionalitäten bereitstellt, können Ablaufverfolgungen verloren gehen, wenn die Datei durch die beiden Prozesse gesperrt wird.  
  
 Sie müssen außerdem berücksichtigen, dass ein benutzerdefinierter Ablaufverfolgungslistener Ablaufverfolgungen und Nachrichten z. B. an eine Remotedatenbank senden kann. Als Anwendungsbereitsteller sollten Sie benutzerdefinierte Listener mit entsprechender Zugriffssteuerung konfigurieren. Sie sollten außerdem eine Sicherheitskontrolle auf alle persönlichen Informationen, die am Remotespeicherort verfügbar gemacht werden können, anwenden.  
  
## <a name="logging-sensitive-information"></a>Protokollieren vertraulicher Informationen  
 Ablaufverfolgungen enthalten Nachrichtenheader, wenn sich eine Nachricht im Gültigkeitsbereich befindet. Bei aktivierter Ablaufverfolgung sind persönliche Informationen in anwendungsspezifischen Headern, wie z. B. eine Abfragezeichenfolge, und Textdaten, wie z. B. eine Kreditkartennummer, u. U. in den Protokollen sichtbar. Der Anwendungsbereitsteller ist für das Erzwingen einer Zugriffssteuerung für die Konfigurations- und Ablaufverfolgungsdateien verantwortlich. Wenn Informationen dieser Art nicht sichtbar sein sollen, sollten Sie die Ablaufverfolgung deaktivieren, oder filtern Sie einen Teil der Daten heraus, wenn Sie die Ablaufverfolgungsprotokolle freigeben möchten.  
  
 Mithilfe der folgenden Tipps können Sie verhindern, dass der Inhalt einer Ablaufverfolgungsdatei unbeabsichtigt verfügbar gemacht wird:  
  
-   Stellen Sie sicher, dass die Protokolldateien durch Access Control Lists (ACL) sowohl bei WebHost als auch bei selbst gehosteten Szenarien geschützt werden.  
  
-   Wählen Sie eine Dateierweiterung aus, die nicht leicht mit einer Webanforderung ausgegeben werden kann. Die Dateierweiterung .xml ist z. B. nicht sicher. Sie finden im IIS-Administratorhandbuch eine Liste aller Erweiterungen, die bereitgestellt werden können.  
  
-   Geben Sie einen absoluten Pfad für den Protokolldateispeicherort an, der sich außerhalb des öffentlichen vroot-Verzeichnisses von WebHost befinden sollte, um einen Zugriff von externer Seite mithilfe eines Webbrowsers zu verhindern.  
  
 Standardmäßig werden Schlüssel und personenbezogene Informationen (PII, personally identifiable information), wie z. B. Benutzername und Passwort, nicht in Ablaufverfolgungen und protokollierten Nachrichten protokolliert. Ein Computeradministrator kann jedoch das `enableLoggingKnownPII`-Attribut im `machineSettings`-Element der Datei Machine.config verwenden, um Anwendungen, die auf dem Computer ausgeführt werden, zu ermöglichen, bekannte personenbezogene Informationen (PII) wie folgt zu protokollieren:  
  
```xml  
<configuration>  
   <system.ServiceModel>  
      <machineSettings enableLoggingKnownPii="Boolean"/>  
   </system.ServiceModel>  
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
            <add name="xml" />  
         </listeners>  
      </source>  
  </sources>  
</system.diagnostics>  
```  
  
 Wenn das `<machineSettings enableLoggingKnownPii="Boolean"/>`-Element außerhalb der Datei Machine.config vorhanden ist, löst das System einen <xref:System.Configuration.ConfigurationErrorsException> aus.  
  
 Die Änderungen sind nur wirksam, wenn die Anwendung gestartet oder neu gestartet wird. Ein Ereignis wird beim Start protokolliert, wenn beide Attribute auf `true` festgelegt werden. Ein Ereignis wird außerdem protokolliert, wenn `logKnownPii` auf `true` festgelegt wird, `enableLoggingKnownPii` jedoch `false` ist.  
  
 Weitere Informationen zur PII-Protokollierung finden Sie unter [PII Sicherheitssperre](../../../../../docs/framework/wcf/samples/pii-security-lockdown.md) Beispiel.  
  
 Der Computeradministrator und der Anwendungsbereitsteller sollten diese beiden Schalter mit großer Vorsicht verwenden. Wenn die PII-Protokollierung aktiviert ist, werden Sicherheitsschlüssel und PII protokolliert. Wenn sie deaktiviert ist, werden vertrauliche und anwendungsspezifische Daten immer noch in Nachrichtenheadern und -texten protokolliert. Eine ausführlichere Erläuterung auf Datenschutz und Schutz von PII verfügbar gemacht wird, finden Sie unter [Datenschutz](http://go.microsoft.com/fwlink/?LinkID=94647).  
  
 Außerdem wird die IP-Adresse des Nachrichtenabsenders einmal pro Verbindung bei verbindungsorientierten Transporten und einmal pro Nachricht bei anderen Übertragungen protokolliert. Dies geschieht ohne Bestätigung durch den Absender. Diese Protokollierung erfolgt jedoch nur auf den Ablaufverfolgungsebenen "Information" oder "Ausführlich", die nicht die Standard- oder empfohlenen Ablaufverfolgungsebenen für die Produktion sind, außer für das Livedebuggen.  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
