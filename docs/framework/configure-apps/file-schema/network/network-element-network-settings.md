---
title: <network>-Element (Netzwerkeinstellungen)
description: <network>Mit dem Netzwerk Einstellungs Element werden die Netzwerkoptionen für externe SMTP-Serveroptionen in der .NET Framework konfiguriert.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: 36857e63871b4672df349934594f0887a042609e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504549"
---
# <a name="network-element-network-settings"></a><span data-ttu-id="2d5b5-103">\<network>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="2d5b5-103">\<network> Element (Network Settings)</span></span>
<span data-ttu-id="2d5b5-104">Konfiguriert die Netzwerkoptionen für einen externen SMTP-Server (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="2d5b5-104">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<network>**

## <a name="syntax"></a><span data-ttu-id="2d5b5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d5b5-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d5b5-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2d5b5-106">Attributes and Elements</span></span>  
 <span data-ttu-id="2d5b5-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d5b5-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="2d5b5-108">Attributes</span></span>  
  
|<span data-ttu-id="2d5b5-109">attribute</span><span class="sxs-lookup"><span data-stu-id="2d5b5-109">Attribute</span></span>|<span data-ttu-id="2d5b5-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2d5b5-110">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="2d5b5-111">Gibt den Client Domänen Namen an, der in der ursprünglichen SMTP-Protokoll Anforderung zum Herstellen einer Verbindung mit dem SMTP-Mailserver verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-111">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="2d5b5-112">Der Standardwert ist der localhost-Name des lokalen Computers, der die Anforderung sendet.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-112">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="2d5b5-113">Gibt an, ob die Standardbenutzer Anmelde Informationen für den Zugriff auf den SMTP-Mailserver für SMTP-Transaktionen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-113">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="2d5b5-114">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-114">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="2d5b5-115">Gibt an, ob für den Zugriff auf einen SMTP-Mailserver SSL verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-115">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="2d5b5-116">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-116">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="2d5b5-117">Gibt den Hostnamen des SMTP-Mailservers an, der für SMTP-Transaktionen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-117">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="2d5b5-118">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-118">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="2d5b5-119">Gibt das Kennwort an, das für die Authentifizierung beim SMTP-Mailserver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-119">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="2d5b5-120">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-120">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="2d5b5-121">Gibt die Portnummer an, die für die Verbindung mit dem SMTP-Mailserver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-121">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="2d5b5-122">Der Standardwert ist 25.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-122">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="2d5b5-123">Gibt den Dienstanbieter Namen (Service Provider Name, SPN) für die Authentifizierung an, wenn der erweiterte Schutz für SMTP-Transaktionen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-123">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="2d5b5-124">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-124">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="2d5b5-125">Gibt den Benutzernamen an, der für die Authentifizierung beim SMTP-Mailserver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-125">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="2d5b5-126">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-126">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d5b5-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2d5b5-127">Child Elements</span></span>  
 <span data-ttu-id="2d5b5-128">Keine</span><span class="sxs-lookup"><span data-stu-id="2d5b5-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d5b5-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2d5b5-129">Parent Elements</span></span>  
  
|<span data-ttu-id="2d5b5-130">Element</span><span class="sxs-lookup"><span data-stu-id="2d5b5-130">Element</span></span>|<span data-ttu-id="2d5b5-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d5b5-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d5b5-132">\<smtp>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="2d5b5-132">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="2d5b5-133">Konfiguriert SMTP (Simple Mail Transport Protocol)-e-Mail-Sende Optionen.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-133">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d5b5-134">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2d5b5-134">Remarks</span></span>  
 <span data-ttu-id="2d5b5-135">Einige SMTP-Server erfordern, dass Sie sich vor der Verwendung beim Server authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-135">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="2d5b5-136">Wenn Sie sich mit den standardmäßigen Netzwerk Anmelde Informationen auf dem Host authentifizieren möchten, legen Sie das- `defaultCredentials` Attribut auf fest `true` .</span><span class="sxs-lookup"><span data-stu-id="2d5b5-136">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="2d5b5-137">Die- <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert des `defaultCredentials` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-137">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="2d5b5-138">Sie können auch die Standard Authentifizierung (Benutzername und Kennwort) verwenden, um sich beim SMTP-Server zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-138">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="2d5b5-139">Um diese Option verwenden zu können, müssen Sie einen gültigen Benutzernamen und ein Kennwort für den angegebenen SMTP-Server angeben.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-139">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d5b5-140">Bei der Standard Authentifizierung werden die `userName` `password` Werte und unverschlüsselt an den Server gesendet.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-140">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="2d5b5-141">Personen, die den Netzwerk Datenverkehr überwachen, können Ihre Anmelde Informationen anzeigen und zum Herstellen der Verbindung mit dem Server verwenden</span><span class="sxs-lookup"><span data-stu-id="2d5b5-141">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="2d5b5-142">Sie sollten die Verwendung eines sichereren Authentifizierungsmechanismus in Erwägung gezogen werden, z. b. Kerberos oder NT-LAN-Manager (NTLM). Wenn `defaultCredentials` `true` den Wert hat, wird Kerberos oder NTLM verwendet, wenn der Server diese Protokolle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-142">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="2d5b5-143">Die Optionen Standard Authentifizierung und Standard-Netzwerk Anmelde Informationen schließen sich gegenseitig aus. Wenn Sie `defaultCredentials` auf festlegen `true` und einen Benutzernamen und ein Kennwort angeben, werden die standardmäßigen Netzwerk Anmelde Informationen verwendet, und die grundlegenden Authentifizierungsdaten werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-143">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="2d5b5-144">Bei der Standard Authentifizierung `userName` sollten Sie auch einen angeben, `password` um sich selbst beim Mailserver zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-144">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="2d5b5-145">Die- <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert des `userName` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-145">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="2d5b5-146">Die- <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert des `password` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-146">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="2d5b5-147">Ein- `password` Attribut wird aus Sicherheitsgründen normalerweise nicht in Konfigurationsdateien eingegeben.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-147">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="2d5b5-148">Das- `clientDomain` Attribut ändert den Client Domänen Namen, der in der ursprünglichen SMTP-Protokoll Anforderung verwendet wird, an einen SMTP-Server.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-148">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="2d5b5-149">Das- `clientDomain` Attribut kann auf den voll qualifizierten Domänen Namen des lokalen Computers und nicht auf den standardmäßig verwendeten localhost-Namen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-149">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="2d5b5-150">Dies ermöglicht eine bessere Konformität mit den SMTP-Protokollstandards.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-150">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="2d5b5-151">Der Standardwert ist der localhost-Name des lokalen Computers, der die Anforderung sendet.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-151">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="2d5b5-152">Die- <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert des `clientDomain` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-152">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="2d5b5-153">Das- `targetName` Attribut wird für die Authentifizierung verwendet, wenn der erweiterte Schutz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-153">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="2d5b5-154">Der Standardwert ist "SmtpSvc/ \<host> ", wobei \<host> der Hostname des SMTP-Mailservers ist.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-154">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="2d5b5-155">Die- <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert des `targetName` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-155">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="2d5b5-156">Das- `enableSsl` Attribut gibt an, ob für den Zugriff auf einen SMTP-Mailserver SSL verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-156">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="2d5b5-157">Die- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> Klasse unterstützt nur die SMTP-Dienst Erweiterung für Secure SMTP over Transport Layer Security, wie in RFC 3207 definiert.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-157">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="2d5b5-158">In diesem Modus beginnt die SMTP-Sitzung auf einem unverschlüsselten Kanal. Anschließend wird vom Client ein STARTTLS-Befehl an den Server ausgegeben, um zur sicheren Kommunikation über SSL zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-158">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="2d5b5-159">Weitere Informationen finden Sie unter RFC 3207, veröffentlicht von der Internet Engineering Task Force (IETF).</span><span class="sxs-lookup"><span data-stu-id="2d5b5-159">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="2d5b5-160">Eine Alternative Verbindungsmethode besteht darin, dass vor dem Senden von Protokoll Befehlen eine SSL-Sitzung eingerichtet wird.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-160">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="2d5b5-161">Diese Verbindungsmethode wird manchmal als SMTPS bezeichnet und verwendet standardmäßig Port 465.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-161">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="2d5b5-162">Diese Alternative Verbindungsmethode mithilfe von SSL wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-162">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="2d5b5-163">Die- <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert des `enableSsl` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-163">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d5b5-164">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2d5b5-164">Example</span></span>  
 <span data-ttu-id="2d5b5-165">Im folgenden Beispiel werden die entsprechenden SMTP-Parameter zum Senden von e-Mails mit den standardmäßigen Netzwerk Anmelde Informationen angegeben.</span><span class="sxs-lookup"><span data-stu-id="2d5b5-165">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2d5b5-166">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="2d5b5-166">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="2d5b5-167">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="2d5b5-167">Network Settings Schema</span></span>](index.md)
