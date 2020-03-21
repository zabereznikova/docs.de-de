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
ms.openlocfilehash: f7cfcc3b9d5a717c23175cd15aa48ae97c828e57
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154815"
---
# <a name="network-element-network-settings"></a><span data-ttu-id="d914a-102">\<Netzwerk->-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="d914a-102">\<network> Element (Network Settings)</span></span>
<span data-ttu-id="d914a-103">Konfiguriert die Netzwerkoptionen für einen externen SMTP-Server (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="d914a-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  

<span data-ttu-id="d914a-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d914a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d914a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d914a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="d914a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d914a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="d914a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d914a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>\
<span data-ttu-id="d914a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Netzwerk->**</span><span class="sxs-lookup"><span data-stu-id="d914a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<network>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d914a-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="d914a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d914a-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d914a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d914a-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d914a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d914a-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="d914a-112">Attributes</span></span>  
  
|<span data-ttu-id="d914a-113">attribute</span><span class="sxs-lookup"><span data-stu-id="d914a-113">Attribute</span></span>|<span data-ttu-id="d914a-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d914a-114">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="d914a-115">Gibt den Clientdomänennamen an, der in der ursprünglichen SMTP-Protokollanforderung zum Herstellen einer Verbindung mit dem SMTP-Mailserver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d914a-115">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="d914a-116">Der Standardwert ist der Name des lokalen Hosts des lokalen Computers, der die Anforderung sendet.</span><span class="sxs-lookup"><span data-stu-id="d914a-116">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="d914a-117">Gibt an, ob die Standardbenutzeranmeldeinformationen für den Zugriff auf den SMTP-Mailserver für SMTP-Transaktionen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d914a-117">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="d914a-118">Standardwert: `false`.</span><span class="sxs-lookup"><span data-stu-id="d914a-118">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="d914a-119">Gibt an, ob SSL für den Zugriff auf einen SMTP-Mailserver verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d914a-119">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="d914a-120">Standardwert: `false`.</span><span class="sxs-lookup"><span data-stu-id="d914a-120">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="d914a-121">Gibt den Hostnamen des SMTP-Mailservers an, der für SMTP-Transaktionen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d914a-121">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="d914a-122">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="d914a-122">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="d914a-123">Gibt das Kennwort an, das für die Authentifizierung beim SMTP-Mailserver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d914a-123">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="d914a-124">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="d914a-124">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="d914a-125">Gibt die Portnummer an, die zum Herstellen einer Verbindung mit dem SMTP-Mailserver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d914a-125">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="d914a-126">Der Standardwert ist 25.</span><span class="sxs-lookup"><span data-stu-id="d914a-126">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="d914a-127">Gibt den Dienstanbieternamen (Service Provider Name, SPN) an, der für die Authentifizierung verwendet werden soll, wenn er erweiterten Schutz für SMTP-Transaktionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d914a-127">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="d914a-128">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="d914a-128">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="d914a-129">Gibt den Benutzernamen an, der für die Authentifizierung auf dem SMTP-Mailserver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d914a-129">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="d914a-130">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="d914a-130">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d914a-131">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d914a-131">Child Elements</span></span>  
 <span data-ttu-id="d914a-132">Keine.</span><span class="sxs-lookup"><span data-stu-id="d914a-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d914a-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d914a-133">Parent Elements</span></span>  
  
|<span data-ttu-id="d914a-134">Element</span><span class="sxs-lookup"><span data-stu-id="d914a-134">Element</span></span>|<span data-ttu-id="d914a-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d914a-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d914a-136">\<smtp> Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="d914a-136">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="d914a-137">Konfiguriert SMTP-E-Mail-Versandoptionen (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="d914a-137">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d914a-138">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d914a-138">Remarks</span></span>  
 <span data-ttu-id="d914a-139">Einige SMTP-Server erfordern, dass Sie sich vor der Verwendung beim Server authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="d914a-139">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="d914a-140">Wenn Sie sich mit den Standardnetzwerkanmeldeinformationen auf Ihrem `defaultCredentials` Host `true`authentifizieren möchten, legen Sie das Attribut auf fest.</span><span class="sxs-lookup"><span data-stu-id="d914a-140">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="d914a-141">Die <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um `defaultCredentials` den aktuellen Wert des Attributs aus den entsprechenden Konfigurationsdateien abzubekommen.</span><span class="sxs-lookup"><span data-stu-id="d914a-141">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="d914a-142">Sie können auch die Standardauthentifizierung (Benutzername und Kennwort) verwenden, um sich beim SMTP-Server zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="d914a-142">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="d914a-143">Um diese Option verwenden zu können, müssen Sie einen gültigen Benutzernamen und ein Kennwort für den angegebenen SMTP-Server angeben.</span><span class="sxs-lookup"><span data-stu-id="d914a-143">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d914a-144">Die Standardauthentifizierung sendet die `userName` und `password` die Werte unverschlüsselt an den Server.</span><span class="sxs-lookup"><span data-stu-id="d914a-144">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="d914a-145">Jeder, der den Netzwerkverkehr überwacht, kann Ihre Anmeldeinformationen anzeigen und diese verwenden, um eine Verbindung mit dem Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d914a-145">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="d914a-146">Sie sollten einen sichereren Authentifizierungsmechanismus verwenden, z. B. Kerberos oder NT LAN Manager (NTLM).) Falls `defaultCredentials` `true`vorhanden , wird Kerberos oder NTLM verwendet, wenn der Server diese Protokolle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d914a-146">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="d914a-147">Die Standardauthentifizierungs- und Standardoptionen für Netzwerkanmeldeinformationen schließen sich gegenseitig aus. Wenn Sie `defaultCredentials` `true` einen Benutzernamen und ein Kennwort festlegen und angeben, werden die Standardnetzwerkanmeldeinformationen verwendet, und die grundlegenden Authentifizierungsdaten werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d914a-147">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="d914a-148">Für die Standardauthentifizierung, wenn Sie `userName` `password` eine angeben, sollten Sie auch eine angeben, um sich selbst beim Mailserver authentifizierung zu machen.</span><span class="sxs-lookup"><span data-stu-id="d914a-148">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="d914a-149">Die <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um `userName` den aktuellen Wert des Attributs aus den entsprechenden Konfigurationsdateien abzubekommen.</span><span class="sxs-lookup"><span data-stu-id="d914a-149">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="d914a-150">Die <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um `password` den aktuellen Wert des Attributs aus den entsprechenden Konfigurationsdateien abzubekommen.</span><span class="sxs-lookup"><span data-stu-id="d914a-150">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="d914a-151">Ein `password` Attribut wird normalerweise aus Sicherheitsgründen nicht in Konfigurationsdateien eingegeben.</span><span class="sxs-lookup"><span data-stu-id="d914a-151">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="d914a-152">Das `clientDomain` Attribut ändert den Clientdomänennamen, der in der ursprünglichen SMTP-Protokollanforderung verwendet wird, in einen SMTP-Server.</span><span class="sxs-lookup"><span data-stu-id="d914a-152">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="d914a-153">Das `clientDomain` Attribut kann auf den vollqualifizierten Domänennamen des lokalen Computers festgelegt werden und nicht auf den Localhost-Namen, der standardmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d914a-153">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="d914a-154">Dies ermöglicht eine bessere Einhaltung der SMTP-Protokollstandards.</span><span class="sxs-lookup"><span data-stu-id="d914a-154">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="d914a-155">Der Standardwert ist der Name des lokalen Hosts des lokalen Computers, der die Anforderung sendet.</span><span class="sxs-lookup"><span data-stu-id="d914a-155">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="d914a-156">Die <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um `clientDomain` den aktuellen Wert des Attributs aus den entsprechenden Konfigurationsdateien abzubekommen.</span><span class="sxs-lookup"><span data-stu-id="d914a-156">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="d914a-157">Das `targetName` Attribut wird für die Authentifizierung verwendet, wenn erweiterter Schutz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d914a-157">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="d914a-158">Der Standardwert ist das Formular\<"SMTPSVC/ \<host>", wobei Host> der Hostname des SMTP-Mailservers ist.</span><span class="sxs-lookup"><span data-stu-id="d914a-158">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="d914a-159">Die <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um `targetName` den aktuellen Wert des Attributs aus den entsprechenden Konfigurationsdateien abzubekommen.</span><span class="sxs-lookup"><span data-stu-id="d914a-159">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="d914a-160">Das `enableSsl` Attribut gibt an, ob SSL für den Zugriff auf einen SMTP-Mailserver verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d914a-160">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="d914a-161">Die <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> Klasse unterstützt nur die SMTP-Diensterweiterung für Secure SMTP over Transport Layer Security, wie in RFC 3207 definiert.</span><span class="sxs-lookup"><span data-stu-id="d914a-161">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="d914a-162">In diesem Modus beginnt die SMTP-Sitzung auf einem unverschlüsselten Kanal, dann wird vom Client ein STARTTLS-Befehl an den Server ausgegeben, um die sichere Kommunikation über SSL zu sichern.</span><span class="sxs-lookup"><span data-stu-id="d914a-162">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="d914a-163">Weitere Informationen finden Sie unter RFC 3207, veröffentlicht von der Internet Engineering Task Force (IETF).</span><span class="sxs-lookup"><span data-stu-id="d914a-163">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="d914a-164">Eine alternative Verbindungsmethode ist, wenn eine SSL-Sitzung im Voraus eingerichtet wird, bevor Protokollbefehle gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="d914a-164">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="d914a-165">Diese Verbindungsmethode wird manchmal SMTPS genannt und verwendet standardmäßig Port 465.</span><span class="sxs-lookup"><span data-stu-id="d914a-165">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="d914a-166">Diese alternative Verbindungsmethode mit SSL wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d914a-166">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="d914a-167">Die <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um `enableSsl` den aktuellen Wert des Attributs aus den entsprechenden Konfigurationsdateien abzubekommen.</span><span class="sxs-lookup"><span data-stu-id="d914a-167">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d914a-168">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d914a-168">Example</span></span>  
 <span data-ttu-id="d914a-169">Im folgenden Beispiel werden die entsprechenden SMTP-Parameter zum Senden von E-Mails mit den Standardnetzwerkanmeldeinformationen angegeben.</span><span class="sxs-lookup"><span data-stu-id="d914a-169">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d914a-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d914a-170">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="d914a-171">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="d914a-171">Network Settings Schema</span></span>](index.md)
