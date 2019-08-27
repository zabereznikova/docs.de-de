---
title: Benutzerdefinierte SendMail-Aktivität
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: 9325817a24fee3ba04c2c305ebfdfbc6ff6da1bd
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70038114"
---
# <a name="sendmail-custom-activity"></a>Benutzerdefinierte SendMail-Aktivität
In diesem Beispiel wird das Erstellen einer benutzerdefinierten Aktivität veranschaulicht, die von der <xref:System.Activities.AsyncCodeActivity> abgeleitet wird, um E-Mail-Nachrichten zur Verwendung in einer Workflowanwendung via SMTP zu senden. Die benutzerdefinierte Aktivität verwendet die Funktionen <xref:System.Net.Mail.SmtpClient> von, um e-Mail-Nachrichten asynchron zu senden und e-Mails mit Authentifizierung zu senden. Außerdem werden Endbenutzerfunktionen wie Testmodus, Tokenersetzung, Dateivorlagen und Testablagepfad bereitgestellt.  
  
 In der folgenden Tabelle werden die Argumente für die `SendMail`-Aktivität aufgelistet.  
  
|Name|Typ|Beschreibung|  
|-|-|-|  
|Host|Zeichenfolge|Die Adresse des SMTP-Serverhosts.|  
|Port|Zeichenfolge|Der Port des SMTP-Diensts auf dem Host.|  
|EnableSsl|bool|Gibt an, ob der <xref:System.Net.Mail.SmtpClient> die Verbindung mit SSL (Secure Sockets Layer) verschlüsselt.|  
|UserName|Zeichenfolge|Der Benutzername zum Einrichten der Anmeldeinformationen und Authentifizieren der <xref:System.Net.Mail.SmtpClient.Credentials%2A>-Absendereigenschaft.|  
|Kennwort|Zeichenfolge|Das Kennwort zum Einrichten der Anmeldeinformationen und Authentifizieren der <xref:System.Net.Mail.SmtpClient.Credentials%2A>-Absendereigenschaft.|  
|Betreff|<xref:System.Activities.InArgument%601>\<string>|Der Betreff der Nachricht.|  
|Text|<xref:System.Activities.InArgument%601>\<string>|Der Nachrichtentext.|  
|Anlagen|<xref:System.Activities.InArgument%601>\<string>|Anlagen Sammlung zum Speichern von Daten, die an diese e-Mail angefügt sind.|  
|Von|<xref:System.Net.Mail.MailAddress>|Von der Adresse für diese e-Mail-Nachricht.|  
|Beschreibung|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Adress Sammlung, die die Empfänger dieser e-Mail-Nachricht enthält.|  
|CC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Adress Sammlung, die die CC-Empfänger für diese e-Mail-Nachricht enthält.|  
|BCC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Die Adress Sammlung, die die Bcc-Empfänger (Blind Carbon Copy) für diese e-Mail-Nachricht enthält.|  
|tokens|<xref:System.Activities.InArgument%601>< IDictionary\<-Zeichenfolge, Zeichenfolge > >|Diese Token können im Text ersetzt werden. Mithilfe dieser Funktion können Benutzer bestimmte Werte im Text verwenden, die später durch Tokens ersetzt werden können, die mit dieser Eigenschaft angegeben werden.|  
|BodyTemplateFilePath|Zeichenfolge|Der Pfad einer Vorlage für den Text. Mit der `SendMail`-Aktivität wird der Inhalt dieser Datei in die body-Eigenschaft kopiert.<br /><br /> Die Vorlage kann Token enthalten, die durch den Inhalt der Tokeneigenschaft ersetzt werden.|  
|TestMailTo|<xref:System.Net.Mail.MailAddress>|Wenn diese Eigenschaft festgelegt ist, werden alle e-Mails an die darin angegebene Adresse gesendet.<br /><br /> Diese Eigenschaft ist für das Testen von Workflows vorgesehen. Wenn Sie z. b. sicherstellen möchten, dass alle e-Mails gesendet werden, ohne dass Sie an die eigentlichen Empfänger gesendet werden.|  
|TestDropPath|Zeichenfolge|Wenn diese Eigenschaft festgelegt ist, werden alle e-Mails ebenfalls in der angegebenen Datei gespeichert.<br /><br /> Diese Eigenschaft soll beim Testen oder Debuggen von Workflows verwendet werden, um sicherzustellen, dass das Format und der Inhalt der ausgehenden e-Mails angemessen sind.|  
  
