---
title: Benutzerdefinierte SendMail-Aktivität
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: f518beebe336080853e4dec3bca6f8539bbec304
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267588"
---
# <a name="sendmail-custom-activity"></a><span data-ttu-id="cbd49-102">Benutzerdefinierte SendMail-Aktivität</span><span class="sxs-lookup"><span data-stu-id="cbd49-102">SendMail Custom Activity</span></span>

<span data-ttu-id="cbd49-103">In diesem Beispiel wird das Erstellen einer benutzerdefinierten Aktivität veranschaulicht, die von der <xref:System.Activities.AsyncCodeActivity> abgeleitet wird, um E-Mail-Nachrichten zur Verwendung in einer Workflowanwendung via SMTP zu senden.</span><span class="sxs-lookup"><span data-stu-id="cbd49-103">This sample demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span> <span data-ttu-id="cbd49-104">Die benutzerdefinierte Aktivität verwendet die Funktionen von <xref:System.Net.Mail.SmtpClient> , um e-Mail-Nachrichten asynchron zu senden und e-Mails mit Authentifizierung zu senden.</span><span class="sxs-lookup"><span data-stu-id="cbd49-104">The custom activity uses the capabilities of <xref:System.Net.Mail.SmtpClient> to send email asynchronously and to send mail with authentication.</span></span> <span data-ttu-id="cbd49-105">Außerdem werden Endbenutzerfunktionen wie Testmodus, Tokenersetzung, Dateivorlagen und Testablagepfad bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="cbd49-105">It also provides some end-user features like test mode, token replacement, file templates, and test drop path.</span></span>  
  
 <span data-ttu-id="cbd49-106">In der folgenden Tabelle werden die Argumente für die `SendMail`-Aktivität aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="cbd49-106">The following table details the arguments for the `SendMail` activity.</span></span>  
  
