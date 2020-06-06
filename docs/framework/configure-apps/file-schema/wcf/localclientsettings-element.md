---
title: <localClientSettings>-Element
ms.date: 03/30/2017
ms.assetid: 4680ace5-f4e1-4fcb-b9d8-a4a4af5cd7ae
ms.openlocfilehash: 3ec0394943c030a8866087c98a912682a2a2112e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400320"
---
# <a name="localclientsettings-element"></a><span data-ttu-id="4269f-102">\<localClientSettings>-Element</span><span class="sxs-lookup"><span data-stu-id="4269f-102">\<localClientSettings> element</span></span>
<span data-ttu-id="4269f-103">Legt die Sicherheitseinstellungen für einen lokalen Client für diese Bindung fest.</span><span class="sxs-lookup"><span data-stu-id="4269f-103">Specifies the security settings of a local client for this binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localClientSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="4269f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4269f-104">Syntax</span></span>  
  
```xml  
<security>
   <localClientSettings cacheCookies="Boolean"
                        cookieRenewalThresholdPercentage="Integer"
                        detectReplays="Boolean"
                        maxClockSkew="TimeSpan"
                        maxCookieCachingTime="TimeSpan"
                        reconnectTransportOnFailure="Boolean"
                        replayCacheSize="Integer"
                        replayWindow="TimeSpan"
                        sessionKeyRenewalInterval="TimeSpan"
                        sessionKeyRolloverInterval="TimeSpan"
                        timestampValidityDuration="TimeSpan" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4269f-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4269f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4269f-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4269f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4269f-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="4269f-107">Attributes</span></span>  
  
|<span data-ttu-id="4269f-108">attribute</span><span class="sxs-lookup"><span data-stu-id="4269f-108">Attribute</span></span>|<span data-ttu-id="4269f-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4269f-109">Description</span></span>|  
|---------------|-----------------|  
|`cacheCookies`|<span data-ttu-id="4269f-110">Ein boolescher Wert, der angibt, ob die Cookiezwischenspeicherung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4269f-110">A Boolean value that specifies whether cookie caching is enabled.</span></span> <span data-ttu-id="4269f-111">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="4269f-111">The default is `false`.</span></span>|  
|`cookieRenewalThresholdPercentage`|<span data-ttu-id="4269f-112">Eine ganze Zahl, die den maximalen Prozentsatz an Cookies angibt, die erneuert werden können.</span><span class="sxs-lookup"><span data-stu-id="4269f-112">An integer that specifies the maximum percentage of cookies that can be renewed.</span></span> <span data-ttu-id="4269f-113">Dieser Wert sollte zwischen 0 und einschließlich 100 liegen.</span><span class="sxs-lookup"><span data-stu-id="4269f-113">This value should be between 0 and 100 inclusively.</span></span> <span data-ttu-id="4269f-114">Der Standard ist 90.</span><span class="sxs-lookup"><span data-stu-id="4269f-114">The default is 90.</span></span>|  
|`detectReplays`|<span data-ttu-id="4269f-115">Ein boolescher Wert, der angibt, ob Replay-Angriffe auf den Kanal automatisch erkannt und behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="4269f-115">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span> <span data-ttu-id="4269f-116">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="4269f-116">The default is `false`.</span></span>|  
|`maxClockSkew`|<span data-ttu-id="4269f-117">Eine <xref:System.TimeSpan>, die den maximal zulässigen Zeitunterschied zwischen den Systemuhren der beiden Kommunikationspartner angibt.</span><span class="sxs-lookup"><span data-stu-id="4269f-117">A <xref:System.TimeSpan> that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span> <span data-ttu-id="4269f-118">Der Standardwert ist "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="4269f-118">The default value is "00:05:00".</span></span><br /><br /> <span data-ttu-id="4269f-119">Wenn dieser Wert auf den Standardwert festgelegt wird, akzeptiert der Empfänger Nachrichten mit Sendezeitstempeln, die bis zu 5 Minuten vor oder nach dem Zeitpunkt liegen, zu dem die Nachricht empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="4269f-119">When this value is set to the default, the receiver accepts messages with send-time time stamps up to 5 minutes later or earlier than the time the message was received.</span></span> <span data-ttu-id="4269f-120">Nachrichten, die den Sendezeittest nicht bestehen, werden verworfen.</span><span class="sxs-lookup"><span data-stu-id="4269f-120">Messages that do not pass the send-time test are rejected.</span></span> <span data-ttu-id="4269f-121">Diese Einstellung wird in Verbindung mit dem `replayWindow`-Attribut verwendet.</span><span class="sxs-lookup"><span data-stu-id="4269f-121">This setting is used in conjunction with the `replayWindow` attribute.</span></span>|  
|`maxCookieCachingTime`|<span data-ttu-id="4269f-122">Eine <xref:System.TimeSpan>, die die maximale Lebensdauer von Cookies angibt.</span><span class="sxs-lookup"><span data-stu-id="4269f-122">A <xref:System.TimeSpan> that specifies the maximum lifetime of cookies.</span></span> <span data-ttu-id="4269f-123">Der Standardwert ist "10675199.02:48:05.4775807".</span><span class="sxs-lookup"><span data-stu-id="4269f-123">The default value is "10675199.02:48:05.4775807".</span></span>|  
|`reconnectTransportOnFailure`|<span data-ttu-id="4269f-124">Ein boolescher Wert, der angibt, ob Verbindungen, die WS-Reliable-Messaging verwenden, nach Transportfehlern erneut versuchen, eine Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4269f-124">A Boolean value that specifies whether connections using WS-Reliable messaging will attempt to reconnect after transport failures.</span></span> <span data-ttu-id="4269f-125">Der Standard ist `true`, was bedeutet, dass unendlich viele Versuche der Verbindungsherstellung durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4269f-125">The default is `true`, which means that infinite attempts to reconnect are attempted.</span></span> <span data-ttu-id="4269f-126">Dieser Kreislauf wird vom Inaktivitätstimeout unterbrochen, das dazu führt, dass der Kanal eine Ausnahme ausgibt, wenn die Verbindung nicht wiederhergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4269f-126">The cycle is broken by the inactivity time-out, which causes the channel to throw an exception when it cannot be reconnected.</span></span>|  
|`replayCacheSize`|<span data-ttu-id="4269f-127">Eine positive ganze Zahl, die die Anzahl der zwischengespeicherten Nonces für die Replay-Erkennung angibt.</span><span class="sxs-lookup"><span data-stu-id="4269f-127">A positive integer that specifies the number of cached nonces used for replay detection.</span></span> <span data-ttu-id="4269f-128">Wenn dieses Limit überschritten wird, wird die älteste Nonce entfernt, und eine neue Nonce für die neue Nachricht wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="4269f-128">If this limit is exceeded, the oldest nonce is removed and a new nonce is created for the new message.</span></span> <span data-ttu-id="4269f-129">Der Standardwert ist 500000.</span><span class="sxs-lookup"><span data-stu-id="4269f-129">The default value is 500000.</span></span>|  
|`replayWindow`|<span data-ttu-id="4269f-130">Eine <xref:System.TimeSpan>, die die Dauer angibt, in der einzelne Nachrichtennonces gültig sind.</span><span class="sxs-lookup"><span data-stu-id="4269f-130">A <xref:System.TimeSpan> that specifies the duration in which individual message nonces are valid.</span></span><br /><br /> <span data-ttu-id="4269f-131">Nach dieser Zeitspanne wird eine Nachricht mit derselben Nonce wie die zuvor gesendete nicht akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="4269f-131">After this duration, a message sent with the same nonce as the one sent before will not be accepted.</span></span> <span data-ttu-id="4269f-132">Dieses Attribut wird in Verbindung mit dem `maxClockSkew`-Attribut verwendet, um Replay-Angriffe zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="4269f-132">This attribute is used in conjunction with the `maxClockSkew` attribute to prevent replay attacks.</span></span> <span data-ttu-id="4269f-133">Ein Angreifer kann eine Nachricht wiederholen, nachdem das Wiederholungsfenster abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="4269f-133">An attacker could replay a message after its replay window has expired.</span></span> <span data-ttu-id="4269f-134">Die Nachricht besteht jedoch den `maxClockSkew`-Test nicht, der Nachrichten mit Zeitstempeln bis zu einem bestimmten Zeitpunkt vor oder nach dem Empfang der Nachricht zurückweist.</span><span class="sxs-lookup"><span data-stu-id="4269f-134">This message, however, would fail the `maxClockSkew` test which rejects messages with send-time timestamps up to a specified time later or earlier than the time the message was received.</span></span>|  
|`sessionKeyRenewalInterval`|<span data-ttu-id="4269f-135">Eine <xref:System.TimeSpan>, die angibt, nach welchem Zeitraum der Initiator den Schlüssel für die Sicherheitssitzung erneuert.</span><span class="sxs-lookup"><span data-stu-id="4269f-135">A <xref:System.TimeSpan> that specifies the duration after which the initiator will renew the key for the security session.</span></span> <span data-ttu-id="4269f-136">Der Standardwert ist "10:00:00".</span><span class="sxs-lookup"><span data-stu-id="4269f-136">The default is "10:00:00".</span></span>|  
|`sessionKeyRolloverInterval`|<span data-ttu-id="4269f-137">Eine <xref:System.TimeSpan>, die das Zeitintervall angibt, während dem ein früherer Sitzungsschlüssel während der Schlüsselerneuerung für eingehende Nachrichten gültig ist.</span><span class="sxs-lookup"><span data-stu-id="4269f-137">A <xref:System.TimeSpan> that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span> <span data-ttu-id="4269f-138">Der Standardwert ist "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="4269f-138">The default is "00:05:00".</span></span><br /><br /> <span data-ttu-id="4269f-139">Während der Erneuerung des Schlüssels müssen Nachrichten vom Client und vom Server mit dem aktuellsten Schlüssel gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="4269f-139">During key renewal, the client and server must always send messages using the most current available key.</span></span> <span data-ttu-id="4269f-140">Eingehende Nachrichten, die mit dem früheren Sitzungsschlüssel gesichert sind, werden von beiden Seiten bis zum Ablauf der Übergangszeit akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="4269f-140">Both parties will accept incoming messages secured with the previous session key until the rollover time expires.</span></span>|  
|`timestampValidityDuration`|<span data-ttu-id="4269f-141">Eine positive <xref:System.TimeSpan>, die die Dauer angibt, in der ein Zeitstempel gültig ist.</span><span class="sxs-lookup"><span data-stu-id="4269f-141">A positive <xref:System.TimeSpan> that specifies the duration in which a time stamp is valid.</span></span> <span data-ttu-id="4269f-142">Der Standardwert ist "00:15:00".</span><span class="sxs-lookup"><span data-stu-id="4269f-142">The default is "00:15:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4269f-143">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4269f-143">Child Elements</span></span>  
 <span data-ttu-id="4269f-144">Keine</span><span class="sxs-lookup"><span data-stu-id="4269f-144">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4269f-145">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4269f-145">Parent Elements</span></span>  
  
|<span data-ttu-id="4269f-146">Element</span><span class="sxs-lookup"><span data-stu-id="4269f-146">Element</span></span>|<span data-ttu-id="4269f-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4269f-147">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="4269f-148">Gibt die Sicherheitsoptionen für eine benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="4269f-148">Specifies the security options for a custom binding.</span></span>|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|<span data-ttu-id="4269f-149">Gibt die Standardwerte an, die zum Initiieren eines sicheren Konversationsdiensts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4269f-149">Specifies the default values used for initiating a secure conversation service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4269f-150">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4269f-150">Remarks</span></span>  
 <span data-ttu-id="4269f-151">Die Einstellungen sind lokal, da sie nicht von der Sicherheitsrichtlinie des Diensts abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="4269f-151">The settings are local in the sense that they are not settings derived from the security policy of the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4269f-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4269f-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.LocalClientSettings%2A>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A>
- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="4269f-153">Bindungen</span><span class="sxs-lookup"><span data-stu-id="4269f-153">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4269f-154">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="4269f-154">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4269f-155">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="4269f-155">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="4269f-156">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="4269f-156">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="4269f-157">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="4269f-157">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
