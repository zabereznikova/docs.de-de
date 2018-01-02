---
title: '&lt;Netzwerk&gt; -Element (Netzwerkeinstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d3e99a10403a735383ee5e1a78c1f85ac7fd8281
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltnetworkgt-element-network-settings"></a><span data-ttu-id="3e9f5-102">&lt;Netzwerk&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="3e9f5-102">&lt;network&gt; Element (Network Settings)</span></span>
<span data-ttu-id="3e9f5-103">Konfiguriert die Netzwerkoptionen für einen externen (SMTP, Simple Mail Transport Protocol)-Server.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="3e9f5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3e9f5-104">\<configuration></span></span>  
<span data-ttu-id="3e9f5-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="3e9f5-105">\<system.net></span></span>  
<span data-ttu-id="3e9f5-106">\<MailSettings ></span><span class="sxs-lookup"><span data-stu-id="3e9f5-106">\<mailSettings></span></span>  
<span data-ttu-id="3e9f5-107">\<SMTP ></span><span class="sxs-lookup"><span data-stu-id="3e9f5-107">\<smtp></span></span>  
<span data-ttu-id="3e9f5-108">\<Netzwerk ></span><span class="sxs-lookup"><span data-stu-id="3e9f5-108">\<network></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e9f5-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="3e9f5-109">Syntax</span></span>  
  
