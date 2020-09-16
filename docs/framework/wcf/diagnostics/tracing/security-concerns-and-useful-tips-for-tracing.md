---
title: Sicherheitsaspekte und nützliche Tipps für die Ablaufverfolgung
ms.date: 03/30/2017
ms.assetid: 88bc2880-ecb9-47cd-9816-39016a07076f
ms.openlocfilehash: 91a1b4bab3ac47f41821ad69228310c3993cf037
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555041"
---
# <a name="security-concerns-and-useful-tips-for-tracing"></a><span data-ttu-id="447e1-102">Sicherheitsaspekte und nützliche Tipps für die Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="447e1-102">Security Concerns and Useful Tips for Tracing</span></span>
<span data-ttu-id="447e1-103">Dieses Thema beschreibt, wie Sie vertrauliche Informationen davor schützen, verfügbar gemacht zu werden, sowie nützliche Tipps zur Verwendung von WebHost.</span><span class="sxs-lookup"><span data-stu-id="447e1-103">This topic describes how you can protect sensitive information from being exposed, as well as useful tips when using WebHost.</span></span>  
  
## <a name="using-a-custom-trace-listener-with-webhost"></a><span data-ttu-id="447e1-104">Verwenden eines benutzerdefinierten Ablaufverfolgungslisteners mit WebHost</span><span class="sxs-lookup"><span data-stu-id="447e1-104">Using a Custom Trace Listener with WebHost</span></span>  
 <span data-ttu-id="447e1-105">Wenn Sie einen eigenen Ablaufverfolgungslistener schreiben, sollten Sie beachten, dass Ablaufverfolgungen bei einem im Internet gehosteten Dienst verloren gehen können.</span><span class="sxs-lookup"><span data-stu-id="447e1-105">If you are writing your own trace listener, you should be aware of the possibility that traces might be lost in the case of a Web-hosted service.</span></span> <span data-ttu-id="447e1-106">Wenn WebHost zur Wiederverwendung genutzt wird, wird der Liveprozess heruntergefahren, während ein Duplikat übernimmt.</span><span class="sxs-lookup"><span data-stu-id="447e1-106">When WebHost recycles, it shuts down the live process while a duplicate takes over.</span></span> <span data-ttu-id="447e1-107">Die beiden Prozesse müssen jedoch trotzdem, abhängig vom Listenertyp, eine Zeit lang Zugriff auf dieselbe Ressource haben.</span><span class="sxs-lookup"><span data-stu-id="447e1-107">However, the two processes must still have access to the same resource for some time, which is dependent on the listener type.</span></span> <span data-ttu-id="447e1-108">In diesem Fall erstellt `XmlWriterTraceListener` eine neue Ablaufverfolgungsdatei für den zweiten Prozess, während die Windows-Ereignisablaufverfolgung mehrere Prozesse innerhalb derselben Sitzung verwaltet und Zugriff auf dieselbe Datei gewährt.</span><span class="sxs-lookup"><span data-stu-id="447e1-108">In this case, , `XmlWriterTraceListener` creates a new trace file for the second process; while Windows event tracing manages multiple processes within the same session and gives access to the same file.</span></span> <span data-ttu-id="447e1-109">Wenn Ihr Listener keine ähnlichen Funktionalitäten bereitstellt, können Ablaufverfolgungen verloren gehen, wenn die Datei durch die beiden Prozesse gesperrt wird.</span><span class="sxs-lookup"><span data-stu-id="447e1-109">If your own listener does not provide similar functionalities, traces can be lost when the file is locked up by the two processes.</span></span>  
  
 <span data-ttu-id="447e1-110">Sie müssen außerdem berücksichtigen, dass ein benutzerdefinierter Ablaufverfolgungslistener Ablaufverfolgungen und Nachrichten z. B. an eine Remotedatenbank senden kann.</span><span class="sxs-lookup"><span data-stu-id="447e1-110">You should also be aware that a custom trace listener can send traces and messages on the wire, for example, to a remote database.</span></span> <span data-ttu-id="447e1-111">Als Anwendungsbereitsteller sollten Sie benutzerdefinierte Listener mit entsprechender Zugriffssteuerung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="447e1-111">As an application deployer, you should configure custom listeners with appropriate access control.</span></span> <span data-ttu-id="447e1-112">Sie sollten außerdem eine Sicherheitskontrolle auf alle persönlichen Informationen, die am Remotespeicherort verfügbar gemacht werden können, anwenden.</span><span class="sxs-lookup"><span data-stu-id="447e1-112">You should also apply security control on any personal information that can be exposed at the remote location.</span></span>  
  
