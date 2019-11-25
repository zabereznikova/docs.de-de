---
title: <network>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: f7b73a725cd406df9ce41e2c4522850ce974022f
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089218"
---
# <a name="network-element-network-settings"></a><span data-ttu-id="25dcf-102">\<Netzwerk >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="25dcf-102">\<network> Element (Network Settings)</span></span>
<span data-ttu-id="25dcf-103">Konfiguriert die Netzwerkoptionen für einen externen SMTP-Server (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="25dcf-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  

<span data-ttu-id="25dcf-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="25dcf-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="25dcf-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="25dcf-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="25dcf-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<mailSettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="25dcf-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="25dcf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](smtp-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="25dcf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>\
<span data-ttu-id="25dcf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Netzwerk >**</span><span class="sxs-lookup"><span data-stu-id="25dcf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<network>**</span></span>

## <a name="syntax"></a><span data-ttu-id="25dcf-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="25dcf-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25dcf-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="25dcf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="25dcf-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="25dcf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25dcf-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="25dcf-112">Attributes</span></span>  
  
|<span data-ttu-id="25dcf-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="25dcf-113">Attribute</span></span>|<span data-ttu-id="25dcf-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25dcf-114">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="25dcf-115">Gibt den Client Domänen Namen an, der in der ursprünglichen SMTP-Protokoll Anforderung zum Herstellen einer Verbindung mit dem SMTP-Mailserver verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="25dcf-115">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="25dcf-116">Der Standardwert ist der localhost-Name des lokalen Computers, der die Anforderung sendet.</span><span class="sxs-lookup"><span data-stu-id="25dcf-116">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="25dcf-117">Gibt an, ob die Standardbenutzer Anmelde Informationen für den Zugriff auf den SMTP-Mailserver für SMTP-Transaktionen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="25dcf-117">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="25dcf-118">Der Standardwert ist `false`sein.</span><span class="sxs-lookup"><span data-stu-id="25dcf-118">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="25dcf-119">Gibt an, ob für den Zugriff auf einen SMTP-Mailserver SSL verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="25dcf-119">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="25dcf-120">Der Standardwert ist `false`sein.</span><span class="sxs-lookup"><span data-stu-id="25dcf-120">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="25dcf-121">Gibt den Hostnamen des SMTP-Mailservers an, der für SMTP-Transaktionen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="25dcf-121">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="25dcf-122">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="25dcf-122">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="25dcf-123">Gibt das Kennwort an, das für die Authentifizierung beim SMTP-Mailserver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="25dcf-123">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="25dcf-124">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="25dcf-124">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="25dcf-125">Gibt die Portnummer an, die für die Verbindung mit dem SMTP-Mailserver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="25dcf-125">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="25dcf-126">Der Standardwert ist 25.</span><span class="sxs-lookup"><span data-stu-id="25dcf-126">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="25dcf-127">Gibt den Dienstanbieter Namen (Service Provider Name, SPN) für die Authentifizierung an, wenn der erweiterte Schutz für SMTP-Transaktionen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="25dcf-127">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="25dcf-128">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="25dcf-128">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="25dcf-129">Gibt den Benutzernamen an, der für die Authentifizierung beim SMTP-Mailserver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="25dcf-129">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="25dcf-130">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="25dcf-130">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="25dcf-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="25dcf-131">Child Elements</span></span>  
 <span data-ttu-id="25dcf-132">Keine</span><span class="sxs-lookup"><span data-stu-id="25dcf-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="25dcf-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="25dcf-133">Parent Elements</span></span>  
  
|<span data-ttu-id="25dcf-134">Element</span><span class="sxs-lookup"><span data-stu-id="25dcf-134">Element</span></span>|<span data-ttu-id="25dcf-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25dcf-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25dcf-136">\<SMTP->-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="25dcf-136">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="25dcf-137">Konfiguriert SMTP (Simple Mail Transport Protocol)-e-Mail-Sende Optionen.</span><span class="sxs-lookup"><span data-stu-id="25dcf-137">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25dcf-138">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25dcf-138">Remarks</span></span>  
 <span data-ttu-id="25dcf-139">Einige SMTP-Server erfordern, dass Sie sich vor der Verwendung beim Server authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="25dcf-139">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="25dcf-140">Wenn Sie sich mit den standardmäßigen Netzwerk Anmelde Informationen auf Ihrem Host authentifizieren möchten, legen Sie das `defaultCredentials`-Attribut auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="25dcf-140">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="25dcf-141">Die <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType>-Eigenschaft kann verwendet werden, um den aktuellen Wert des `defaultCredentials` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="25dcf-141">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="25dcf-142">Sie können auch die Standard Authentifizierung (Benutzername und Kennwort) verwenden, um sich beim SMTP-Server zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="25dcf-142">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="25dcf-143">Um diese Option verwenden zu können, müssen Sie einen gültigen Benutzernamen und ein Kennwort für den angegebenen SMTP-Server angeben.</span><span class="sxs-lookup"><span data-stu-id="25dcf-143">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="25dcf-144">Bei der Standard Authentifizierung werden die `userName`-und `password` Werte unverschlüsselt an den Server gesendet.</span><span class="sxs-lookup"><span data-stu-id="25dcf-144">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="25dcf-145">Personen, die den Netzwerk Datenverkehr überwachen, können Ihre Anmelde Informationen anzeigen und zum Herstellen der Verbindung mit dem Server verwenden</span><span class="sxs-lookup"><span data-stu-id="25dcf-145">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="25dcf-146">Sie sollten die Verwendung eines sichereren Authentifizierungsmechanismus in Erwägung gezogen werden, z. b. Kerberos oder NT-LAN-Manager (NTLM). Wenn `defaultCredentials` `true`ist, wird Kerberos oder NTLM verwendet, wenn der Server diese Protokolle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25dcf-146">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="25dcf-147">Die Optionen Standard Authentifizierung und Standard-Netzwerk Anmelde Informationen schließen sich gegenseitig aus. Wenn Sie `defaultCredentials` auf `true` festlegen und einen Benutzernamen und ein Kennwort angeben, werden die standardmäßigen Netzwerk Anmelde Informationen verwendet, und die grundlegenden Authentifizierungsdaten werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="25dcf-147">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="25dcf-148">Bei der Standard `userName`Authentifizierung sollten Sie auch eine `password` angeben, um sich selbst beim Mailserver zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="25dcf-148">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="25dcf-149">Die <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType>-Eigenschaft kann verwendet werden, um den aktuellen Wert des `userName` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="25dcf-149">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="25dcf-150">Die <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType>-Eigenschaft kann verwendet werden, um den aktuellen Wert des `password` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="25dcf-150">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="25dcf-151">Aus Sicherheitsgründen wird in der Regel kein `password` Attribut in Konfigurationsdateien eingegeben.</span><span class="sxs-lookup"><span data-stu-id="25dcf-151">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="25dcf-152">Mit dem `clientDomain`-Attribut wird der in der ursprünglichen SMTP-Protokoll Anforderung verwendete Client Domänen Name auf einen SMTP-Server geändert.</span><span class="sxs-lookup"><span data-stu-id="25dcf-152">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="25dcf-153">Das `clientDomain`-Attribut kann auf den voll qualifizierten Domänen Namen des lokalen Computers und nicht auf den standardmäßig verwendeten localhost-Namen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="25dcf-153">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="25dcf-154">Dies ermöglicht eine bessere Konformität mit den SMTP-Protokollstandards.</span><span class="sxs-lookup"><span data-stu-id="25dcf-154">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="25dcf-155">Der Standardwert ist der localhost-Name des lokalen Computers, der die Anforderung sendet.</span><span class="sxs-lookup"><span data-stu-id="25dcf-155">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="25dcf-156">Die <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType>-Eigenschaft kann verwendet werden, um den aktuellen Wert des `clientDomain` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="25dcf-156">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="25dcf-157">Das `targetName`-Attribut wird für die Authentifizierung verwendet, wenn der erweiterte Schutz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="25dcf-157">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="25dcf-158">Der Standardwert ist die Form "SmtpSvc/\<Host >", wobei \<Host > der Hostname des SMTP-Mailservers ist.</span><span class="sxs-lookup"><span data-stu-id="25dcf-158">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="25dcf-159">Die <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType>-Eigenschaft kann verwendet werden, um den aktuellen Wert des `targetName` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="25dcf-159">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="25dcf-160">Das `enableSsl`-Attribut gibt an, ob für den Zugriff auf einen SMTP-Mailserver SSL verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="25dcf-160">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="25dcf-161">Die <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>-Klasse unterstützt nur die SMTP-Dienst Erweiterung für Secure SMTP over Transport Layer Security, wie in RFC 3207 definiert.</span><span class="sxs-lookup"><span data-stu-id="25dcf-161">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="25dcf-162">In diesem Modus beginnt die SMTP-Sitzung auf einem unverschlüsselten Kanal. Anschließend wird vom Client ein STARTTLS-Befehl an den Server ausgegeben, um zur sicheren Kommunikation über SSL zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="25dcf-162">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="25dcf-163">Weitere Informationen finden Sie unter RFC 3207, veröffentlicht von der Internet Engineering Task Force (IETF).</span><span class="sxs-lookup"><span data-stu-id="25dcf-163">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="25dcf-164">Eine Alternative Verbindungsmethode besteht darin, dass vor dem Senden von Protokoll Befehlen eine SSL-Sitzung eingerichtet wird.</span><span class="sxs-lookup"><span data-stu-id="25dcf-164">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="25dcf-165">Diese Verbindungsmethode wird manchmal als SMTPS bezeichnet und verwendet standardmäßig Port 465.</span><span class="sxs-lookup"><span data-stu-id="25dcf-165">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="25dcf-166">Diese Alternative Verbindungsmethode mithilfe von SSL wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25dcf-166">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="25dcf-167">Die <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType>-Eigenschaft kann verwendet werden, um den aktuellen Wert des `enableSsl` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="25dcf-167">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25dcf-168">Beispiel</span><span class="sxs-lookup"><span data-stu-id="25dcf-168">Example</span></span>  
 <span data-ttu-id="25dcf-169">Im folgenden Beispiel werden die entsprechenden SMTP-Parameter zum Senden von e-Mails mit den standardmäßigen Netzwerk Anmelde Informationen angegeben.</span><span class="sxs-lookup"><span data-stu-id="25dcf-169">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
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
  
## <a name="see-also"></a><span data-ttu-id="25dcf-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25dcf-170">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="25dcf-171">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="25dcf-171">Network Settings Schema</span></span>](index.md)