## <a name="solution-contents"></a>Inhalt der Projektmappe  
 Die Projektmappe enthält zwei Projekte.  
  
|Projekt|Beschreibung|Wichtige Dateien|  
|-------------|-----------------|---------------------|  
|SendMail|Die SendMail-Aktivität|1.  SendMail.cs: Implementierung für die Hauptaktivität<br />2.  SendMailDesigner.xaml und SendMailDesigner.xaml.cs: Designer für die SendMail-Aktivität<br />3.  MailTemplateBody.htm: Vorlage für die zu sendende E-Mail-Nachricht.|  
|SendMailTestClient|Ein Client zum Testen der SendMail-Aktivität.  In diesem Projekt werden zwei Möglichkeiten zum Aufrufen der SendMail-Aktivität veranschaulicht: deklarativ und programmgesteuert.|1.  Sequence1.xaml: Workflow zum Aufrufen der SendMail-Aktivität.<br />2.  Program.cs: ruft Sequence1 auf und erstellt programmgesteuert einen Workflow mit SendMail.|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a>Weitere Konfiguration der SendMail-Aktivität  
 Benutzer können weitere Konfigurationen für die SendMail-Aktivität angeben, die in diesem Beispiel nicht gezeigt werden. Dies wird in den folgenden drei Abschnitten veranschaulicht.  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a>Senden einer E-Mail-Nachricht mit Token im Text  
 Mit diesem Codeausschnitt wird veranschaulicht, wie Sie eine E-Mail-Nachricht mit Token im Text senden können. Die Token werden in der body-Eigenschaft bereitgestellt. Die Werte für die Token werden in der Tokeneigenschaft bereitgestellt.  
  
```html  
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
  
```  
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
 In diesem Code Ausschnitt wird gezeigt, wie die zwei Test Eigenschaften festgelegt werden `TestMailTo` : durch Festlegen von auf alle nach `john.doe@contoso.con` richten, die an gesendet werden (ohne Berücksichtigung der Werte von to, CC, BCC). Durch Festlegen von TestDropPath werden alle ausgehenden E-Mail-Nachrichten außerdem unter dem angegebenen Pfad gespeichert. Diese Eigenschaften können unabhängig voneinander festgelegt werden (sie sind nicht verknüpft).  
  
```  
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
  
- [Microsoft Technet](https://go.microsoft.com/fwlink/?LinkId=166060)  
  
- [Konfigurieren des SMTP-Dienstanbieter (IIS 6,0)](https://go.microsoft.com/fwlink/?LinkId=150456)  
  
- [IIS 7.0: Konfigurieren von SMTP-e-Mails](https://go.microsoft.com/fwlink/?LinkId=150457)  
  
- [Installieren des SMTP-Dienstanbieter](https://go.microsoft.com/fwlink/?LinkId=150458)  
  
 SMTP-Emulatoren können von Drittanbietern heruntergeladen werden.  
  
##### <a name="to-run-this-sample"></a>So führen Sie dieses Beispiel aus  
  
1. Öffnen Sie die Projektmappendatei sendmail. sln mithilfe von Visual Studio 2010.  
  
2. Stellen Sie sicher, dass sie auf einen funktionierenden SMTP-Server zugreifen können. Beachten Sie dazu die Setupanweisungen.  
  
3. Konfigurieren Sie das Programm mit Ihrer Server Adresse und von und an e-Mail-Adressen.  
  
     Um dieses Beispiel ordnungsgemäß auszuführen, müssen Sie möglicherweise den Wert von und für e-Mail-Adressen und die Adresse des SMTP-Servers in Program.cs und Sequence. XAML konfigurieren. Die Adressen müssen an beiden Speicherorten geändert werden, da das Programm E-Mail-Nachrichten auf unterschiedliche Weise sendet.  
  
4. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
5. Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`