|<span data-ttu-id="cbd49-107">Name</span><span class="sxs-lookup"><span data-stu-id="cbd49-107">Name</span></span>|<span data-ttu-id="cbd49-108">type</span><span class="sxs-lookup"><span data-stu-id="cbd49-108">Type</span></span>|<span data-ttu-id="cbd49-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cbd49-109">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="cbd49-110">Host</span><span class="sxs-lookup"><span data-stu-id="cbd49-110">Host</span></span>|<span data-ttu-id="cbd49-111">String</span><span class="sxs-lookup"><span data-stu-id="cbd49-111">String</span></span>|<span data-ttu-id="cbd49-112">Die Adresse des SMTP-Serverhosts.</span><span class="sxs-lookup"><span data-stu-id="cbd49-112">Address of the SMTP server host.</span></span>|  
|<span data-ttu-id="cbd49-113">Port</span><span class="sxs-lookup"><span data-stu-id="cbd49-113">Port</span></span>|<span data-ttu-id="cbd49-114">String</span><span class="sxs-lookup"><span data-stu-id="cbd49-114">String</span></span>|<span data-ttu-id="cbd49-115">Der Port des SMTP-Diensts auf dem Host.</span><span class="sxs-lookup"><span data-stu-id="cbd49-115">Port of the SMTP service in the host.</span></span>|  
|<span data-ttu-id="cbd49-116">EnableSsl</span><span class="sxs-lookup"><span data-stu-id="cbd49-116">EnableSsl</span></span>|<span data-ttu-id="cbd49-117">bool</span><span class="sxs-lookup"><span data-stu-id="cbd49-117">bool</span></span>|<span data-ttu-id="cbd49-118">Gibt an, ob der <xref:System.Net.Mail.SmtpClient> die Verbindung mit SSL (Secure Sockets Layer) verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="cbd49-118">Specifies whether the <xref:System.Net.Mail.SmtpClient> uses Secure Sockets Layer (SSL) to encrypt the connection.</span></span>|  
|<span data-ttu-id="cbd49-119">UserName</span><span class="sxs-lookup"><span data-stu-id="cbd49-119">UserName</span></span>|<span data-ttu-id="cbd49-120">String</span><span class="sxs-lookup"><span data-stu-id="cbd49-120">String</span></span>|<span data-ttu-id="cbd49-121">Der Benutzername zum Einrichten der Anmeldeinformationen und Authentifizieren der <xref:System.Net.Mail.SmtpClient.Credentials%2A>-Absendereigenschaft.</span><span class="sxs-lookup"><span data-stu-id="cbd49-121">Username to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="cbd49-122">Kennwort</span><span class="sxs-lookup"><span data-stu-id="cbd49-122">Password</span></span>|<span data-ttu-id="cbd49-123">String</span><span class="sxs-lookup"><span data-stu-id="cbd49-123">String</span></span>|<span data-ttu-id="cbd49-124">Das Kennwort zum Einrichten der Anmeldeinformationen und Authentifizieren der <xref:System.Net.Mail.SmtpClient.Credentials%2A>-Absendereigenschaft.</span><span class="sxs-lookup"><span data-stu-id="cbd49-124">Password to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="cbd49-125">Subject</span><span class="sxs-lookup"><span data-stu-id="cbd49-125">Subject</span></span>|<xref:System.Activities.InArgument%601>\<string>|<span data-ttu-id="cbd49-126">Der Betreff der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="cbd49-126">Subject of the message.</span></span>|  
|<span data-ttu-id="cbd49-127">Text</span><span class="sxs-lookup"><span data-stu-id="cbd49-127">Body</span></span>|<xref:System.Activities.InArgument%601>\<string>|<span data-ttu-id="cbd49-128">Der Nachrichtentext.</span><span class="sxs-lookup"><span data-stu-id="cbd49-128">Body of the message.</span></span>|  
|<span data-ttu-id="cbd49-129">Attachments</span><span class="sxs-lookup"><span data-stu-id="cbd49-129">Attachments</span></span>|<xref:System.Activities.InArgument%601>\<string>|<span data-ttu-id="cbd49-130">Anlagen Sammlung zum Speichern von Daten, die an diese e-Mail angefügt sind.</span><span class="sxs-lookup"><span data-stu-id="cbd49-130">Attachment collection used to store data attached to this email message.</span></span>|  
|<span data-ttu-id="cbd49-131">Von</span><span class="sxs-lookup"><span data-stu-id="cbd49-131">From</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="cbd49-132">Von der Adresse für diese e-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="cbd49-132">From address for this email message.</span></span>|  
|<span data-ttu-id="cbd49-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cbd49-133">To</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="cbd49-134">Adress Sammlung, die die Empfänger dieser e-Mail-Nachricht enthält.</span><span class="sxs-lookup"><span data-stu-id="cbd49-134">Address collection that contains the recipients of this email message.</span></span>|  
|<span data-ttu-id="cbd49-135">CC</span><span class="sxs-lookup"><span data-stu-id="cbd49-135">CC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="cbd49-136">Adress Sammlung, die die CC-Empfänger für diese e-Mail-Nachricht enthält.</span><span class="sxs-lookup"><span data-stu-id="cbd49-136">Address collection that contains the carbon copy (CC) recipients for this email message.</span></span>|  
|<span data-ttu-id="cbd49-137">BCC</span><span class="sxs-lookup"><span data-stu-id="cbd49-137">BCC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="cbd49-138">Die Adress Sammlung, die die Bcc-Empfänger (Blind Carbon Copy) für diese e-Mail-Nachricht enthält.</span><span class="sxs-lookup"><span data-stu-id="cbd49-138">Address collection that contains the blind carbon copy (BCC) recipients for this email message.</span></span>|  
|<span data-ttu-id="cbd49-139">Token</span><span class="sxs-lookup"><span data-stu-id="cbd49-139">Tokens</span></span>|<span data-ttu-id="cbd49-140"><xref:System.Activities.InArgument%601> IDictionary<\<string, string>></span><span class="sxs-lookup"><span data-stu-id="cbd49-140"><xref:System.Activities.InArgument%601><IDictionary\<string, string>></span></span>|<span data-ttu-id="cbd49-141">Diese Token können im Text ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="cbd49-141">Tokens to replace in the body.</span></span> <span data-ttu-id="cbd49-142">Mithilfe dieser Funktion können Benutzer bestimmte Werte im Text verwenden, die später durch Tokens ersetzt werden können, die mit dieser Eigenschaft angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cbd49-142">This feature allows users to specify some values in the body than can be replaced later by the tokens provided using this property.</span></span>|  
|<span data-ttu-id="cbd49-143">BodyTemplateFilePath</span><span class="sxs-lookup"><span data-stu-id="cbd49-143">BodyTemplateFilePath</span></span>|<span data-ttu-id="cbd49-144">String</span><span class="sxs-lookup"><span data-stu-id="cbd49-144">String</span></span>|<span data-ttu-id="cbd49-145">Der Pfad einer Vorlage für den Text.</span><span class="sxs-lookup"><span data-stu-id="cbd49-145">Path of a template for the body.</span></span> <span data-ttu-id="cbd49-146">Mit der `SendMail`-Aktivität wird der Inhalt dieser Datei in die body-Eigenschaft kopiert.</span><span class="sxs-lookup"><span data-stu-id="cbd49-146">The `SendMail` activity copies the contents of this file to its body property.</span></span><br /><br /> <span data-ttu-id="cbd49-147">Die Vorlage kann Token enthalten, die durch den Inhalt der Tokeneigenschaft ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="cbd49-147">The template can contain tokens that are replaced by the contents of the tokens property.</span></span>|  
|<span data-ttu-id="cbd49-148">TestMailTo</span><span class="sxs-lookup"><span data-stu-id="cbd49-148">TestMailTo</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="cbd49-149">Wenn diese Eigenschaft festgelegt ist, werden alle e-Mails an die darin angegebene Adresse gesendet.</span><span class="sxs-lookup"><span data-stu-id="cbd49-149">When this property is set, all emails are sent to the address specified in it.</span></span><br /><br /> <span data-ttu-id="cbd49-150">Diese Eigenschaft ist für das Testen von Workflows vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="cbd49-150">This property is intended to be used when testing workflows.</span></span> <span data-ttu-id="cbd49-151">Wenn Sie z. b. sicherstellen möchten, dass alle e-Mails gesendet werden, ohne dass Sie an die eigentlichen Empfänger gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="cbd49-151">For example, when you want to make sure that all emails are sent without sending them to the actual recipients.</span></span>|  
|<span data-ttu-id="cbd49-152">TestDropPath</span><span class="sxs-lookup"><span data-stu-id="cbd49-152">TestDropPath</span></span>|<span data-ttu-id="cbd49-153">String</span><span class="sxs-lookup"><span data-stu-id="cbd49-153">String</span></span>|<span data-ttu-id="cbd49-154">Wenn diese Eigenschaft festgelegt ist, werden alle e-Mails ebenfalls in der angegebenen Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cbd49-154">When this property is set, all emails are also saved in the specified file.</span></span><br /><br /> <span data-ttu-id="cbd49-155">Diese Eigenschaft soll beim Testen oder Debuggen von Workflows verwendet werden, um sicherzustellen, dass das Format und der Inhalt der ausgehenden e-Mails angemessen sind.</span><span class="sxs-lookup"><span data-stu-id="cbd49-155">This property is intended to be used when you are testing or debugging workflows, to make sure that the format and contents of the outgoing emails is appropriate.</span></span>|  
  