## <a name="logging-sensitive-information"></a><span data-ttu-id="447e1-113">Protokollieren vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="447e1-113">Logging Sensitive Information</span></span>  
 <span data-ttu-id="447e1-114">Ablaufverfolgungen enthalten Nachrichtenheader, wenn sich eine Nachricht im Gültigkeitsbereich befindet.</span><span class="sxs-lookup"><span data-stu-id="447e1-114">Traces contain message headers when a message is in scope.</span></span> <span data-ttu-id="447e1-115">Bei aktivierter Ablaufverfolgung sind persönliche Informationen in anwendungsspezifischen Headern, wie z. B. eine Abfragezeichenfolge, und Textdaten, wie z. B. eine Kreditkartennummer, u. U. in den Protokollen sichtbar.</span><span class="sxs-lookup"><span data-stu-id="447e1-115">When tracing is enabled, personal information in application-specific headers, such as, a query string; and body information, such as, a credit card number, can become visible in the logs.</span></span> <span data-ttu-id="447e1-116">Der Anwendungsbereitsteller ist für das Erzwingen einer Zugriffssteuerung für die Konfigurations- und Ablaufverfolgungsdateien verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="447e1-116">The application deployer is responsible for enforcing access control on the configuration and trace files.</span></span> <span data-ttu-id="447e1-117">Wenn Informationen dieser Art nicht sichtbar sein sollen, sollten Sie die Ablaufverfolgung deaktivieren, oder filtern Sie einen Teil der Daten heraus, wenn Sie die Ablaufverfolgungsprotokolle freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="447e1-117">If you do not want this kind of information to be visible, you should disable tracing, or filter out part of the data if you want to share the trace logs.</span></span>  
  
 <span data-ttu-id="447e1-118">Mithilfe der folgenden Tipps können Sie verhindern, dass der Inhalt einer Ablaufverfolgungsdatei unbeabsichtigt verfügbar gemacht wird:</span><span class="sxs-lookup"><span data-stu-id="447e1-118">The following tips can help you to prevent the content of a trace file from being exposed unintentionally:</span></span>  
  
- <span data-ttu-id="447e1-119">Stellen Sie sicher, dass die Protokolldateien durch Access Control Lists (ACL) sowohl bei WebHost als auch bei selbst gehosteten Szenarien geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="447e1-119">Ensure that the log files are protected by Access Control Lists (ACL) both in WebHost and self-host scenarios.</span></span>  
  
- <span data-ttu-id="447e1-120">Wählen Sie eine Dateierweiterung aus, die nicht leicht mit einer Webanforderung ausgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="447e1-120">Choose a file extension that cannot be easily served using a Web request.</span></span> <span data-ttu-id="447e1-121">Die Dateierweiterung .xml ist z. B. nicht sicher.</span><span class="sxs-lookup"><span data-stu-id="447e1-121">For example, the .xml file extension is not a safe choice.</span></span> <span data-ttu-id="447e1-122">Sie finden im IIS-Administratorhandbuch eine Liste aller Erweiterungen, die bereitgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="447e1-122">You can check the IIS administration guide to see a list of extensions that can be served.</span></span>  
  
