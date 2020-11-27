---
title: Schnelleinstieg zur Problembehandlung in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], troubleshooting
- Windows Communication Foundation [WCF], troubleshooting
ms.assetid: a9ea7a53-f31a-46eb-806e-898e465a4992
ms.openlocfilehash: 7df178334ca3ef5b901e3e82bf39592434ee059e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279726"
---
# <a name="wcf-troubleshooting-quickstart"></a><span data-ttu-id="fa07e-102">Schnelleinstieg zur Problembehandlung in WCF</span><span class="sxs-lookup"><span data-stu-id="fa07e-102">WCF Troubleshooting Quickstart</span></span>

<span data-ttu-id="fa07e-103">In diesem Thema wird eine Reihe bekannter Probleme aufgeführt, denen Kunden beim Entwickeln von WCF-Clients und -Diensten begegnet sind.</span><span class="sxs-lookup"><span data-stu-id="fa07e-103">This topic lists a number of known issues customers have run into while developing WCF clients and services.</span></span> <span data-ttu-id="fa07e-104">Wenn Ihr spezifisches Problem nicht in dieser Liste enthalten ist, sollten Sie die Ablaufverfolgung für den Dienst konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fa07e-104">If the issue you are running into is not in this list, we recommend you configure tracing for your service.</span></span> <span data-ttu-id="fa07e-105">Dadurch wird eine Ablaufverfolgungsdatei generiert, die Sie im Ablaufverfolgungsdatei-Viewer anzeigen können, um detaillierte Informationen zu Ausnahmen im Dienst zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fa07e-105">This will generate a trace file that you can view with the trace file viewer and get detailed information about exceptions that may be occurring within the service.</span></span> <span data-ttu-id="fa07e-106">Weitere Informationen zum Konfigurieren der Ablaufverfolgung finden Sie unter [Configuring Tracing](./diagnostics/tracing/configuring-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="fa07e-106">For more information on configuring tracing, see: [Configuring Tracing](./diagnostics/tracing/configuring-tracing.md).</span></span> <span data-ttu-id="fa07e-107">Weitere Informationen zum Ablaufverfolgungsdatei-Viewer finden Sie unter [Service Trace Viewer Tool (SvcTraceViewer.exe)](service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="fa07e-107">For more information on the trace file viewer, see: [Service Trace Viewer Tool (SvcTraceViewer.exe)](service-trace-viewer-tool-svctraceviewer-exe.md).</span></span>  
  
1. [<span data-ttu-id="fa07e-108">Wenn ich nach dem Installieren von Windows 7 und IIS versuche, auf einen WCF-Dienst zuzugreifen, erhalte ich die folgende Fehlermeldung: HTTP-Fehler 404.3 – Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="fa07e-108">After installing Windows 7 and IIS, when I attempt to browse to a WCF service I get the following error message: HTTP Error 404.3 – Not Found</span></span>](#bkmk_0)  
  
     <span data-ttu-id="fa07e-109">HTTP Fehler 404.3 – Nicht gefunden. Die angeforderte Seite kann aufgrund einer Konfigurationserweiterung nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fa07e-109">HTTP Error 404.3 – Not FoundThe page you are requesting cannot be served because of the extension configuration.</span></span> <span data-ttu-id="fa07e-110">Wenn es sich bei der Seite um ein Skript handelt, müssen Sie einen Handler hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fa07e-110">If the page is a script, add a handler.</span></span> <span data-ttu-id="fa07e-111">Wenn die Datei heruntergeladen werden soll, müssen Sie eine MIME-Zuordnung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fa07e-111">If the file should be downloaded, add a MIME map.</span></span> <span data-ttu-id="fa07e-112">Detaillierte Fehlerinformationen finden Sie unter dem Modul StaticFileModule.</span><span class="sxs-lookup"><span data-stu-id="fa07e-112">Detailed Error InformationModule StaticFileModule.</span></span>  
  
2. [<span data-ttu-id="fa07e-113">Manchmal erhalte ich eine messagesecurrityexception bei der zweiten Anforderung, wenn sich der Client nach der ersten Anforderung eine Weile im Leerlauf befindet. Was passiert?</span><span class="sxs-lookup"><span data-stu-id="fa07e-113">Sometimes I receive a MessageSecurityException on the second request if my client is idle for a while after the first request. What is happening?</span></span>](#BKMK_q1)  
  
3. [<span data-ttu-id="fa07e-114">Der Dienst beginnt mit dem Ablehnen neuer Clients, nachdem ungefähr 10 Clients damit interagieren. Was passiert?</span><span class="sxs-lookup"><span data-stu-id="fa07e-114">My service starts to reject new clients after about 10 clients are interacting with it. What is happening?</span></span>](#BKMK_q2)  
  
4. [<span data-ttu-id="fa07e-115">Kann ich die Dienstkonfiguration aus einer anderen Quelle laden als der Konfigurationsdatei der WCF-Anwendung?</span><span class="sxs-lookup"><span data-stu-id="fa07e-115">Can I load my service configuration from somewhere other than the WCF application’s configuration file?</span></span>](#BKMK_q3)  
  
5. [<span data-ttu-id="fa07e-116">Der Dienst und der Client funktionieren hervorragend, aber ich kann ihn nicht zum Funktionieren machen, wenn sich der Client auf einem anderen Computer befindet? Was passiert?</span><span class="sxs-lookup"><span data-stu-id="fa07e-116">My service and client work great, but I can’t get them to work when the client is on another computer? What’s happening?</span></span>](#BKMK_q4)  
  
6. [<span data-ttu-id="fa07e-117">Wenn eine FaultException ausgelöst \<Exception> wird, bei der der Typ eine Ausnahme ist, erhalte ich immer einen allgemeinen FaultException-Typ auf dem Client, nicht den generischen Typ. Was passiert?</span><span class="sxs-lookup"><span data-stu-id="fa07e-117">When I throw a FaultException\<Exception> where the type is an exception, I always receive a general FaultException type on the client and not the generic type. What’s happening?</span></span>](#BKMK_q5)  
  
7. [<span data-ttu-id="fa07e-118">Es scheint, als ob unidirektionale und Anforderung-Antwort-Vorgänge mit ungefähr derselben Geschwindigkeit zurückgegeben werden, wenn die Antwort keine Daten enthält. Was passiert?</span><span class="sxs-lookup"><span data-stu-id="fa07e-118">It seems like one-way and request-reply operations return at roughly the same speed when the reply contains no data. What's happening?</span></span>](#BKMK_q6)  
  
8. [<span data-ttu-id="fa07e-119">Ich verwende ein X. 509-Zertifikat mit meinem Dienst und erhalte eine System. Security. Cryptography. CryptographicException. Was passiert?</span><span class="sxs-lookup"><span data-stu-id="fa07e-119">I’m using an X.509 certificate with my service and I get a System.Security.Cryptography.CryptographicException. What’s happening?</span></span>](#BKMK_q77)  
  
9. [<span data-ttu-id="fa07e-120">Ich habe den ersten Parameter eines Vorgangs von Großbuchstaben in Kleinbuchstaben geändert; nun löst der Client eine Ausnahme aus. Was passiert?</span><span class="sxs-lookup"><span data-stu-id="fa07e-120">I changed the first parameter of an operation from uppercase to lowercase; now my client throws an exception. What's happening?</span></span>](#BKMK_q88)  
  
10. [<span data-ttu-id="fa07e-121">Ich verwende eines meiner Ablauf Verfolgungs Tools, und ich erhalte eine EndpointNotFoundException. Was passiert?</span><span class="sxs-lookup"><span data-stu-id="fa07e-121">I’m using one of my tracing tools and I get an EndpointNotFoundException. What’s happening?</span></span>](#BKMK_q99)  
  
11. [<span data-ttu-id="fa07e-122">Beim Aufruf einer WCF-Web HTTP-Anwendung aus einer WCF-SOAP-Anwendung gibt der Dienst die folgende Fehlermeldung zurück: 405 "Method Not Allowed"</span><span class="sxs-lookup"><span data-stu-id="fa07e-122">When calling a WCF Web HTTP application from a WCF SOAP application the service returns the following error: 405 Method Not Allowed</span></span>](#BK_MK99)  
  
 [<span data-ttu-id="fa07e-123">Was ist die Basisadresse? Wie verhält es sich mit einer Endpunkt Adresse?</span><span class="sxs-lookup"><span data-stu-id="fa07e-123">What is the base address? How does it relate to an endpoint address?</span></span>](#BKMK_q10)  
  
<a name="bkmk_0"></a>

## <a name="after-installing-windows-7-and-iis-when-i-attempt-to-browse-to-a-wcf-service-i-get-the-following-error-message-http-error-4043--not-found"></a><span data-ttu-id="fa07e-124">Wenn ich nach dem Installieren von Windows 7 und IIS versuche, auf einen WCF-Dienst zuzugreifen, erhalte ich die folgende Fehlermeldung: HTTP-Fehler 404.3 – Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="fa07e-124">After installing Windows 7 and IIS, when I attempt to browse to a WCF service I get the following error message: HTTP Error 404.3 – Not Found</span></span>  

 <span data-ttu-id="fa07e-125">Die vollständige Fehlermeldung lautet:</span><span class="sxs-lookup"><span data-stu-id="fa07e-125">The full error message is:</span></span>  
  
 <span data-ttu-id="fa07e-126">HTTP Fehler 404.3 – Nicht gefunden. Die angeforderte Seite kann aufgrund einer Konfigurationserweiterung nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fa07e-126">HTTP Error 404.3 – Not FoundThe page you are requesting cannot be served because of the extension configuration.</span></span> <span data-ttu-id="fa07e-127">Wenn es sich bei der Seite um ein Skript handelt, müssen Sie einen Handler hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fa07e-127">If the page is a script, add a handler.</span></span> <span data-ttu-id="fa07e-128">Wenn die Datei heruntergeladen werden soll, müssen Sie eine MIME-Zuordnung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fa07e-128">If the file should be downloaded, add a MIME map.</span></span> <span data-ttu-id="fa07e-129">Detaillierte Fehlerinformationen finden Sie unter dem Modul StaticFileModule.</span><span class="sxs-lookup"><span data-stu-id="fa07e-129">Detailed Error InformationModule StaticFileModule.</span></span>  
  
 <span data-ttu-id="fa07e-130">Diese Fehlermeldung tritt auf, wenn die Option "Windows Communication Foundation http-Aktivierung" nicht explizit in der Systemsteuerung festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="fa07e-130">This error message occurs when "Windows Communication Foundation HTTP Activation" is not explicitly set in the Control Panel.</span></span> <span data-ttu-id="fa07e-131">Um dies festzulegen, wechseln Sie zur Systemsteuerung, und klicken Sie in der unteren linken Ecke des Fensters auf "Programme".</span><span class="sxs-lookup"><span data-stu-id="fa07e-131">To set this go to the Control Panel, click Programs in the lower left-hand corner of the window.</span></span> <span data-ttu-id="fa07e-132">Klicken Sie auf "Windows-Funktionen ein- oder ausschalten".</span><span class="sxs-lookup"><span data-stu-id="fa07e-132">Click Turn Windows features on or off.</span></span> <span data-ttu-id="fa07e-133">Erweitern Sie "Microsoft .NET Framework 3.5.1", und wählen Sie "Windows Communication Foundation-Http-Aktivierung" aus.</span><span class="sxs-lookup"><span data-stu-id="fa07e-133">Expand Microsoft .NET Framework 3.5.1 and select Windows Communication Foundation HTTP Activation.</span></span>  
  
<a name="BKMK_q1"></a>

## <a name="sometimes-i-receive-a-messagesecurityexception-on-the-second-request-if-my-client-is-idle-for-a-while-after-the-first-request-what-is-happening"></a><span data-ttu-id="fa07e-134">Manchmal wird eine MessageSecurityException bei der zweiten Anforderung ausgelöst, wenn sich der Client nach der ersten Anforderung eine Weile im Leerlauf befunden hat.</span><span class="sxs-lookup"><span data-stu-id="fa07e-134">Sometimes I receive a MessageSecurityException on the second request if my client is idle for a while after the first request.</span></span> <span data-ttu-id="fa07e-135">Was passiert?</span><span class="sxs-lookup"><span data-stu-id="fa07e-135">What is happening?</span></span>  

 <span data-ttu-id="fa07e-136">Die zweite Anforderung kann in erster Linie aus zwei Gründen fehlschlagen: (1) Das Timeout der Sitzung wurde überschritten. (2) Der Webserver, der diesen Dienst hostet, wird wiederverwendet.</span><span class="sxs-lookup"><span data-stu-id="fa07e-136">The second request can fail primarily for two reasons: (1) the session has timed out or (2) the Web server that is hosting the service is recycled.</span></span> <span data-ttu-id="fa07e-137">Im ersten Fall ist die Sitzung gültig, bis das Timeout für den Dienst eintritt. Wenn der Dienst innerhalb der in der Bindung des Diensts angegebenen Zeitspanne () keine Anforderung vom Client empfängt <xref:System.ServiceModel.Channels.Binding.ReceiveTimeout%2A> , beendet der Dienst die Sicherheits Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fa07e-137">In the first case, the session is valid until the service times out. When the service does not receive a request from the client within the period of time specified in the service's binding (<xref:System.ServiceModel.Channels.Binding.ReceiveTimeout%2A>), the service terminates the security session.</span></span> <span data-ttu-id="fa07e-138">Nachfolgende Clientnachrichten führen zu <xref:System.ServiceModel.Security.MessageSecurityException>.</span><span class="sxs-lookup"><span data-stu-id="fa07e-138">Subsequent client messages result in the <xref:System.ServiceModel.Security.MessageSecurityException>.</span></span> <span data-ttu-id="fa07e-139">Der Code muss erneut eine Sicherheitssitzung mit dem Dienst herstellen, um weitere Nachrichten senden oder ein Token für den Sicherheitszustandskontext verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="fa07e-139">The client must re-establish a secure session with the service to send future messages or use a stateful security context token.</span></span> <span data-ttu-id="fa07e-140">Token für den Sicherheitszustandskontext sorgen auch dafür, dass eine Sicherheitssitzung das Wiederverwenden eines Webservers überdauert.</span><span class="sxs-lookup"><span data-stu-id="fa07e-140">Stateful security context tokens also allow a secure session to survive a Web server being recycled.</span></span> <span data-ttu-id="fa07e-141">Weitere Informationen zur Verwendung von Zustands behafteten sicheren Kontext Token in einer sicheren Sitzung finden Sie unter Gewusst [wie: Erstellen eines Sicherheitskontext Tokens für eine sichere Sitzung](./feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span><span class="sxs-lookup"><span data-stu-id="fa07e-141">For more information about using stateful secure context tokens in a secure session, see [How to: Create a Security Context Token for a Secure Session](./feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span> <span data-ttu-id="fa07e-142">Stattdessen können Sie Sicherheitssitzungen auch deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fa07e-142">Alternatively, you can disable secure sessions.</span></span> <span data-ttu-id="fa07e-143">Wenn Sie die- [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) Bindung verwenden, können Sie die- `establishSecurityContext` Eigenschaft auf festlegen, `false` um sichere Sitzungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fa07e-143">When you use the [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) binding, you can set the `establishSecurityContext` property to `false` to disable secure sessions.</span></span> <span data-ttu-id="fa07e-144">Wenn Sie Sicherheitssitzungen für andere Bindungen deaktivieren möchten, müssen Sie eine benutzerdefinierte Bindung erstellen.</span><span class="sxs-lookup"><span data-stu-id="fa07e-144">To disable secure sessions for other bindings, you must create a custom binding.</span></span> <span data-ttu-id="fa07e-145">Ausführliche Informationen zum Erstellen einer benutzerdefinierten Bindung finden Sie unter [How to: Create a Custom Binding Using the SecurityBindingElement](./feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="fa07e-145">For details about creating a custom binding, see [How to: Create a Custom Binding Using the SecurityBindingElement](./feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span> <span data-ttu-id="fa07e-146">Bevor Sie eine dieser Optionen anwenden, müssen Sie die Sicherheitsanforderungen der Anwendung kennen.</span><span class="sxs-lookup"><span data-stu-id="fa07e-146">Before you apply any of these options, you must understand your application's security requirements.</span></span>  
  
<a name="BKMK_q2"></a>

## <a name="my-service-starts-to-reject-new-clients-after-about-10-clients-are-interacting-with-it-what-is-happening"></a><span data-ttu-id="fa07e-147">Der Dienst lehnt nach einer Interaktion mit ungefähr 10 Clients weitere Clients ab.</span><span class="sxs-lookup"><span data-stu-id="fa07e-147">My service starts to reject new clients after about 10 clients are interacting with it.</span></span> <span data-ttu-id="fa07e-148">Was passiert?</span><span class="sxs-lookup"><span data-stu-id="fa07e-148">What is happening?</span></span>  

 <span data-ttu-id="fa07e-149">Standardmäßig können Dienste nur 10 Sitzungen gleichzeitig verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="fa07e-149">By default, services can have only 10 concurrent sessions.</span></span> <span data-ttu-id="fa07e-150">Wenn die Dienstbindungen Sitzungen verwenden, akzeptiert der Dienst neue Clientverbindungen folglich, bis diese Zahl erreicht ist. Anschließend lehnt er neue Clientverbindungen ab, bis eine der aktuellen Sitzungen beendet wird.</span><span class="sxs-lookup"><span data-stu-id="fa07e-150">Therefore, if the service bindings use sessions, the service accepts new client connections until it reaches that number, after which it refuses new client connections until one of the current sessions ends.</span></span> <span data-ttu-id="fa07e-151">Es gibt verschiedene Möglichkeiten, mehr Clients zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="fa07e-151">You can support more clients in a number of ways.</span></span> <span data-ttu-id="fa07e-152">Wenn der Dienst keine Sitzungen erfordert, verwenden Sie keine sitzungsbasierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="fa07e-152">If your service does not require sessions, do not use a sessionful binding.</span></span> <span data-ttu-id="fa07e-153">(Weitere Informationen finden Sie unter [Verwenden von Sitzungen](using-sessions.md).) Eine weitere Möglichkeit besteht darin, das Sitzungs Limit zu erhöhen, indem Sie den Wert der- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A> Eigenschaft auf die für ihre Umstände geeignete Zahl ändern.</span><span class="sxs-lookup"><span data-stu-id="fa07e-153">(For more information, see [Using Sessions](using-sessions.md).) Another option is to increase the session limit by changing the value of the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A> property to the number appropriate to your circumstance.</span></span>  
  
<a name="BKMK_q3"></a>

## <a name="can-i-load-my-service-configuration-from-somewhere-other-than-the-wcf-applications-configuration-file"></a><span data-ttu-id="fa07e-154">Kann ich die Dienstkonfiguration aus einer anderen Quelle laden als der Konfigurationsdatei der WCF-Anwendung?</span><span class="sxs-lookup"><span data-stu-id="fa07e-154">Can I load my service configuration from somewhere other than the WCF application’s configuration file?</span></span>  

 <span data-ttu-id="fa07e-155">Ja. Sie müssen jedoch eine benutzerdefinierte <xref:System.ServiceModel.ServiceHost> -Klasse erstellen, die die <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> -Methode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="fa07e-155">Yes, however, you have to create a custom <xref:System.ServiceModel.ServiceHost> class that overrides the <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> method.</span></span> <span data-ttu-id="fa07e-156">In dieser Methode können Sie die Basisklasse aufrufen und zuerst die Konfiguration laden (wenn Sie die Standardkonfigurationsinformationen ebenfalls laden möchten). Sie können jedoch auch das gesamte Konfigurationsladesystem ersetzen.</span><span class="sxs-lookup"><span data-stu-id="fa07e-156">Inside that method, you can call the base to load configuration first (if you want to load the standard configuration information as well) but you can also entirely replace the configuration loading system.</span></span> <span data-ttu-id="fa07e-157">Wenn Sie die Konfiguration aus einer anderen Konfigurationsdatei als der Anwendungs Konfigurationsdatei laden möchten, müssen Sie die Konfigurationsdatei selbst analysieren und die Konfiguration laden.</span><span class="sxs-lookup"><span data-stu-id="fa07e-157">If you want to load configuration from a configuration file that is different from the application configuration file, you must parse the configuration file yourself and load the configuration.</span></span>  
  
 <span data-ttu-id="fa07e-158">Im folgenden Codebeispiel wird veranschaulicht, wie die <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> -Methode überschrieben und ein Endpunkt direkt konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="fa07e-158">The following code example shows how to override the <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> method and directly configure an endpoint.</span></span>  
  
```csharp
public class MyServiceHost : ServiceHost  
{  
    public MyServiceHost(Type serviceType, params Uri[] baseAddresses)
      : base(serviceType, baseAddresses)  
    {
        Console.WriteLine("MyServiceHost Constructor");
    }  
  
    protected override void ApplyConfiguration()  
    {  
        string straddress = GetAddress();  
        Uri address = new Uri(straddress);  
        Binding binding = GetBinding();  
        base.AddServiceEndpoint(typeof(IData), binding, address);  
    }  
  
    string GetAddress()  
    {
        return "http://MyMachine:7777/MyEndpointAddress/";
    }  
  
    Binding GetBinding()  
    {  
        WSHttpBinding binding = new WSHttpBinding();  
        binding.Security.Mode = SecurityMode.None;  
        return binding;  
    }  
}  
```  
  
<a name="BKMK_q4"></a>

## <a name="my-service-and-client-work-great-but-i-cant-get-them-to-work-when-the-client-is-on-another-computer-whats-happening"></a><span data-ttu-id="fa07e-159">Dienst und Client funktionieren hervorragend, nicht jedoch, wenn sich der Client auf einem anderen Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="fa07e-159">My service and client work great, but I can’t get them to work when the client is on another computer?</span></span> <span data-ttu-id="fa07e-160">Woran liegt das?</span><span class="sxs-lookup"><span data-stu-id="fa07e-160">What’s happening?</span></span>  

 <span data-ttu-id="fa07e-161">Je nach Ausnahme können verschiedene Probleme vorliegen:</span><span class="sxs-lookup"><span data-stu-id="fa07e-161">Depending upon the exception, there may be several issues:</span></span>  
  
- <span data-ttu-id="fa07e-162">Möglicherweise müssen Sie die Clientendpunktadressen von localhost auf den Hostnamen ändern.</span><span class="sxs-lookup"><span data-stu-id="fa07e-162">You might need to change the client endpoint addresses to the host name and not "localhost".</span></span>  
  
- <span data-ttu-id="fa07e-163">Sie müssen gegebenenfalls den Anschluss zur Anwendung öffnen.</span><span class="sxs-lookup"><span data-stu-id="fa07e-163">You might need to open the port to the application.</span></span> <span data-ttu-id="fa07e-164">Weitere Informationen finden Sie unter [Firewall Instructions](./samples/firewall-instructions.md) in den SDK-Beispielen.</span><span class="sxs-lookup"><span data-stu-id="fa07e-164">For details, see [Firewall Instructions](./samples/firewall-instructions.md) from the SDK samples.</span></span>  
  
- <span data-ttu-id="fa07e-165">Weitere mögliche Probleme finden Sie im Thema mit den Beispielen unter [Ausführen der Windows Communication Foundation Beispiele](./samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fa07e-165">For other possible issues, see the samples topic [Running the Windows Communication Foundation Samples](./samples/running-the-samples.md).</span></span>  
  
- <span data-ttu-id="fa07e-166">Wenn der Client Windows-Anmeldeinformationen verwendet und es sich bei der Ausnahme um <xref:System.ServiceModel.Security.SecurityNegotiationException>handelt, konfigurieren Sie Kerberos wie folgt.</span><span class="sxs-lookup"><span data-stu-id="fa07e-166">If your client is using Windows credentials and the exception is a <xref:System.ServiceModel.Security.SecurityNegotiationException>, configure Kerberos as follows.</span></span>  
  
    1. <span data-ttu-id="fa07e-167">Fügen Sie die Anmeldeinformationen für die Identität dem Endpunktelement in der Datei App.config des Clients hinzu:</span><span class="sxs-lookup"><span data-stu-id="fa07e-167">Add the identity credentials to the endpoint element in the client’s App.config file:</span></span>  
  
        ```xml
        <endpoint
          address="http://MyServer:8000/MyService/"
          binding="wsHttpBinding"
          bindingConfiguration="WSHttpBinding_IServiceExample"
          contract="IServiceExample"
          behaviorConfiguration="ClientCredBehavior"
          name="WSHttpBinding_IServiceExample">  
          <identity>  
            <userPrincipalName value="name@corp.contoso.com"/>  
          </identity>  
        </endpoint>  
        ```  
  
    2. <span data-ttu-id="fa07e-168">Führen Sie den selbst gehosteten Dienst unter dem System- oder dem Netzwerkdienstkonto aus.</span><span class="sxs-lookup"><span data-stu-id="fa07e-168">Run the self-hosted service under the System or NetworkService account.</span></span> <span data-ttu-id="fa07e-169">Sie können diesen Befehl ausführen, um unter dem Systemkonto ein Befehlsfenster zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="fa07e-169">You can run this command to create a command window under the System account:</span></span>  
  
        ```console
        at 12:36 /interactive "cmd.exe"  
        ```  
  
    3. <span data-ttu-id="fa07e-170">Hosten Sie den Dienst unter Internetinformationsdienste (IIS). Standardmäßig wird hier das Dienstprinzipalnamenkonto verwendet.</span><span class="sxs-lookup"><span data-stu-id="fa07e-170">Host the service under Internet Information Services (IIS), which, by default, uses the service principal name (SPN) account.</span></span>  
  
    4. <span data-ttu-id="fa07e-171">Registrieren Sie mit SetSPN einen neuen Dienstprinzipalnamen bei der Domäne.</span><span class="sxs-lookup"><span data-stu-id="fa07e-171">Register a new SPN with the domain using SetSPN.</span></span> <span data-ttu-id="fa07e-172">Um dies zu erreichen, müssen Sie ein Domänen Administrator sein.</span><span class="sxs-lookup"><span data-stu-id="fa07e-172">You need to be a domain administrator in order to do this.</span></span>  
  
 <span data-ttu-id="fa07e-173">Weitere Informationen zum Kerberos-Protokoll finden Sie unter [in WCF verwendete Sicherheitskonzepte](./feature-details/security-concepts-used-in-wcf.md) und:</span><span class="sxs-lookup"><span data-stu-id="fa07e-173">For more information about the Kerberos protocol, see [Security Concepts Used in WCF](./feature-details/security-concepts-used-in-wcf.md) and:</span></span>  
  
- [<span data-ttu-id="fa07e-174">Debuggen von Windows-Authentifizierungsfehlern</span><span class="sxs-lookup"><span data-stu-id="fa07e-174">Debugging Windows Authentication Errors</span></span>](./feature-details/debugging-windows-authentication-errors.md)  
  
- <span data-ttu-id="fa07e-175">[Registrieren von Kerberos-Dienstprinzipalnamen mithilfe von HTTP.SYS.](/previous-versions/sql/sql-server-2008-r2/ms178119(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="fa07e-175">[Registering Kerberos Service Principal Names by Using Http.sys](/previous-versions/sql/sql-server-2008-r2/ms178119(v=sql.105))</span></span>  
  
- <span data-ttu-id="fa07e-176">[Informationen zu Kerberos](/previous-versions/windows/it-pro/windows-2000-server/bb742516(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="fa07e-176">[Kerberos Explained](/previous-versions/windows/it-pro/windows-2000-server/bb742516(v=technet.10))</span></span>  
  
<a name="BKMK_q5"></a>

## <a name="when-i-throw-a-faultexceptionexception-where-the-type-is-an-exception-i-always-receive-a-general-faultexception-type-on-the-client-and-not-the-generic-type-whats-happening"></a><span data-ttu-id="fa07e-177">Wenn eine FaultException ausgelöst \<Exception> wird, bei der der Typ eine Ausnahme ist, erhalte ich immer einen allgemeinen FaultException-Typ auf dem Client, nicht den generischen Typ.</span><span class="sxs-lookup"><span data-stu-id="fa07e-177">When I throw a FaultException\<Exception> where the type is an exception, I always receive a general FaultException type on the client and not the generic type.</span></span> <span data-ttu-id="fa07e-178">Woran liegt das?</span><span class="sxs-lookup"><span data-stu-id="fa07e-178">What’s happening?</span></span>  

 <span data-ttu-id="fa07e-179">Erstellen Sie unbedingt einen eigenen benutzerdefinierten Fehlerdatentyp und deklarieren Sie ihn als Detailtyp in ihrem Fehlervertrag.</span><span class="sxs-lookup"><span data-stu-id="fa07e-179">It is highly recommended that you create your own custom error data type and declare that as the detail type in your fault contract.</span></span> <span data-ttu-id="fa07e-180">Das Problem entsteht, weil Folgendes geschieht, wenn vom System bereitgestellter Ausnahmetypen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="fa07e-180">The reason is that using system-provided exception types:</span></span>  
  
- <span data-ttu-id="fa07e-181">Eine Typabhängigkeit wird erstellt, die eine der größten Stärken dienstorientierter Anwendungen entfernt.</span><span class="sxs-lookup"><span data-stu-id="fa07e-181">Creates a type dependency that removes one of the biggest strengths of service-oriented applications.</span></span>  
  
- <span data-ttu-id="fa07e-182">Ausnahmen werden nicht notwendigerweise standardmäßig serialisiert.</span><span class="sxs-lookup"><span data-stu-id="fa07e-182">Cannot depend upon exceptions serializing in a standard way.</span></span> <span data-ttu-id="fa07e-183">Einige – wie <xref:System.Security.SecurityException>– sind vielleicht überhaupt nicht serialisierbar.</span><span class="sxs-lookup"><span data-stu-id="fa07e-183">Some—like <xref:System.Security.SecurityException>—may not be serializable at all.</span></span>  
  
- <span data-ttu-id="fa07e-184">Interne Implementierungsdetails werden für Clients verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="fa07e-184">Exposes internal implementation details to clients.</span></span> <span data-ttu-id="fa07e-185">Weitere Informationen finden Sie unter [angeben und behandeln von Fehlern in Verträgen und Diensten](specifying-and-handling-faults-in-contracts-and-services.md).</span><span class="sxs-lookup"><span data-stu-id="fa07e-185">For more information, see [Specifying and Handling Faults in Contracts and Services](specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
 <span data-ttu-id="fa07e-186">Wenn Sie eine Anwendung debuggen, können Sie jedoch mit der <xref:System.ServiceModel.Description.ServiceDebugBehavior> -Klasse Ausnahmeinformationen serialisieren und an den Client zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="fa07e-186">If you are debugging an application, however, you can serialize exception information and return it to the client by using the <xref:System.ServiceModel.Description.ServiceDebugBehavior> class.</span></span>  
  
<a name="BKMK_q6"></a>

## <a name="it-seems-like-one-way-and-request-reply-operations-return-at-roughly-the-same-speed-when-the-reply-contains-no-data-whats-happening"></a><span data-ttu-id="fa07e-187">Unidirektionale und Anforderung-Antwort-Vorgänge scheinen nahezu mit der gleichen Geschwindigkeit zurückgegeben zu werden, wenn die Antwort keine Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="fa07e-187">It seems like one-way and request-reply operations return at roughly the same speed when the reply contains no data.</span></span> <span data-ttu-id="fa07e-188">Woran liegt das?</span><span class="sxs-lookup"><span data-stu-id="fa07e-188">What's happening?</span></span>  

 <span data-ttu-id="fa07e-189">Einen Vorgang als unidirektional anzugeben, bedeutet, dass der Vorgangsvertrag lediglich eine Eingabenachricht akzeptiert und keine Ausgabenachricht zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fa07e-189">Specifying that an operation is one way means only that the operation contract accepts an input message and does not return an output message.</span></span> <span data-ttu-id="fa07e-190">In WCF werden alle Client Aufrufe zurückgegeben, wenn die ausgehenden Daten in das Netzwerk geschrieben wurden oder eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="fa07e-190">In WCF, all client invocations return when the outbound data has been written to the wire or an exception is thrown.</span></span> <span data-ttu-id="fa07e-191">Unidirektionale Vorgänge funktionieren genauso. Außerdem können sie eine Ausnahme auslösen, falls der Dienst nicht gefunden wird, oder sie können blockiert werden, falls der Dienst nicht zur Annahme der Daten aus dem Netzwerk bereit ist.</span><span class="sxs-lookup"><span data-stu-id="fa07e-191">One-way operations work the same way, and they can throw if the service cannot be located or block if the service is not prepared to accept the data from the network.</span></span> <span data-ttu-id="fa07e-192">In WCF führt dies in der Regel dazu, dass unidirektionale Aufrufe schneller an den Client zurückgegeben werden als Request-Reply; Allerdings verlangsamt jede Bedingung, die das Senden der ausgehenden Daten über das Netzwerk verlangsamt, unidirektionale Vorgänge und Anforderungs-Antwort-Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="fa07e-192">Typically in WCF, this results in one-way calls returning to the client more quickly than request-reply; but any condition that slows the sending of the outbound data over the network slows one-way operations as well as request-reply operations.</span></span> <span data-ttu-id="fa07e-193">Weitere Informationen finden Sie unter unidirektionale [Dienste](./feature-details/one-way-services.md) und [zugreifen auf Dienste mithilfe eines WCF-Clients](./feature-details/accessing-services-using-a-client.md).</span><span class="sxs-lookup"><span data-stu-id="fa07e-193">For more information, see [One-Way Services](./feature-details/one-way-services.md) and [Accessing Services Using a WCF Client](./feature-details/accessing-services-using-a-client.md).</span></span>  
  
<a name="BKMK_q77"></a>

## <a name="im-using-an-x509-certificate-with-my-service-and-i-get-a-systemsecuritycryptographycryptographicexception-whats-happening"></a><span data-ttu-id="fa07e-194">Ich verwende ein X.509-Zertifikat mit dem Dienst und erhalte eine System.Security.Cryptography.CryptographicException.</span><span class="sxs-lookup"><span data-stu-id="fa07e-194">I’m using an X.509 certificate with my service and I get a System.Security.Cryptography.CryptographicException.</span></span> <span data-ttu-id="fa07e-195">Woran liegt das?</span><span class="sxs-lookup"><span data-stu-id="fa07e-195">What’s happening?</span></span>  

 <span data-ttu-id="fa07e-196">Das Problem tritt in der Regel nach einer Änderung des Benutzerkontos auf, unter dem der IIS-Arbeitsprozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fa07e-196">This commonly occurs after changing the user account under which the IIS worker process runs.</span></span> <span data-ttu-id="fa07e-197">Wenn Sie z. b. unter Windows XP das Standardbenutzer Konto, unter dem der Aspnet_wp.exe ausgeführt wird, von ASPNET in ein benutzerdefiniertes Benutzerkonto ändern, wird dieser Fehler möglicherweise angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa07e-197">For example, in Windows XP, if you change the default user account that the Aspnet_wp.exe runs under from ASPNET to a custom user account, you may see this error.</span></span> <span data-ttu-id="fa07e-198">Bei der Verwendung eines privaten Schlüssels benötigt der entsprechende Prozess die Berechtigungen für den Zugriff auf die Datei, in der der Schlüssel gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="fa07e-198">If using a private key, the process that uses it will need to have permissions to access the file storing that key.</span></span>  
  
 <span data-ttu-id="fa07e-199">In diesem Fall müssen Sie dem Konto des Prozesses Leseberechtigungen für die Datei mit dem Schlüssel erteilen.</span><span class="sxs-lookup"><span data-stu-id="fa07e-199">If this is the case, you must give read access privileges to the process's account for the file containing the private key.</span></span> <span data-ttu-id="fa07e-200">Wenn z. B. der IIS-Arbeitsprozess unter dem Konto Bob ausgeführt wird, müssen Sie Bob den Lesezugriff auf die Datei erteilen, die den privaten Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="fa07e-200">For example, if the IIS worker process is running under the Bob account, then you will need to give Bob read access to the file containing the private key.</span></span>  
  
 <span data-ttu-id="fa07e-201">Weitere Informationen zum Zugriff auf die Datei, die den privaten Schlüssel für ein bestimmtes X. 509-Zertifikat enthält, finden Sie unter Gewusst [wie: Zugreifen auf x. 509-Zertifikate für WCF](./feature-details/how-to-make-x-509-certificates-accessible-to-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="fa07e-201">For more information about how to give the correct user account access to the file that contains the private key for a specific X.509 certificate, see [How to: Make X.509 Certificates Accessible to WCF](./feature-details/how-to-make-x-509-certificates-accessible-to-wcf.md).</span></span>  
  
<a name="BKMK_q88"></a>

## <a name="i-changed-the-first-parameter-of-an-operation-from-uppercase-to-lowercase-now-my-client-throws-an-exception-whats-happening"></a><span data-ttu-id="fa07e-202">Ich habe den ersten Parameter eines Vorgangs von Groß- in Kleinbuchstaben geändert, und der Client löst nun eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="fa07e-202">I changed the first parameter of an operation from uppercase to lowercase; now my client throws an exception.</span></span> <span data-ttu-id="fa07e-203">Woran liegt das?</span><span class="sxs-lookup"><span data-stu-id="fa07e-203">What's happening?</span></span>  

 <span data-ttu-id="fa07e-204">Die Werte der Parameternamen in der Vorgangs Signatur sind Teil des Vertrags und werden nach Groß-/Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="fa07e-204">The values of the parameter names in the operation signature are part of the contract and are case-sensitive.</span></span> <span data-ttu-id="fa07e-205">Verwenden Sie das <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType> -Attribut, wenn der lokale Parametername von den Metadaten unterschieden werden muss, die den Vorgang für Clientanwendungen beschreiben.</span><span class="sxs-lookup"><span data-stu-id="fa07e-205">Use the <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType> attribute when you need to distinguish between the local parameter name and the metadata that describes the operation for client applications.</span></span>  
  
<a name="BKMK_q99"></a>

## <a name="im-using-one-of-my-tracing-tools-and-i-get-an-endpointnotfoundexception-whats-happening"></a><span data-ttu-id="fa07e-206">Bei der Verwendung eines meiner Ablaufverfolgungstools wird EndpointNotFoundException ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="fa07e-206">I’m using one of my tracing tools and I get an EndpointNotFoundException.</span></span> <span data-ttu-id="fa07e-207">Woran liegt das?</span><span class="sxs-lookup"><span data-stu-id="fa07e-207">What’s happening?</span></span>  

 <span data-ttu-id="fa07e-208">Wenn Sie ein Ablauf Verfolgungs Tool verwenden, bei dem es sich nicht um den vom System bereitgestellten WCF-Ablauf Verfolgungs Mechanismus handelt und Sie einen erhalten, der <xref:System.ServiceModel.EndpointNotFoundException> angibt, dass ein Adress Filter Konflikt vorliegt, müssen Sie die <xref:System.ServiceModel.Description.ClientViaBehavior> -Klasse verwenden, um die Nachrichten an das Ablaufverfolgungs-Hilfsprogramm weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="fa07e-208">If you are using a tracing tool that is not the system-provided WCF tracing mechanism and you receive an <xref:System.ServiceModel.EndpointNotFoundException> that indicates that there was an address filter mismatch, you need to use the <xref:System.ServiceModel.Description.ClientViaBehavior> class to direct the messages to the tracing utility and have the utility redirect those messages to the service address.</span></span> <span data-ttu-id="fa07e-209">Die <xref:System.ServiceModel.Description.ClientViaBehavior> -Klasse ändert den Adressierungsheader `Via` und gibt die nächste Netzwerkadresse unabhängig vom endgültigen Empfänger an, der mit dem Adressierungsheader `To` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fa07e-209">The <xref:System.ServiceModel.Description.ClientViaBehavior> class alters the `Via` addressing header to specify the next network address separately from the ultimate receiver, indicated by the `To` addressing header.</span></span> <span data-ttu-id="fa07e-210">Ändern Sie dabei jedoch nicht die Endpunktadresse, die den `To` -Wert festlegt.</span><span class="sxs-lookup"><span data-stu-id="fa07e-210">When doing this, however, do not change the endpoint address, which is used to establish the `To` value.</span></span>  
  
 <span data-ttu-id="fa07e-211">Das folgende Codebeispiel zeigt eine standardmäßige Konfigurationsdatei für einen Beispielclient.</span><span class="sxs-lookup"><span data-stu-id="fa07e-211">The following code example shows an example client configuration file.</span></span>  
  
```xml
<endpoint
  address="http://localhost:8000/MyServer/"  
  binding="wsHttpBinding"  
  bindingConfiguration="WSHttpBinding_IMyContract"  
  behaviorConfiguration="MyClient"
  contract="IMyContract"
  name="WSHttpBinding_IMyContract">  
</endpoint>  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="MyClient">  
      <clientVia viaUri="http://localhost:8001/MyServer/"/>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
```  
  
<a name="BKMK_q10"></a>

## <a name="what-is-the-base-address-how-does-it-relate-to-an-endpoint-address"></a><span data-ttu-id="fa07e-212">Was ist die Basisadresse?</span><span class="sxs-lookup"><span data-stu-id="fa07e-212">What is the base address?</span></span> <span data-ttu-id="fa07e-213">Worin besteht die Beziehung zu einer Endpunktadresse?</span><span class="sxs-lookup"><span data-stu-id="fa07e-213">How does it relate to an endpoint address?</span></span>  

 <span data-ttu-id="fa07e-214">Eine Basisadresse ist die Stammadresse für eine <xref:System.ServiceModel.ServiceHost> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="fa07e-214">A base address is the root address for a <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="fa07e-215">Wenn Sie der Dienstkonfiguration eine <xref:System.ServiceModel.Description.ServiceMetadataBehavior> -Klasse hinzufügen, werden standardmäßig die WSDL (Web Services Description Language) für alle vom Host veröffentlichten Endpunkte aus der HTTP-Basisadresse und alle relativen Adressen, die für das Metadatenverhalten bereitgestellt werden, sowie "?wsdl" abgerufen.</span><span class="sxs-lookup"><span data-stu-id="fa07e-215">By default, if you add a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class into your service configuration, the Web Services Description Language (WSDL) for all endpoints the host publishes are retrieved from the HTTP base address, plus any relative address provided to the metadata behavior, plus "?wsdl".</span></span> <span data-ttu-id="fa07e-216">Wenn Sie mit ASP.net und IIS vertraut sind, ist die Basisadresse mit dem virtuellen Verzeichnis identisch.</span><span class="sxs-lookup"><span data-stu-id="fa07e-216">If you are familiar with ASP.NET and IIS, the base address is equivalent to the virtual directory.</span></span>  
  
## <a name="sharing-a-port-between-a-service-endpoint-and-a-mex-endpoint-using-the-nettcpbinding"></a><span data-ttu-id="fa07e-217">Gemeinsames Verwenden eines Ports durch einen Dienstendpunkt und einen mex-Endpunkt mithilfe der NetTcpBinding</span><span class="sxs-lookup"><span data-stu-id="fa07e-217">Sharing a port between a service endpoint and a mex endpoint using the NetTcpBinding</span></span>  

 <span data-ttu-id="fa07e-218">Wenn Sie die Basisadresse für einen Dienst als net.tcp://MyServer:8080/MyService angeben und die folgenden Endpunkte hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="fa07e-218">If you specify the base address for a service as net.tcp://MyServer:8080/MyService and add the following endpoints:</span></span>  
  
```xml  
<services>  
  <service name="Microsoft.Samples.NetTcp.CalculatorService">  
    <endpoint address="calcsvc" binding ="netTcpBinding" contract="Microsoft.Samples.NetTcp.ICalculator"/>  
    <endpoint address="mex" binding="mexTcpBinding" contract="IMetadataExchange" />  
  </service>  
</services>  
```  
  
 <span data-ttu-id="fa07e-219">Und wenn Sie eine der NetTcpBinding-Einstellungen wie im folgenden Konfigurationsausschnitt veranschaulicht ändern:</span><span class="sxs-lookup"><span data-stu-id="fa07e-219">And if you modify one of the NetTcpBinding settings as shown in the following configuration snippet:</span></span>  
  
```xml  
<bindings>  
  <netTcpBinding>  
    <binding closeTimeout="00:01:00" openTimeout="00:01:00" receiveTimeout="00:10:00" sendTimeout="00:01:00" transactionFlow="false" transferMode="Buffered" transactionProtocol="OleTransactions" hostNameComparisonMode="StrongWildcard" listenBacklog="10" maxBufferPoolSize="524288" maxBufferSize="65536" maxConnections="11" maxReceivedMessageSize="65536">  
      <readerQuotas maxDepth="32" maxStringContentLength="8192" maxArrayLength="16384" maxBytesPerRead="4096" maxNameTableCharCount="16384"/>  
      <reliableSession ordered="true" inactivityTimeout="00:10:00" enabled="false"/>  
      <security mode="Transport">  
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign"/>  
      </security>  
    </binding>  
  </netTcpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="fa07e-220">Ein Fehler ähnlich dem folgenden wird angezeigt: Unbehandelte Ausnahme: System.ServiceModel.AddressAlreadyInUseException: Für den IP-Endpunkt 0.0.0.0:9000 ist bereits ein Listener vorhanden. Sie können diesen Fehler beheben, indem Sie eine vollqualifizierte URL mit einem anderen Port für den MEX-Endpunkt angeben. Dies wird im folgenden Konfigurationsausschnitt veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="fa07e-220">You will see an error like the following: Unhandled Exception: System.ServiceModel.AddressAlreadyInUseException: There is already a listener on IP endpoint 0.0.0.0:9000 You can work around this error by specifying a fully qualified URL with a different port for the MEX endpoint as shown in the following configuration snippet:</span></span>  
  
```xml
<services>  
  <service name="Microsoft.Samples.NetTcp.CalculatorService">  
    <endpoint address="calcsvc" binding ="netTcpBinding" contract="Microsoft.Samples.NetTcp.ICalculator"/>  
    <endpoint address="net.tcp://localhost:9001/servicemodelsamples/mex" binding="mexTcpBinding" contract="IMetadataExchange" />  
  </service>  
</services>  
```  
  
<a name="BK_MK99"></a>

## <a name="when-calling-a-wcf-web-http-application-from-a-wcf-soap-application-the-service-returns-the-following-error-405-method-not-allowed"></a><span data-ttu-id="fa07e-221">Beim Aufruf einer WCF-Web HTTP-Anwendung aus einer WCF-SOAP-Anwendung gibt der Dienst die folgende Fehlermeldung zurück: 405 "Method Not Allowed"</span><span class="sxs-lookup"><span data-stu-id="fa07e-221">When calling a WCF Web HTTP application from a WCF SOAP application the service returns the following error: 405 Method Not Allowed</span></span>  

 <span data-ttu-id="fa07e-222">Durch Aufrufen einer WCF-Web-HTTP-Anwendung (ein Dienst, der <xref:System.ServiceModel.WebHttpBinding> und <xref:System.ServiceModel.Description.WebHttpBehavior> aus einem WCF-Dienst verwendet) wird möglicherweise die folgende Ausnahme generiert: ``Unhandled Exception: System.ServiceModel.FaultException`1[System.ServiceModel.ExceptionDetail]: The remote server returned an unexpected response: (405) Method Not Allowed.`` Diese Ausnahme tritt auf, weil WCF den ausgehenden <xref:System.ServiceModel.OperationContext> mit dem eingehenden überschreibt <xref:System.ServiceModel.OperationContext> .</span><span class="sxs-lookup"><span data-stu-id="fa07e-222">Calling a WCF Web HTTP application (a service that uses the <xref:System.ServiceModel.WebHttpBinding> and <xref:System.ServiceModel.Description.WebHttpBehavior>) from a WCF service may generate the following exception: ``Unhandled Exception: System.ServiceModel.FaultException`1[System.ServiceModel.ExceptionDetail]: The remote server returned an unexpected response: (405) Method Not Allowed.`` This exception occurs because WCF overwrites the outgoing <xref:System.ServiceModel.OperationContext> with the incoming <xref:System.ServiceModel.OperationContext>.</span></span> <span data-ttu-id="fa07e-223">Um dieses Problem zu beheben, erstellen Sie <xref:System.ServiceModel.OperationContextScope> im WCF-Web-HTTP-Dienst Vorgang einen.</span><span class="sxs-lookup"><span data-stu-id="fa07e-223">To solve this problem, create an <xref:System.ServiceModel.OperationContextScope> within the WCF Web HTTP service operation.</span></span> <span data-ttu-id="fa07e-224">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fa07e-224">For example:</span></span>  
  
```csharp
public string Echo(string input)  
{  
    using (new OperationContextScope(this.InnerChannel))  
    {  
        return base.Channel.Echo(input);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa07e-225">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fa07e-225">See also</span></span>

- [<span data-ttu-id="fa07e-226">Debuggen von Windows-Authentifizierungsfehlern</span><span class="sxs-lookup"><span data-stu-id="fa07e-226">Debugging Windows Authentication Errors</span></span>](./feature-details/debugging-windows-authentication-errors.md)
