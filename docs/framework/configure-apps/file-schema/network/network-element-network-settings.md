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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154815"
---
# <a name="network-element-network-settings"></a><span data-ttu-id="293df-102">\<network>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="293df-102">\<network> Element (Network Settings)</span></span>
<span data-ttu-id="293df-103">Konfiguriert die Netzwerkoptionen für einen externen SMTP-Server (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="293df-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<network>**

## <a name="syntax"></a><span data-ttu-id="293df-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="293df-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="293df-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="293df-105">Attributes and Elements</span></span>  
 <span data-ttu-id="293df-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="293df-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="293df-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="293df-107">Attributes</span></span>  
  
|<span data-ttu-id="293df-108">attribute</span><span class="sxs-lookup"><span data-stu-id="293df-108">Attribute</span></span>|<span data-ttu-id="293df-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="293df-109">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="293df-110">Gibt den Client Domänen Namen an, der in der ursprünglichen SMTP-Protokoll Anforderung zum Herstellen einer Verbindung mit dem SMTP-Mailserver verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="293df-110">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="293df-111">Der Standardwert ist der localhost-Name des lokalen Computers, der die Anforderung sendet.</span><span class="sxs-lookup"><span data-stu-id="293df-111">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="293df-112">Gibt an, ob die Standardbenutzer Anmelde Informationen für den Zugriff auf den SMTP-Mailserver für SMTP-Transaktionen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="293df-112">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="293df-113">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="293df-113">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="293df-114">Gibt an, ob für den Zugriff auf einen SMTP-Mailserver SSL verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="293df-114">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="293df-115">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="293df-115">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="293df-116">Gibt den Hostnamen des SMTP-Mailservers an, der für SMTP-Transaktionen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="293df-116">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="293df-117">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="293df-117">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="293df-118">Gibt das Kennwort an, das für die Authentifizierung beim SMTP-Mailserver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="293df-118">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="293df-119">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="293df-119">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="293df-120">Gibt die Portnummer an, die für die Verbindung mit dem SMTP-Mailserver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="293df-120">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="293df-121">Der Standardwert ist 25.</span><span class="sxs-lookup"><span data-stu-id="293df-121">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="293df-122">Gibt den Dienstanbieter Namen (Service Provider Name, SPN) für die Authentifizierung an, wenn der erweiterte Schutz für SMTP-Transaktionen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="293df-122">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="293df-123">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="293df-123">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="293df-124">Gibt den Benutzernamen an, der für die Authentifizierung beim SMTP-Mailserver verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="293df-124">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="293df-125">Dieses Attribut hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="293df-125">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="293df-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="293df-126">Child Elements</span></span>  
 <span data-ttu-id="293df-127">Keine</span><span class="sxs-lookup"><span data-stu-id="293df-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="293df-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="293df-128">Parent Elements</span></span>  
  
|<span data-ttu-id="293df-129">Element</span><span class="sxs-lookup"><span data-stu-id="293df-129">Element</span></span>|<span data-ttu-id="293df-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="293df-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="293df-131">\<smtp>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="293df-131">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="293df-132">Konfiguriert SMTP (Simple Mail Transport Protocol)-e-Mail-Sende Optionen.</span><span class="sxs-lookup"><span data-stu-id="293df-132">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="293df-133">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="293df-133">Remarks</span></span>  
 <span data-ttu-id="293df-134">Einige SMTP-Server erfordern, dass Sie sich vor der Verwendung beim Server authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="293df-134">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="293df-135">Wenn Sie sich mit den standardmäßigen Netzwerk Anmelde Informationen auf dem Host authentifizieren möchten, legen Sie das- `defaultCredentials` Attribut auf fest `true` .</span><span class="sxs-lookup"><span data-stu-id="293df-135">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="293df-136">Die- <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert des `defaultCredentials` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="293df-136">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="293df-137">Sie können auch die Standard Authentifizierung (Benutzername und Kennwort) verwenden, um sich beim SMTP-Server zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="293df-137">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="293df-138">Um diese Option verwenden zu können, müssen Sie einen gültigen Benutzernamen und ein Kennwort für den angegebenen SMTP-Server angeben.</span><span class="sxs-lookup"><span data-stu-id="293df-138">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="293df-139">Bei der Standard Authentifizierung werden die `userName` `password` Werte und unverschlüsselt an den Server gesendet.</span><span class="sxs-lookup"><span data-stu-id="293df-139">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="293df-140">Personen, die den Netzwerk Datenverkehr überwachen, können Ihre Anmelde Informationen anzeigen und zum Herstellen der Verbindung mit dem Server verwenden</span><span class="sxs-lookup"><span data-stu-id="293df-140">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="293df-141">Sie sollten die Verwendung eines sichereren Authentifizierungsmechanismus in Erwägung gezogen werden, z. b. Kerberos oder NT-LAN-Manager (NTLM). Wenn `defaultCredentials` `true` den Wert hat, wird Kerberos oder NTLM verwendet, wenn der Server diese Protokolle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="293df-141">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="293df-142">Die Optionen Standard Authentifizierung und Standard-Netzwerk Anmelde Informationen schließen sich gegenseitig aus. Wenn Sie `defaultCredentials` auf festlegen `true` und einen Benutzernamen und ein Kennwort angeben, werden die standardmäßigen Netzwerk Anmelde Informationen verwendet, und die grundlegenden Authentifizierungsdaten werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="293df-142">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="293df-143">Bei der Standard Authentifizierung `userName` sollten Sie auch einen angeben, `password` um sich selbst beim Mailserver zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="293df-143">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="293df-144">Die- <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert des `userName` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="293df-144">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="293df-145">Die- <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert des `password` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="293df-145">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="293df-146">Ein- `password` Attribut wird aus Sicherheitsgründen normalerweise nicht in Konfigurationsdateien eingegeben.</span><span class="sxs-lookup"><span data-stu-id="293df-146">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="293df-147">Das- `clientDomain` Attribut ändert den Client Domänen Namen, der in der ursprünglichen SMTP-Protokoll Anforderung verwendet wird, an einen SMTP-Server.</span><span class="sxs-lookup"><span data-stu-id="293df-147">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="293df-148">Das- `clientDomain` Attribut kann auf den voll qualifizierten Domänen Namen des lokalen Computers und nicht auf den standardmäßig verwendeten localhost-Namen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="293df-148">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="293df-149">Dies ermöglicht eine bessere Konformität mit den SMTP-Protokollstandards.</span><span class="sxs-lookup"><span data-stu-id="293df-149">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="293df-150">Der Standardwert ist der localhost-Name des lokalen Computers, der die Anforderung sendet.</span><span class="sxs-lookup"><span data-stu-id="293df-150">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="293df-151">Die- <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert des `clientDomain` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="293df-151">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="293df-152">Das- `targetName` Attribut wird für die Authentifizierung verwendet, wenn der erweiterte Schutz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="293df-152">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="293df-153">Der Standardwert ist "SmtpSvc/ \<host> ", wobei \<host> der Hostname des SMTP-Mailservers ist.</span><span class="sxs-lookup"><span data-stu-id="293df-153">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="293df-154">Die- <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert des `targetName` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="293df-154">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="293df-155">Das- `enableSsl` Attribut gibt an, ob für den Zugriff auf einen SMTP-Mailserver SSL verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="293df-155">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="293df-156">Die- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> Klasse unterstützt nur die SMTP-Dienst Erweiterung für Secure SMTP over Transport Layer Security, wie in RFC 3207 definiert.</span><span class="sxs-lookup"><span data-stu-id="293df-156">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="293df-157">In diesem Modus beginnt die SMTP-Sitzung auf einem unverschlüsselten Kanal. Anschließend wird vom Client ein STARTTLS-Befehl an den Server ausgegeben, um zur sicheren Kommunikation über SSL zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="293df-157">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="293df-158">Weitere Informationen finden Sie unter RFC 3207, veröffentlicht von der Internet Engineering Task Force (IETF).</span><span class="sxs-lookup"><span data-stu-id="293df-158">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="293df-159">Eine Alternative Verbindungsmethode besteht darin, dass vor dem Senden von Protokoll Befehlen eine SSL-Sitzung eingerichtet wird.</span><span class="sxs-lookup"><span data-stu-id="293df-159">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="293df-160">Diese Verbindungsmethode wird manchmal als SMTPS bezeichnet und verwendet standardmäßig Port 465.</span><span class="sxs-lookup"><span data-stu-id="293df-160">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="293df-161">Diese Alternative Verbindungsmethode mithilfe von SSL wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="293df-161">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="293df-162">Die- <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> Eigenschaft kann verwendet werden, um den aktuellen Wert des `enableSsl` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="293df-162">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="293df-163">Beispiel</span><span class="sxs-lookup"><span data-stu-id="293df-163">Example</span></span>  
 <span data-ttu-id="293df-164">Im folgenden Beispiel werden die entsprechenden SMTP-Parameter zum Senden von e-Mails mit den standardmäßigen Netzwerk Anmelde Informationen angegeben.</span><span class="sxs-lookup"><span data-stu-id="293df-164">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="293df-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="293df-165">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="293df-166">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="293df-166">Network Settings Schema</span></span>](index.md)
