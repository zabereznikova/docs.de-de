---
title: Benutzerdefinierte SendMail-Aktivität
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: e7cc64e68c3d78b9ee7ec813700e96a52c239141
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182784"
---
# <a name="sendmail-custom-activity"></a>Benutzerdefinierte SendMail-Aktivität
In diesem Beispiel wird das Erstellen einer benutzerdefinierten Aktivität veranschaulicht, die von der <xref:System.Activities.AsyncCodeActivity> abgeleitet wird, um E-Mail-Nachrichten zur Verwendung in einer Workflowanwendung via SMTP zu senden. Die benutzerdefinierte Aktivität <xref:System.Net.Mail.SmtpClient> verwendet die Funktionen, e-Mails asynchron zu senden und E-Mails mit Authentifizierung zu senden. Außerdem werden Endbenutzerfunktionen wie Testmodus, Tokenersetzung, Dateivorlagen und Testablagepfad bereitgestellt.  
  
 In der folgenden Tabelle werden die Argumente für die `SendMail`-Aktivität aufgelistet.  
  
|Name|type|Beschreibung|  
|-|-|-|  
|Host|String|Die Adresse des SMTP-Serverhosts.|  
|Port|String|Der Port des SMTP-Diensts auf dem Host.|  
|EnableSsl|bool|Gibt an, ob der <xref:System.Net.Mail.SmtpClient> die Verbindung mit SSL (Secure Sockets Layer) verschlüsselt.|  
|UserName|String|Der Benutzername zum Einrichten der Anmeldeinformationen und Authentifizieren der <xref:System.Net.Mail.SmtpClient.Credentials%2A>-Absendereigenschaft.|  
|Kennwort|String|Das Kennwort zum Einrichten der Anmeldeinformationen und Authentifizieren der <xref:System.Net.Mail.SmtpClient.Credentials%2A>-Absendereigenschaft.|  
|Subject|<xref:System.Activities.InArgument%601>\<>|Der Betreff der Nachricht.|  
|Body|<xref:System.Activities.InArgument%601>\<>|Der Nachrichtentext.|  
|Attachments|<xref:System.Activities.InArgument%601>\<>|Anlagensammlung, die zum Speichern von Daten verwendet wird, die an diese E-Mail-Nachricht angehängt sind.|  
|From|<xref:System.Net.Mail.MailAddress>|Von der Adresse für diese E-Mail-Nachricht.|  
|To|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Adresssammlung, die die Empfänger dieser E-Mail-Nachricht enthält.|  
|CC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Adresssammlung, die die Empfänger der Co2-Kopie (CC) für diese E-Mail-Nachricht enthält.|  
|BCC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Adresssammlung, die die BCC-Empfänger (Blind Carbon Copy) für diese E-Mail-Nachricht enthält.|  
|Token|<xref:System.Activities.InArgument%601><IDictionary-Zeichenfolge,\<>>|Diese Token können im Text ersetzt werden. Mithilfe dieser Funktion können Benutzer bestimmte Werte im Text verwenden, die später durch Tokens ersetzt werden können, die mit dieser Eigenschaft angegeben werden.|  
|BodyTemplateFilePath|String|Der Pfad einer Vorlage für den Text. Mit der `SendMail`-Aktivität wird der Inhalt dieser Datei in die body-Eigenschaft kopiert.<br /><br /> Die Vorlage kann Token enthalten, die durch den Inhalt der Tokeneigenschaft ersetzt werden.|  
|TestMailTo|<xref:System.Net.Mail.MailAddress>|Wenn diese Eigenschaft festgelegt ist, werden alle E-Mails an die darin angegebene Adresse gesendet.<br /><br /> Diese Eigenschaft ist für das Testen von Workflows vorgesehen. Wenn Sie beispielsweise sicherstellen möchten, dass alle E-Mails gesendet werden, ohne sie an die tatsächlichen Empfänger zu senden.|  
|TestDropPath|String|Wenn diese Eigenschaft festgelegt ist, werden alle E-Mails auch in der angegebenen Datei gespeichert.<br /><br /> Diese Eigenschaft soll beim Testen oder Debuggen von Workflows verwendet werden, um sicherzustellen, dass das Format und der Inhalt der ausgehenden E-Mails geeignet sind.|  
  
## <a name="solution-contents"></a>Inhalt der Projektmappe  
 Die Projektmappe enthält zwei Projekte.  
  