## <a name="solution-contents"></a><span data-ttu-id="cbd49-156">Inhalt der Projektmappe</span><span class="sxs-lookup"><span data-stu-id="cbd49-156">Solution Contents</span></span>  

 <span data-ttu-id="cbd49-157">Die Projektmappe enthält zwei Projekte.</span><span class="sxs-lookup"><span data-stu-id="cbd49-157">The solution contains two projects.</span></span>  
  
|<span data-ttu-id="cbd49-158">Projekt</span><span class="sxs-lookup"><span data-stu-id="cbd49-158">Project</span></span>|<span data-ttu-id="cbd49-159">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cbd49-159">Description</span></span>|<span data-ttu-id="cbd49-160">Wichtige Dateien</span><span class="sxs-lookup"><span data-stu-id="cbd49-160">Important Files</span></span>|  
|-------------|-----------------|---------------------|  
|<span data-ttu-id="cbd49-161">SendMail</span><span class="sxs-lookup"><span data-stu-id="cbd49-161">SendMail</span></span>|<span data-ttu-id="cbd49-162">Die SendMail-Aktivität</span><span class="sxs-lookup"><span data-stu-id="cbd49-162">The SendMail activity</span></span>|<span data-ttu-id="cbd49-163">1. sendmail.cs: Implementierung für die Hauptaktivität</span><span class="sxs-lookup"><span data-stu-id="cbd49-163">1.  SendMail.cs: implementation for the main activity</span></span><br /><span data-ttu-id="cbd49-164">2. sendmaildesigner. XAML und SendMailDesigner.XAML.cs: Designer für die sendmail-Aktivität</span><span class="sxs-lookup"><span data-stu-id="cbd49-164">2.  SendMailDesigner.xaml and SendMailDesigner.xaml.cs: designer for the SendMail activity</span></span><br /><span data-ttu-id="cbd49-165">3. MailTemplateBody.htm: die Vorlage für die zu sendende e-Mail.</span><span class="sxs-lookup"><span data-stu-id="cbd49-165">3.  MailTemplateBody.htm: template for the email to be sent out.</span></span>|  
|<span data-ttu-id="cbd49-166">SendMailTestClient</span><span class="sxs-lookup"><span data-stu-id="cbd49-166">SendMailTestClient</span></span>|<span data-ttu-id="cbd49-167">Ein Client zum Testen der SendMail-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="cbd49-167">Client to test the SendMail activity.</span></span>  <span data-ttu-id="cbd49-168">In diesem Projekt werden zwei Möglichkeiten zum Aufrufen der SendMail-Aktivität veranschaulicht: deklarativ und programmgesteuert.</span><span class="sxs-lookup"><span data-stu-id="cbd49-168">This project demonstrates two ways of invoking the SendMail activity: declaratively, and programmatically.</span></span>|<span data-ttu-id="cbd49-169">1. Sequence1. XAML: Workflow, der die sendmail-Aktivität aufruft.</span><span class="sxs-lookup"><span data-stu-id="cbd49-169">1.  Sequence1.xaml: workflow that invokes the SendMail activity.</span></span><br /><span data-ttu-id="cbd49-170">2. Program.cs: Ruft Sequence1 auf und erstellt auch Programm gesteuert einen Workflow, der sendmail verwendet.</span><span class="sxs-lookup"><span data-stu-id="cbd49-170">2.  Program.cs: invokes Sequence1 and also creates a workflow programmatically that uses SendMail.</span></span>|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a><span data-ttu-id="cbd49-171">Weitere Konfiguration der SendMail-Aktivität</span><span class="sxs-lookup"><span data-stu-id="cbd49-171">Further configuration of the SendMail activity</span></span>  

 <span data-ttu-id="cbd49-172">Benutzer können weitere Konfigurationen für die SendMail-Aktivität angeben, die in diesem Beispiel nicht gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cbd49-172">Although not shown in the sample, users can perform addition configuration of the SendMail activity.</span></span> <span data-ttu-id="cbd49-173">Dies wird in den folgenden drei Abschnitten veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="cbd49-173">The next three sections demonstrate how this is done.</span></span>  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a><span data-ttu-id="cbd49-174">Senden einer E-Mail-Nachricht mit Token im Text</span><span class="sxs-lookup"><span data-stu-id="cbd49-174">Sending an email using tokens specified in the body</span></span>  

 <span data-ttu-id="cbd49-175">Mit diesem Codeausschnitt wird veranschaulicht, wie Sie eine E-Mail-Nachricht mit Token im Text senden können.</span><span class="sxs-lookup"><span data-stu-id="cbd49-175">This code snippet demonstrates how you can send email with tokens in the body.</span></span> <span data-ttu-id="cbd49-176">Die Token werden in der body-Eigenschaft bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="cbd49-176">Notice how the tokens are provided in the body property.</span></span> <span data-ttu-id="cbd49-177">Die Werte für die Token werden in der Tokeneigenschaft bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="cbd49-177">Values for those tokens are provided to the tokens property.</span></span>  
  
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
  