- <span data-ttu-id="447e1-123">Geben Sie einen absoluten Pfad für den Protokolldateispeicherort an, der sich außerhalb des öffentlichen vroot-Verzeichnisses von WebHost befinden sollte, um einen Zugriff von externer Seite mithilfe eines Webbrowsers zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="447e1-123">Specify an absolute path for the log file location, which should be outside of the WebHost vroot public directory to prevent it from being accessed by an external party using a Web browser.</span></span>  
  
 <span data-ttu-id="447e1-124">Standardmäßig werden Schlüssel und personenbezogene Informationen (PII, personally identifiable information), wie z. B. Benutzername und Passwort, nicht in Ablaufverfolgungen und protokollierten Nachrichten protokolliert.</span><span class="sxs-lookup"><span data-stu-id="447e1-124">By default, keys and personally identifiable information (PII) such as username and password are not logged in traces and logged messages.</span></span> <span data-ttu-id="447e1-125">Ein Computeradministrator kann jedoch das `enableLoggingKnownPII`-Attribut im `machineSettings`-Element der Datei Machine.config verwenden, um Anwendungen, die auf dem Computer ausgeführt werden, zu ermöglichen, bekannte personenbezogene Informationen (PII) wie folgt zu protokollieren:</span><span class="sxs-lookup"><span data-stu-id="447e1-125">A machine administrator, however, can use the `enableLoggingKnownPII` attribute in the `machineSettings` element of the Machine.config file to permit applications running on the machine to log known personally identifiable information (PII) as follows:</span></span>  
  
