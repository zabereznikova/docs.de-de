---
title: 'Vorgehensweise: Aktivieren der Nachrichtenreplay-Erkennung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF security
- replay detection [WCF]
- WCF, custom bindings
- WCF, security
ms.assetid: 8b847e91-69a3-49e1-9e5f-0c455e50d804
ms.openlocfilehash: bf45b39f59e2fe38fec88d1fac23ab824c009546
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597084"
---
# <a name="how-to-enable-message-replay-detection"></a><span data-ttu-id="279ef-102">Vorgehensweise: Aktivieren der Nachrichtenreplay-Erkennung</span><span class="sxs-lookup"><span data-stu-id="279ef-102">How to: Enable Message Replay Detection</span></span>
<span data-ttu-id="279ef-103">Ein Replay-Angriff tritt auf, wenn ein Angreifer einen Nachrichtenstrom zwischen zwei Parteien kopiert und den Strom für eine oder mehrere Parteien wiedergibt.</span><span class="sxs-lookup"><span data-stu-id="279ef-103">A replay attack occurs when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties.</span></span> <span data-ttu-id="279ef-104">Wenn der Angriff nicht abgeschwächt wird, verarbeiten die angegriffenen Computer den Strom als zulässige Meldungen, was zu einer Reihe negativer Konsequenzen führt, wie z. B. redundanten Bestellungen eines Artikels.</span><span class="sxs-lookup"><span data-stu-id="279ef-104">Unless mitigated, the computers subject to the attack will process the stream as legitimate messages, resulting in a range of bad consequences, such as redundant orders of an item.</span></span>  
  
 <span data-ttu-id="279ef-105">Weitere Informationen zur Erkennung von Nachrichten Replay finden Sie unter [Message Replay-Erkennung](https://docs.microsoft.com/previous-versions/msp-n-p/ff649371(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="279ef-105">For more information about message replay detection, see [Message Replay Detection](https://docs.microsoft.com/previous-versions/msp-n-p/ff649371(v=pandp.10)).</span></span>  
  
 <span data-ttu-id="279ef-106">Das folgende Verfahren veranschaulicht verschiedene Eigenschaften, die Sie verwenden können, um die Wiedergabe Erkennung mithilfe von Windows Communication Foundation (WCF) zu steuern.</span><span class="sxs-lookup"><span data-stu-id="279ef-106">The following procedure demonstrates various properties that you can use to control replay detection using Windows Communication Foundation (WCF).</span></span>  
  
### <a name="to-control-replay-detection-on-the-client-using-code"></a><span data-ttu-id="279ef-107">So steuern Sie die Replay-Erkennung für den Client mithilfe von Code</span><span class="sxs-lookup"><span data-stu-id="279ef-107">To control replay detection on the client using code</span></span>  
  
1. <span data-ttu-id="279ef-108">Erstellen Sie ein <xref:System.ServiceModel.Channels.SecurityBindingElement> zur Verwendung in einer <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="279ef-108">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> to use in a <xref:System.ServiceModel.Channels.CustomBinding>.</span></span> <span data-ttu-id="279ef-109">Weitere Informationen finden Sie unter Gewusst [wie: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="279ef-109">For more information, see [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span> <span data-ttu-id="279ef-110">Im folgenden Beispiel wird eine <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> verwendet, die mithilfe der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> der <xref:System.ServiceModel.Channels.SecurityBindingElement>-Klasse erstellt worden ist.</span><span class="sxs-lookup"><span data-stu-id="279ef-110">The following example uses a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> created with the <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span>  
  
2. <span data-ttu-id="279ef-111">Verwenden Sie die <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A>-Eigenschaft, um einen Verweis auf die <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>-Klasse zurückzugeben und die folgenden Eigenschaften nach Bedarf festzulegen:</span><span class="sxs-lookup"><span data-stu-id="279ef-111">Use the <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A> property to return a reference to the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> class and set any of the following properties, as appropriate:</span></span>  
  
    1. <span data-ttu-id="279ef-112">`DetectReplay`.</span><span class="sxs-lookup"><span data-stu-id="279ef-112">`DetectReplay`.</span></span> <span data-ttu-id="279ef-113">Ein boolescher Wert.</span><span class="sxs-lookup"><span data-stu-id="279ef-113">A Boolean value.</span></span> <span data-ttu-id="279ef-114">Dieser bestimmt, ob der Client Replays vom Server erkennen sollte.</span><span class="sxs-lookup"><span data-stu-id="279ef-114">This governs whether the client should detect replays from the server.</span></span> <span data-ttu-id="279ef-115">Der Standardwert lautet `true`.</span><span class="sxs-lookup"><span data-stu-id="279ef-115">The default is `true`.</span></span>  
  
    2. <span data-ttu-id="279ef-116">`MaxClockSkew`.</span><span class="sxs-lookup"><span data-stu-id="279ef-116">`MaxClockSkew`.</span></span> <span data-ttu-id="279ef-117">Ein <xref:System.TimeSpan>-Wert.</span><span class="sxs-lookup"><span data-stu-id="279ef-117">A <xref:System.TimeSpan> value.</span></span> <span data-ttu-id="279ef-118">Bestimmt die Zeitverschiebung, die der Replay-Mechanismus zwischen dem Client und dem Server tolerieren kann.</span><span class="sxs-lookup"><span data-stu-id="279ef-118">Governs how much time skew the replay mechanism can tolerate between the client and the server.</span></span> <span data-ttu-id="279ef-119">Das Sicherheitsverfahren untersucht den gesendeten Zeitstempel und bestimmt, ob er zu weit in der Vergangenheit zurückliegend gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="279ef-119">The security mechanism examines the time stamp sent and determines whether it was sent too far back in the past.</span></span> <span data-ttu-id="279ef-120">Die Standardeinstellung ist 5 Minuten.</span><span class="sxs-lookup"><span data-stu-id="279ef-120">The default is 5 minutes.</span></span>  
  
    3. <span data-ttu-id="279ef-121">`ReplayWindow`.</span><span class="sxs-lookup"><span data-stu-id="279ef-121">`ReplayWindow`.</span></span> <span data-ttu-id="279ef-122">Ein `TimeSpan`-Wert.</span><span class="sxs-lookup"><span data-stu-id="279ef-122">A `TimeSpan` value.</span></span> <span data-ttu-id="279ef-123">Dieser bestimmt, wie lange eine Nachricht im Netzwerk bleiben kann, nachdem sie vom Server (durch Vermittler) gesendet worden ist, bevor sie den Client erreicht.</span><span class="sxs-lookup"><span data-stu-id="279ef-123">This governs how long a message can live in the network after the server sends it (through intermediaries) before reaching the client.</span></span> <span data-ttu-id="279ef-124">Der Client verfolgt die Signaturen der Nachrichten, die innerhalb des letzten `ReplayWindow` gesendet wurden, zur Replay-Erkennung.</span><span class="sxs-lookup"><span data-stu-id="279ef-124">The client tracks the signatures of the messages sent within the latest `ReplayWindow` for the purposes of replay detection.</span></span>  
  
    4. <span data-ttu-id="279ef-125">`ReplayCacheSize`.</span><span class="sxs-lookup"><span data-stu-id="279ef-125">`ReplayCacheSize`.</span></span> <span data-ttu-id="279ef-126">Ein ganzzahliger Wert.</span><span class="sxs-lookup"><span data-stu-id="279ef-126">An integer value.</span></span> <span data-ttu-id="279ef-127">Der Client speichert die Signaturen der Nachricht in einem Cache.</span><span class="sxs-lookup"><span data-stu-id="279ef-127">The client stores the signatures of the message in a cache.</span></span> <span data-ttu-id="279ef-128">Diese Einstellung gibt an, wie viele Signaturen der Cache speichern kann.</span><span class="sxs-lookup"><span data-stu-id="279ef-128">This setting specifies how many signatures the cache can store.</span></span> <span data-ttu-id="279ef-129">Wenn die Zahl der Nachrichten, die innerhalb des letzten Replay-Fensters gesendet wurden, das Cachelimit erreicht, werden neue Nachrichten zurückgewiesen, bis die ältesten zwischengespeicherten Signaturen das Zeitlimit überschreiten.</span><span class="sxs-lookup"><span data-stu-id="279ef-129">If the number of messages sent within the last replay window reaches the cache limit, new messages are rejected until the oldest cached signatures reach the time limit.</span></span> <span data-ttu-id="279ef-130">Der Standardwert ist 500000.</span><span class="sxs-lookup"><span data-stu-id="279ef-130">The default is 500000.</span></span>  
  
### <a name="to-control-replay-detection-on-the-service-using-code"></a><span data-ttu-id="279ef-131">So steuern Sie die Replay-Erkennung für den Dienst mithilfe von Code</span><span class="sxs-lookup"><span data-stu-id="279ef-131">To control replay detection on the service using code</span></span>  
  
1. <span data-ttu-id="279ef-132">Erstellen Sie ein <xref:System.ServiceModel.Channels.SecurityBindingElement> zur Verwendung in einer <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="279ef-132">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> to use in a <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>  
  
2. <span data-ttu-id="279ef-133">Verwenden Sie die <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A>-Eigenschaft, um einen Verweis auf die <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>-Klasse zurückzugeben, und legen Sie die Eigenschaften fest, wie zuvor beschrieben.</span><span class="sxs-lookup"><span data-stu-id="279ef-133">Use the <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A> property to return a reference to the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class, and set the properties as described previously.</span></span>  
  
### <a name="to-control-replay-detection-in-configuration-for-the-client-or-service"></a><span data-ttu-id="279ef-134">So steuern Sie die Replay-Erkennung in der Konfiguration für den Client oder den Dienst</span><span class="sxs-lookup"><span data-stu-id="279ef-134">To control replay detection in configuration for the client or service</span></span>  
  
1. <span data-ttu-id="279ef-135">Erstellen Sie eine [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="279ef-135">Create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
2. <span data-ttu-id="279ef-136">Erstellen Sie ein `<security>`-Element.</span><span class="sxs-lookup"><span data-stu-id="279ef-136">Create a `<security>` element.</span></span>  
  
3. <span data-ttu-id="279ef-137">Erstellen Sie ein [\<localClientSettings>](../../configure-apps/file-schema/wcf/localclientsettings-element.md) oder ein [\<localServiceSettings>](../../configure-apps/file-schema/wcf/localservicesettings-element.md) .</span><span class="sxs-lookup"><span data-stu-id="279ef-137">Create a [\<localClientSettings>](../../configure-apps/file-schema/wcf/localclientsettings-element.md) or [\<localServiceSettings>](../../configure-apps/file-schema/wcf/localservicesettings-element.md).</span></span>  
  
4. <span data-ttu-id="279ef-138">Legen Sie die folgenden Attributwerte nach Bedarf fest: `detectReplays`, `maxClockSkew`, `replayWindow` und `replayCacheSize`.</span><span class="sxs-lookup"><span data-stu-id="279ef-138">Set the following attribute values, as appropriate: `detectReplays`, `maxClockSkew`, `replayWindow`, and `replayCacheSize`.</span></span> <span data-ttu-id="279ef-139">Im folgenden Beispiel werden sowohl die Attribute eines `<localServiceSettings>`-Elements festgelegt:</span><span class="sxs-lookup"><span data-stu-id="279ef-139">The following example sets the attributes of both a `<localServiceSettings>` and a `<localClientSettings>` element:</span></span>  
  
    ```xml  
    <customBinding>  
      <binding name="NewBinding0">  
       <textMessageEncoding />  
        <security>  
         <localClientSettings
          replayCacheSize="800000"
          maxClockSkew="00:03:00"  
          replayWindow="00:03:00" />  
         <localServiceSettings
          replayCacheSize="800000"
          maxClockSkew="00:03:00"  
          replayWindow="00:03:00" />  
        <secureConversationBootstrap />  
       </security>  
      <httpTransport />  
     </binding>  
    </customBinding>  
    ```  
  
## <a name="example"></a><span data-ttu-id="279ef-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="279ef-140">Example</span></span>  
 <span data-ttu-id="279ef-141">Im folgenden Beispiel wird ein <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> mithilfe der <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A>-Methode erstellt, und die Replay-Eigenschaften der Bindung werden festgelegt.</span><span class="sxs-lookup"><span data-stu-id="279ef-141">The following example creates a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> using the <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> method, and sets the replay properties of the binding.</span></span>  
  
 [!code-csharp[c_ReplayDetection#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_replaydetection/cs/source.cs#1)]
 [!code-vb[c_ReplayDetection#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_replaydetection/vb/source.vb#1)]  
  
## <a name="scope-of-replay-message-security-only"></a><span data-ttu-id="279ef-142">Replay-Bereich: Nur Nachrichtensicherheit</span><span class="sxs-lookup"><span data-stu-id="279ef-142">Scope of Replay: Message Security Only</span></span>  
 <span data-ttu-id="279ef-143">Beachten Sie, dass die folgenden Prozeduren nur für den Nachrichtensicherheitsmodus gelten.</span><span class="sxs-lookup"><span data-stu-id="279ef-143">Note that the following procedures apply only to Message security mode.</span></span> <span data-ttu-id="279ef-144">Für den Transportmodus und den Transportmodus mit Nachrichtenanmeldeinformationen erkennen die Transportmechanismen Replays.</span><span class="sxs-lookup"><span data-stu-id="279ef-144">For Transport and Transport with Message Credential modes, the transport mechanisms detect replays.</span></span>  
  
## <a name="secure-conversation-notes"></a><span data-ttu-id="279ef-145">Hinweise für die sichere Konversation</span><span class="sxs-lookup"><span data-stu-id="279ef-145">Secure Conversation Notes</span></span>  
 <span data-ttu-id="279ef-146">Bei Bindungen, die sichere Konversationen ermöglichen, können Sie diese Einstellungen sowohl für den Anwendungskanal als auch für die sichere Konversationsbootstrap-Bindung anpassen.</span><span class="sxs-lookup"><span data-stu-id="279ef-146">For bindings that enable secure conversations, you can adjust these settings both for the application channel as well as for the secure conversation bootstrap binding.</span></span> <span data-ttu-id="279ef-147">Sie können z. B. Replays für den Anwendungskanal deaktivieren, sie jedoch für den Bootstrapkanal aktivieren, der die sichere Konversation aufbaut.</span><span class="sxs-lookup"><span data-stu-id="279ef-147">For example, you can turn off replays for the application channel but enable them for the bootstrap channel that establishes the secure conversation.</span></span>  
  
 <span data-ttu-id="279ef-148">Wenn Sie keine Sitzungen für sichere Konversation verwenden, kann die Replay-Erkennung nicht garantieren, dass Replays in Serverfarmszenarien und bei der Wiederverwendung des Prozesses erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="279ef-148">If you do not use secure conversation sessions, replay detection does not guarantee detecting replays in server farm scenarios and when the process is recycled.</span></span> <span data-ttu-id="279ef-149">Dies gilt für die folgenden vom System bereitgestellten Bindungen:</span><span class="sxs-lookup"><span data-stu-id="279ef-149">This applies to the following system-provided bindings:</span></span>  
  
- <span data-ttu-id="279ef-150"><xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="279ef-150"><xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
- <span data-ttu-id="279ef-151"><xref:System.ServiceModel.WSHttpBinding> mit der <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A>-Eigenschaft mit dem Wert `false`.</span><span class="sxs-lookup"><span data-stu-id="279ef-151"><xref:System.ServiceModel.WSHttpBinding> with the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> property set to `false`.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="279ef-152">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="279ef-152">Compiling the Code</span></span>  
  
- <span data-ttu-id="279ef-153">Die folgenden Namespaces sind zum Kompilieren des Codes erforderlich:</span><span class="sxs-lookup"><span data-stu-id="279ef-153">The following namespaces are required to compile the code:</span></span>  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
## <a name="see-also"></a><span data-ttu-id="279ef-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="279ef-154">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [<span data-ttu-id="279ef-155">Sichere Unterhaltungen und sichere Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="279ef-155">Secure Conversations and Secure Sessions</span></span>](secure-conversations-and-secure-sessions.md)
- [\<localClientSettings>](../../configure-apps/file-schema/wcf/localclientsettings-element.md)
- [<span data-ttu-id="279ef-156">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="279ef-156">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