### <a name="sending-an-email-using-a-template"></a><span data-ttu-id="cbd49-178">Senden einer E-Mail-Nachricht mit einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="cbd49-178">Sending an email using a template</span></span>  

 <span data-ttu-id="cbd49-179">Mit diesem Codeausschnitt wird veranschaulicht, wie Sie eine E-Mail-Nachricht mit Vorlagentoken im Text senden können.</span><span class="sxs-lookup"><span data-stu-id="cbd49-179">This snippet shows how to send an email using a template tokens in the body.</span></span> <span data-ttu-id="cbd49-180">Beachten Sie, dass beim Festlegen der `BodyTemplateFilePath`-Eigenschaft kein Wert für die body-Eigenschaft angegeben werden muss (der Inhalt der Vorlagendatei wird in den Text kopiert).</span><span class="sxs-lookup"><span data-stu-id="cbd49-180">Notice that when setting the `BodyTemplateFilePath` property we don’t need to provide the value for Body property (the contents of the template file will be copied to the body).</span></span>  
  
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
  
### <a name="sending-mails-in-testing-mode"></a><span data-ttu-id="cbd49-181">Senden von E-Mails im Testmodus</span><span class="sxs-lookup"><span data-stu-id="cbd49-181">Sending Mails in Testing Mode</span></span>  

 <span data-ttu-id="cbd49-182">In diesem Code Ausschnitt wird gezeigt, wie die zwei Test Eigenschaften festgelegt werden: durch Festlegen von `TestMailTo` auf alle Nachrichten, die an gesendet werden `john.doe@contoso.con` (ohne Berücksichtigung der Werte von to, CC, BCC).</span><span class="sxs-lookup"><span data-stu-id="cbd49-182">This code snippet shows how to set the two testing properties: by setting `TestMailTo` to all messages will be sent to `john.doe@contoso.con` (without regard of the values of To, Cc, Bcc).</span></span> <span data-ttu-id="cbd49-183">Durch Festlegen von TestDropPath werden alle ausgehenden E-Mail-Nachrichten außerdem unter dem angegebenen Pfad gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cbd49-183">By setting TestDropPath all outgoing emails will be also recorded in the provided path.</span></span> <span data-ttu-id="cbd49-184">Diese Eigenschaften können unabhängig voneinander festgelegt werden (sie sind nicht verknüpft).</span><span class="sxs-lookup"><span data-stu-id="cbd49-184">These properties can be set independently (they are not related).</span></span>  
  
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
  