|Project|Beschreibung|Wichtige Dateien|  
|-------------|-----------------|---------------------|  
|SendMail|Die SendMail-Aktivität|1. SendMail.cs: Durchführung für die Haupttätigkeit<br />2. SendMailDesigner.xaml und SendMailDesigner.xaml.cs: Designer für die SendMail-Aktivität<br />3. MailTemplateBody.htm: Vorlage für die zu versendende E-Mail.|  
|SendMailTestClient|Ein Client zum Testen der SendMail-Aktivität.  In diesem Projekt werden zwei Möglichkeiten zum Aufrufen der SendMail-Aktivität veranschaulicht: deklarativ und programmgesteuert.|1. Sequence1.xaml: Workflow, der die SendMail-Aktivität aufruft.<br />2. Program.cs: ruft Sequence1 auf und erstellt auch einen Workflow programmgesteuert, der SendMail verwendet.|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a>Weitere Konfiguration der SendMail-Aktivität  
 Benutzer können weitere Konfigurationen für die SendMail-Aktivität angeben, die in diesem Beispiel nicht gezeigt werden. Dies wird in den folgenden drei Abschnitten veranschaulicht.  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a>Senden einer E-Mail-Nachricht mit Token im Text  
 Mit diesem Codeausschnitt wird veranschaulicht, wie Sie eine E-Mail-Nachricht mit Token im Text senden können. Die Token werden in der body-Eigenschaft bereitgestellt. Die Werte für die Token werden in der Tokeneigenschaft bereitgestellt.  
  
```csharp  
IDictionary<string, string> tokens = new Dictionary<string, string>();  
tokens.Add("@name", "John Doe");  
tokens.Add("@date", DateTime.Now.ToString());  
tokens.Add("@server", "localhost");  
  
new SendMail  
{  
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Body = "Hello @name. This is a test email sent from @server. Current date is @date",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens)  
};  
```  
  
### <a name="sending-an-email-using-a-template"></a>Senden einer E-Mail-Nachricht mit einer Vorlage  
 Mit diesem Codeausschnitt wird veranschaulicht, wie Sie eine E-Mail-Nachricht mit Vorlagentoken im Text senden können. Beachten Sie, dass beim Festlegen der `BodyTemplateFilePath`-Eigenschaft kein Wert für die body-Eigenschaft angegeben werden muss (der Inhalt der Vorlagendatei wird in den Text kopiert).  
  
```csharp  
new SendMail  
{
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
    BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",
};  
```  
  
### <a name="sending-mails-in-testing-mode"></a>Senden von E-Mails im Testmodus  
 Dieser Codeausschnitt zeigt, wie die beiden Testeigenschaften `TestMailTo` festgelegt werden: Durch `john.doe@contoso.con` Festlegen auf alle Nachrichten wird an gesendet (ohne Berücksichtigung der Werte von To, Cc, Bcc). Durch Festlegen von TestDropPath werden alle ausgehenden E-Mail-Nachrichten außerdem unter dem angegebenen Pfad gespeichert. Diese Eigenschaften können unabhängig voneinander festgelegt werden (sie sind nicht verknüpft).  
  
```csharp  
new SendMail  
{
   From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
   Subject = "Test email",  
   Host = "localhost",  
   Port = 25,  
   Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
   BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",  
   TestMailTo= new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   TestDropPath = @"c:\Samples\SendMail\TestDropPath\",  
};  
```  
  
## <a name="set-up-instructions"></a>Setupanweisungen  
 Um dieses Beispiel ausführen zu können, ist der Zugriff auf einen SMTP-Server erforderlich.  
  
 Weitere Informationen zum Einrichten eines SMTP-Servers finden Sie unter den folgenden Links.  
  
- [Konfigurieren des SMTP-Diensts (IIS 6.0)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc784968(v=ws.10))  
  
- [IIS 7.0: Konfigurieren von SMTP-E-Mail](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772058(v=ws.10))  
  
- [Installieren des SMTP-Diensts](https://docs.microsoft.com/previous-versions/tn-archive/aa997480(v=exchg.65))  
  
 SMTP-Emulatoren können von Drittanbietern heruntergeladen werden.  
  
##### <a name="to-run-this-sample"></a>So führen Sie dieses Beispiel aus  
  
1. Öffnen Sie mit Visual Studio 2010 die Lösungsdatei SendMail.sln.  
  
2. Stellen Sie sicher, dass sie auf einen funktionierenden SMTP-Server zugreifen können. Beachten Sie dazu die Setupanweisungen.  
  
3. Konfigurieren Sie das Programm mit Ihrer Serveradresse sowie von und zu E-Mail-Adressen.  
  
     Um dieses Beispiel korrekt auszuführen, müssen Sie möglicherweise den Wert von Von- und An-E-Mail-Adressen und die Adresse des SMTP-Servers in Program.cs und in Sequence.xaml konfigurieren. Die Adressen müssen an beiden Speicherorten geändert werden, da das Programm E-Mail-Nachrichten auf unterschiedliche Weise sendet.  
  
4. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
5. Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`