```xml  
<network  
  clientDomain="string"   
  defaultCredentials="true|false"  
  enableSsl="true|false"  
  host="string"   
  password="string"  
  port="integer"   
  targetName="string"  
  userName="string"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e9f5-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3e9f5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3e9f5-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e9f5-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="3e9f5-112">Attributes</span></span>  
  
|<span data-ttu-id="3e9f5-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="3e9f5-113">Attribute</span></span>|<span data-ttu-id="3e9f5-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3e9f5-114">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="3e9f5-115">Gibt den Namen des Client-Domäne, in der ursprünglichen Anforderung der SMTP-Protokoll verwenden, um den SMTP-Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-115">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="3e9f5-116">Der Standardwert ist die "localhost" der Name des lokalen Computers, der die Anforderung gesendet.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-116">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="3e9f5-117">Gibt an, ob die Standardanmeldeinformationen für die Benutzer Zugriff auf die SMTP-Mailserver für SMTP-Transaktionen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-117">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="3e9f5-118">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-118">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="3e9f5-119">Gibt an, ob SSL verwendet wird, um einen SMTP-Mailserver zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-119">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="3e9f5-120">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-120">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="3e9f5-121">Gibt den Hostnamen des SMTP-Mailservers, der für SMTP-Transaktionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-121">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="3e9f5-122">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-122">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="3e9f5-123">Gibt das Kennwort für den SMTP-Server-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-123">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="3e9f5-124">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-124">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="3e9f5-125">Gibt die Portnummer für die Verbindung zum SMTP-Mailserver verwendet.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-125">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="3e9f5-126">Der Standardwert ist 25.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-126">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="3e9f5-127">Gibt an, die Service Provider (Name, SPN) für die Authentifizierung zu verwenden, bei der Verwendung des erweiterten Schutzes für SMTP-Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-127">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="3e9f5-128">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-128">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="3e9f5-129">Gibt den Benutzernamen ein, für den SMTP-Server-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-129">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="3e9f5-130">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-130">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3e9f5-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3e9f5-131">Child Elements</span></span>  
 <span data-ttu-id="3e9f5-132">Keine</span><span class="sxs-lookup"><span data-stu-id="3e9f5-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3e9f5-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3e9f5-133">Parent Elements</span></span>  
  
|<span data-ttu-id="3e9f5-134">Element</span><span class="sxs-lookup"><span data-stu-id="3e9f5-134">Element</span></span>|<span data-ttu-id="3e9f5-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3e9f5-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3e9f5-136">\<SMTP >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="3e9f5-136">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="3e9f5-137">Konfiguriert (SMTP, Simple Mail Transport Protocol) e-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-137">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e9f5-138">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3e9f5-138">Remarks</span></span>  
 <span data-ttu-id="3e9f5-139">Einige SMTP-Server erfordern, dass Sie sich an den Server vor der Verwendung authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-139">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="3e9f5-140">Wenn Sie sich unter Verwendung der Standard-Netzwerkanmeldeinformationen auf Ihrem Host authentifizieren, legen Sie möchten die `defaultCredentials` -Attribut `true`.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-140">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="3e9f5-141">Die <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, den aktuellen Wert der abzurufenden der `defaultCredentials` Attribut aus anwendbaren Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-141">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="3e9f5-142">Sie können auch die Standardauthentifizierung (Benutzername und Kennwort) selbst den SMTP-Server zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-142">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="3e9f5-143">Um diese Option verwenden zu können, müssen Sie einen gültigen Benutzernamen und ein Kennwort für den angegebenen SMTP-Server angeben.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-143">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e9f5-144">Standardauthentifizierung sendet die `userName` und `password` Werte an den Server entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-144">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="3e9f5-145">Jeder der Überwachung des Netzwerkverkehrs kann die Anmeldeinformationen anzeigen und verwenden, um mit dem Server verbinden.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-145">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="3e9f5-146">Verwenden Sie einen sichereren Authentifizierungsmechanismus, z. B. Kerberos oder NT LAN Manager (NTLM). Wenn `defaultCredentials` ist `true`, Kerberos oder NTLM verwendet, wenn der Server diese Protokolle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-146">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="3e9f5-147">Die grundlegende Authentifizierung und der Standard-Anmeldeinformationen Netzwerkoptionen schließen sich gegenseitig aus; Wenn Sie festlegen, `defaultCredentials` auf `true` und einen Benutzernamen und ein Kennwort angeben, wird die Standard-Netzwerkanmeldeinformationen verwendet, und die Standardauthentifizierung wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-147">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="3e9f5-148">Für die Standardauthentifizierung, wenn Sie angeben, eine `userName`, sollten Sie auch angeben einer `password` zur Authentifizierung selbst mit dem e-Mail-Server.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-148">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="3e9f5-149">Die <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, den aktuellen Wert der abzurufenden der `userName` Attribut aus anwendbaren Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-149">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="3e9f5-150">Die <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, den aktuellen Wert der abzurufenden der `password` Attribut aus anwendbaren Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-150">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="3e9f5-151">Ein `password` Attribut würden normalerweise nicht in Konfigurationsdateien aus Sicherheitsgründen eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-151">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="3e9f5-152">Die `clientDomain` Attribut ändert sich der Client-Domänenname, der in der ursprünglichen SMTP-Protokoll-Anforderung an einen SMTP-Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-152">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="3e9f5-153">Die `clientDomain` Attribut kann festgelegt werden, um den vollqualifizierten Domänennamen des lokalen Computers anstelle von "localhost"-Name, der standardmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-153">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="3e9f5-154">Dies bietet größere Kompatibilität mit den SMTP-Protokoll-Standards.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-154">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="3e9f5-155">Der Standardwert ist die "localhost" der Name des lokalen Computers, der die Anforderung gesendet.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-155">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="3e9f5-156">Die <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, den aktuellen Wert der abzurufenden der `clientDomain` Attribut aus anwendbaren Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-156">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="3e9f5-157">Die `targetName` Attribut wird bei Verwendung von erweiterter Schutz für die Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-157">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="3e9f5-158">Der Standardwert ist im Format "SMTPSVC /\<Host >", in denen \<Host > ist der Hostname des SMTP-Mailserver.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-158">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="3e9f5-159">Die <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, den aktuellen Wert der abzurufenden der `targetName` Attribut aus anwendbaren Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-159">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="3e9f5-160">Die `enableSsl` Attribut gibt an, ob SSL verwendet wird, um einen SMTP-Mailserver zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-160">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="3e9f5-161">Die <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> Klasse unterstützt nur die Erweiterung der SMTP-Dienst für sicheres SMTP über Transport Layer Security gemäß Definition in RFC 3207.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-161">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="3e9f5-162">In diesem Modus wird die SMTP-Sitzung beginnt, auf einen unverschlüsselten Kanal, und dann eine Befehls "STARTTLS" wird vom Client ausgegeben, mit dem Server, um zur sicheren Kommunikation mit SSL zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-162">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="3e9f5-163">Finden Sie unter RFC 3207, veröffentlicht von der Internet Engineering Task Force (IETF) Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-163">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="3e9f5-164">Eine alternative Verbindungsmethode ist, auf dem vorab eine SSL-Sitzung vor ein Protokoll hergestellt ist, die Befehle gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-164">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="3e9f5-165">Diese Verbindungsmethode wird manchmal als SMTPS bezeichnet und verwendet standardmäßig Port 465.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-165">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="3e9f5-166">Diese alternative Verbindungsmethode mit SSL wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-166">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="3e9f5-167">Die <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, den aktuellen Wert der abzurufenden der `enableSsl` Attribut aus anwendbaren Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-167">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e9f5-168">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3e9f5-168">Example</span></span>  
 <span data-ttu-id="3e9f5-169">Im folgenden Beispiel wird die entsprechenden SMTP-Parameter, um e-Mails unter Verwendung der Standard-Netzwerkanmeldeinformationen zu senden.</span><span class="sxs-lookup"><span data-stu-id="3e9f5-169">The following example specifies the appropriate SMTP parameters to send e-mail using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network">  
        <network  
          clientDomain="www.contoso.com"  
          defaultCredentials="true"  
          enableSsl="false"  
          host="mail.contoso.com"  
          port="25"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e9f5-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e9f5-170">See Also</span></span>  
 <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 [<span data-ttu-id="3e9f5-171">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="3e9f5-171">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