```xml  
<configuration>  
   <system.ServiceModel>  
      <machineSettings enableLoggingKnownPii="Boolean"/>  
   </system.ServiceModel>  
</configuration>
```  
  
 <span data-ttu-id="447e1-126">Ein Anwendungsbereitsteller kann daraufhin das `logKnownPii`-Attribut entweder in der Datei App.config oder in der Datei Web.config verwenden, um die PII-Protokollierung wie folgt zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="447e1-126">An application deployer can then use the `logKnownPii` attribute in either the App.config or Web.config file to enable PII logging as follows:</span></span>  
  
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
  
 <span data-ttu-id="447e1-127">Nur wenn beide Einstellungen auf `true` festgelegt sind, wird die PII-Protokollierung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="447e1-127">Only when both settings are `true` is PII logging enabled.</span></span> <span data-ttu-id="447e1-128">Die Kombination von zwei Schaltern ermöglicht, bekannte PII für jede Anwendung zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="447e1-128">The combination of two switches allows the flexibility to log known PII for each application.</span></span>  
  
 <span data-ttu-id="447e1-129">Sie müssen berücksichtigen, dass nur die Attribute der ersten Quelle gelesen werden, wenn Sie zwei oder mehr benutzerdefinierte Quellen in einer Konfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="447e1-129">You should be aware that if you specify two or more custom sources in a configuration file, only the attributes of the first source are read.</span></span> <span data-ttu-id="447e1-130">Die anderen werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="447e1-130">The others are ignored.</span></span> <span data-ttu-id="447e1-131">Dies bedeutet, dass PII für die folgende Datei App.config nicht für beide Quellen protokolliert wird, obwohl die PII-Protokollierung explizit für die zweite Quelle aktiviert worden ist.</span><span class="sxs-lookup"><span data-stu-id="447e1-131">This means that, for the following App.config, file, PII is not logged for both sources even though PII logging is explicitly enabled for the second source.</span></span>  
  
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
  
 <span data-ttu-id="447e1-132">Wenn das `<machineSettings enableLoggingKnownPii="Boolean"/>`-Element außerhalb der Datei Machine.config vorhanden ist, löst das System einen <xref:System.Configuration.ConfigurationErrorsException> aus.</span><span class="sxs-lookup"><span data-stu-id="447e1-132">If the `<machineSettings enableLoggingKnownPii="Boolean"/>` element exists outside the Machine.config file, the system throws a <xref:System.Configuration.ConfigurationErrorsException>.</span></span>  
  
 <span data-ttu-id="447e1-133">Die Änderungen sind nur wirksam, wenn die Anwendung gestartet oder neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="447e1-133">The changes are effective only when the application starts or restarts.</span></span> <span data-ttu-id="447e1-134">Ein Ereignis wird beim Start protokolliert, wenn beide Attribute auf `true` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="447e1-134">An event is logged at startup when both attributes are set to `true`.</span></span> <span data-ttu-id="447e1-135">Ein Ereignis wird außerdem protokolliert, wenn `logKnownPii` auf `true` festgelegt wird, `enableLoggingKnownPii` jedoch `false` ist.</span><span class="sxs-lookup"><span data-stu-id="447e1-135">An event is also logged if `logKnownPii` is set to `true` but `enableLoggingKnownPii` is `false`.</span></span>  
  
 <span data-ttu-id="447e1-136">Weitere Informationen zur PII-Protokollierung finden [Sie unter PII Security Lock](../../samples/pii-security-lockdown.md) Sample.</span><span class="sxs-lookup"><span data-stu-id="447e1-136">For more information on PII logging, see [PII Security Lockdown](../../samples/pii-security-lockdown.md) sample.</span></span>  
  
 <span data-ttu-id="447e1-137">Der Computeradministrator und der Anwendungsbereitsteller sollten diese beiden Schalter mit großer Vorsicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="447e1-137">The machine administrator and application deployer should exercise extreme caution when using these two switches.</span></span> <span data-ttu-id="447e1-138">Wenn die PII-Protokollierung aktiviert ist, werden Sicherheitsschlüssel und PII protokolliert.</span><span class="sxs-lookup"><span data-stu-id="447e1-138">If PII logging is enabled, security keys and PII are logged.</span></span> <span data-ttu-id="447e1-139">Wenn sie deaktiviert ist, werden vertrauliche und anwendungsspezifische Daten immer noch in Nachrichtenheadern und -texten protokolliert.</span><span class="sxs-lookup"><span data-stu-id="447e1-139">If it is disabled, sensitive and application-specific data is still logged in message headers and bodies.</span></span> <span data-ttu-id="447e1-140">Eine ausführlichere Erläuterung zum Datenschutz und zum Schutz von PII vor dem verfügbar machen finden Sie unter [Benutzerdaten Schutz](/previous-versions/dotnet/articles/aa480490(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="447e1-140">For a more thorough discussion on privacy and protecting PII from being exposed, see [User Privacy](/previous-versions/dotnet/articles/aa480490(v=msdn.10)).</span></span>  
  
 <span data-ttu-id="447e1-141">Außerdem wird die IP-Adresse des Nachrichtenabsenders einmal pro Verbindung bei verbindungsorientierten Transporten und einmal pro Nachricht bei anderen Übertragungen protokolliert.</span><span class="sxs-lookup"><span data-stu-id="447e1-141">In addition, the IP address of the message sender is logged once per connection for connection-oriented transports, and once per message sent otherwise.</span></span> <span data-ttu-id="447e1-142">Dies geschieht ohne Bestätigung durch den Absender.</span><span class="sxs-lookup"><span data-stu-id="447e1-142">This is done without the consent of the sender.</span></span> <span data-ttu-id="447e1-143">Diese Protokollierung erfolgt jedoch nur auf den Ablaufverfolgungsebenen "Information" oder "Ausführlich", die nicht die Standard- oder empfohlenen Ablaufverfolgungsebenen für die Produktion sind, außer für das Livedebuggen.</span><span class="sxs-lookup"><span data-stu-id="447e1-143">However, this logging only occurs at the Information or Verbose tracing levels, which are not the default or recommended tracing levels in production, except for live debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="447e1-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="447e1-144">See also</span></span>

- [<span data-ttu-id="447e1-145">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="447e1-145">Tracing</span></span>](index.md)