## <a name="set-up-instructions"></a><span data-ttu-id="cbd49-185">Setupanweisungen</span><span class="sxs-lookup"><span data-stu-id="cbd49-185">Set-Up Instructions</span></span>  

 <span data-ttu-id="cbd49-186">Um dieses Beispiel ausführen zu können, ist der Zugriff auf einen SMTP-Server erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cbd49-186">Access to a SMTP server is required for this sample.</span></span>  
  
 <span data-ttu-id="cbd49-187">Weitere Informationen zum Einrichten eines SMTP-Servers finden Sie unter den folgenden Links.</span><span class="sxs-lookup"><span data-stu-id="cbd49-187">For more information about setting up a SMTP server, see the following links.</span></span>  
  
- <span data-ttu-id="cbd49-188">[Konfigurieren des SMTP-Diensts (IIS 6.0)](/previous-versions/windows/it-pro/windows-server-2003/cc784968(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="cbd49-188">[Configuring the SMTP Service (IIS 6.0)](/previous-versions/windows/it-pro/windows-server-2003/cc784968(v=ws.10))</span></span>  
  
- <span data-ttu-id="cbd49-189">[IIS 7.0: Konfigurieren von SMTP-E-Mail](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772058(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="cbd49-189">[IIS 7.0: Configure SMTP E-Mail](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772058(v=ws.10))</span></span>  
  
- <span data-ttu-id="cbd49-190">[Installieren des SMTP-Diensts](/previous-versions/tn-archive/aa997480(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="cbd49-190">[How to Install the SMTP Service](/previous-versions/tn-archive/aa997480(v=exchg.65))</span></span>  
  
 <span data-ttu-id="cbd49-191">SMTP-Emulatoren können von Drittanbietern heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="cbd49-191">SMTP emulators provided by third parties are available for download.</span></span>  
  
##### <a name="to-run-this-sample"></a><span data-ttu-id="cbd49-192">So führen Sie dieses Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="cbd49-192">To run this sample</span></span>  
  
1. <span data-ttu-id="cbd49-193">Öffnen Sie die Projektmappendatei sendmail. sln mithilfe von Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="cbd49-193">Using Visual Studio 2010, open the SendMail.sln solution file.</span></span>  
  
2. <span data-ttu-id="cbd49-194">Stellen Sie sicher, dass sie auf einen funktionierenden SMTP-Server zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="cbd49-194">Ensure that you have access to a valid SMTP server.</span></span> <span data-ttu-id="cbd49-195">Beachten Sie dazu die Setupanweisungen.</span><span class="sxs-lookup"><span data-stu-id="cbd49-195">See the set-up instructions.</span></span>  
  
3. <span data-ttu-id="cbd49-196">Konfigurieren Sie das Programm mit Ihrer Server Adresse und von und an e-Mail-Adressen.</span><span class="sxs-lookup"><span data-stu-id="cbd49-196">Configure the program with your server address, and From and To email addresses.</span></span>  
  
     <span data-ttu-id="cbd49-197">Um dieses Beispiel ordnungsgemäß auszuführen, müssen Sie möglicherweise den Wert von und für e-Mail-Adressen und die Adresse des SMTP-Servers in Program.cs und Sequence. XAML konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cbd49-197">To correctly run this sample, you may need to configure the value of From and To email addresses and the address of the SMTP server in  Program.cs and in Sequence.xaml.</span></span> <span data-ttu-id="cbd49-198">Die Adressen müssen an beiden Speicherorten geändert werden, da das Programm E-Mail-Nachrichten auf unterschiedliche Weise sendet.</span><span class="sxs-lookup"><span data-stu-id="cbd49-198">You will need to change the address in both locations since the program sends mail in two different ways</span></span>  
  
4. <span data-ttu-id="cbd49-199">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cbd49-199">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5. <span data-ttu-id="cbd49-200">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cbd49-200">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="cbd49-201">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="cbd49-201">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cbd49-202">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="cbd49-202">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="cbd49-203">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cbd49-203">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cbd49-204">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="cbd49-204">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`
