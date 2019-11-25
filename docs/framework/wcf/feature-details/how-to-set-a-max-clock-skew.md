---
title: 'Vorgehensweise: Festlegen der maximalen Zeitdehnung (Uhrabweichung)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MaxClockSkew property
- WCF, custom bindings
ms.assetid: 491d1705-eb29-43c2-a44c-c0cf996f74eb
ms.openlocfilehash: 96afa61d32e1ba744c9f3dbbeeb7fb2e55157f4c
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141655"
---
# <a name="how-to-set-a-max-clock-skew"></a><span data-ttu-id="ae951-102">Vorgehensweise: Festlegen der maximalen Zeitdehnung (Uhrabweichung)</span><span class="sxs-lookup"><span data-stu-id="ae951-102">How to: Set a Max Clock Skew</span></span>
<span data-ttu-id="ae951-103">Zeitkritische Funktionen können behindert werden, wenn zwei Computer unterschiedliche Uhreinstellungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ae951-103">Time-critical functions can be derailed if the clock settings on two computers are different.</span></span> <span data-ttu-id="ae951-104">Um diese Gefahr zu umgehen, können Sie für die `MaxClockSkew`-Eigenschaft einen <xref:System.TimeSpan>-Wert festlegen.</span><span class="sxs-lookup"><span data-stu-id="ae951-104">To mitigate this possibility, you can set the `MaxClockSkew` property to a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="ae951-105">Diese Eigenschaft ist für zwei Klassen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="ae951-105">This property is available on two classes:</span></span>  
  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
  
> [!IMPORTANT]
> <span data-ttu-id="ae951-106">Für eine sichere Konversation müssen Änderungen an der `MaxClockSkew`-Eigenschaft vorgenommen werden, wenn der Dienst oder der Client bootstrapped ist.</span><span class="sxs-lookup"><span data-stu-id="ae951-106">For a secure conversation, changes to the `MaxClockSkew` property  must be made when the service or client is bootstrapped.</span></span> <span data-ttu-id="ae951-107">Zu diesem Zweck müssen Sie die-Eigenschaft für den <xref:System.ServiceModel.Channels.SecurityBindingElement> festlegen, der von der <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A?displayProperty=nameWithType>-Eigenschaft zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ae951-107">To do this, you must set the property on the <xref:System.ServiceModel.Channels.SecurityBindingElement> returned by the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="ae951-108">Um die Eigenschaft bei einer der vom System bereitgestellten Bindungen zu ändern, suchen Sie das Sicherheitsbindungselement in der Bindungsauflistung und legen für die `MaxClockSkew`-Eigenschaft einen neuen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="ae951-108">To change the property on one of the system-provided bindings, you must find the security binding element in the collection of bindings and set the `MaxClockSkew` property to a new value.</span></span> <span data-ttu-id="ae951-109">Von <xref:System.ServiceModel.Channels.SecurityBindingElement> werden zwei Klassen abgeleitet: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> und <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="ae951-109">Two classes derive from the <xref:System.ServiceModel.Channels.SecurityBindingElement>: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="ae951-110">Wenn Sie die Sicherheitsbindung aus der Auflistung abrufen, müssen Sie eine Umwandlung in einen dieser Typen durchführen, damit die `MaxClockSkew`-Eigenschaft richtig festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ae951-110">When retrieving the security binding from the collection, you must cast to one of these types in order to correctly set the `MaxClockSkew` property.</span></span> <span data-ttu-id="ae951-111">Im folgenden Beispiel wird eine <xref:System.ServiceModel.WSHttpBinding> verwendet, die die <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>-Klasse nutzt.</span><span class="sxs-lookup"><span data-stu-id="ae951-111">The following example uses a <xref:System.ServiceModel.WSHttpBinding>, which uses the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="ae951-112">Eine Liste, die den Typ der Sicherheitsbindung angibt, der in jeder vom System bereitgestellten Bindung verwendet werden soll, finden Sie unter vom [System bereitgestellte Bindungen](../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="ae951-112">For a list that specifies which type of security binding to use in each system-provided binding, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
## <a name="to-create-a-custom-binding-with-a-new-clock-skew-value-in-code"></a><span data-ttu-id="ae951-113">So erstellen Sie eine benutzerdefinierte Bindung mit einem neuen Zeitdehnungswert im Code</span><span class="sxs-lookup"><span data-stu-id="ae951-113">To create a custom binding with a new clock skew value in code</span></span>  
  
> [!WARNING]
> <span data-ttu-id="ae951-114">Fügen Sie im Code Verweise auf die folgenden Namespaces hinzu: <xref:System.ServiceModel.Channels>, <xref:System.ServiceModel.Description>, <xref:System.Security.Permissions>und <xref:System.ServiceModel.Security.Tokens>.</span><span class="sxs-lookup"><span data-stu-id="ae951-114">Add references to the following namespaces in your code: <xref:System.ServiceModel.Channels>, <xref:System.ServiceModel.Description>, <xref:System.Security.Permissions>, and <xref:System.ServiceModel.Security.Tokens>.</span></span>  
  
1. <span data-ttu-id="ae951-115">Erstellen Sie eine Instanz einer <xref:System.ServiceModel.WSHttpBinding>-Klasse, und legen Sie als Sicherheitsmodus <xref:System.ServiceModel.SecurityMode.Message?displayProperty=nameWithType> fest.</span><span class="sxs-lookup"><span data-stu-id="ae951-115">Create an instance of a <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to <xref:System.ServiceModel.SecurityMode.Message?displayProperty=nameWithType>.</span></span>  
  
2. <span data-ttu-id="ae951-116">Erstellen Sie eine neue Instanz der <xref:System.ServiceModel.Channels.BindingElementCollection>-Klasse durch Aufruf der <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="ae951-116">Create a new instance of the <xref:System.ServiceModel.Channels.BindingElementCollection> class by calling the <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> method.</span></span>  
  
3. <span data-ttu-id="ae951-117">Suchen Sie mit der <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A>-Methode der <xref:System.ServiceModel.Channels.BindingElementCollection>-Klasse nach dem Sicherheitsbindungselement.</span><span class="sxs-lookup"><span data-stu-id="ae951-117">Use the <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> method of the <xref:System.ServiceModel.Channels.BindingElementCollection> class to find the security binding element.</span></span>  
  
4. <span data-ttu-id="ae951-118">Bei Verwendung der <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A>-Methode führen Sie eine Umwandlung in den tatsächlichen Typ durch.</span><span class="sxs-lookup"><span data-stu-id="ae951-118">When using the <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> method, cast to the actual type.</span></span> <span data-ttu-id="ae951-119">Im folgenden Beispiel wird eine Umwandlung in den <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>-Typ vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="ae951-119">The example below casts to the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> type.</span></span>  
  
5. <span data-ttu-id="ae951-120">Legen Sie für das Sicherheitsbindungselement die <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="ae951-120">Set the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> property on the security binding element.</span></span>  
  
6. <span data-ttu-id="ae951-121">Erstellen Sie einen <xref:System.ServiceModel.ServiceHost> mit geeignetem Diensttyp und entsprechender Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="ae951-121">Create a <xref:System.ServiceModel.ServiceHost> with an appropriate service type and base address.</span></span>  
  
7. <span data-ttu-id="ae951-122">Fügen Sie mit der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methode einen Endpunkt hinzu, und nehmen Sie die <xref:System.ServiceModel.Channels.CustomBinding> auf.</span><span class="sxs-lookup"><span data-stu-id="ae951-122">Use the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method to add an endpoint and include the <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>  
  
     [!code-csharp[c_MaxClockSkew#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_maxclockskew/cs/source.cs#1)]
     [!code-vb[c_MaxClockSkew#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_maxclockskew/vb/source.vb#1)]  
  
## <a name="to-set-the-maxclockskew-in-configuration"></a><span data-ttu-id="ae951-123">So legen Sie MaxClockSkew in der Konfiguration fest</span><span class="sxs-lookup"><span data-stu-id="ae951-123">To set the MaxClockSkew in configuration</span></span>  
  
1. <span data-ttu-id="ae951-124">Erstellen Sie im Abschnitt [\<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Element einen [\<CustomBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="ae951-124">Create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) in the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element section.</span></span>  
  
2. <span data-ttu-id="ae951-125">Erstellen Sie ein [\<Bindungs >](../../configure-apps/file-schema/wcf/bindings.md) Element, und legen Sie das `name`-Attribut auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="ae951-125">Create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="ae951-126">Im folgenden Beispiel wird das Attribut auf den Wert `MaxClockSkewBinding` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ae951-126">The following example sets it to `MaxClockSkewBinding`.</span></span>  
  
3. <span data-ttu-id="ae951-127">Fügen Sie ein Codierungselement hinzu.</span><span class="sxs-lookup"><span data-stu-id="ae951-127">Add an encoding element.</span></span> <span data-ttu-id="ae951-128">Im folgenden Beispiel wird eine [\<textMessageEncoding->](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ae951-128">The example below adds a [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span></span>  
  
4. <span data-ttu-id="ae951-129">Fügen Sie ein [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Element hinzu, und legen Sie das `authenticationMode`-Attribut auf eine geeignete Einstellung fest.</span><span class="sxs-lookup"><span data-stu-id="ae951-129">Add a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element and set the `authenticationMode` attribute to an appropriate setting.</span></span> <span data-ttu-id="ae951-130">Im folgenden Beispiel wird das Attribut auf `Kerberos` festgelegt, um anzugeben, dass der Dienst die Windows-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="ae951-130">The following example set the attribute to `Kerberos` to specify that the service use Windows authentication.</span></span>  
  
5. <span data-ttu-id="ae951-131">Fügen Sie eine [\<LocalServiceSettings->](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) hinzu, und legen Sie das `maxClockSkew`-Attribut auf einen Wert in der Form `"##:##:##"`fest.</span><span class="sxs-lookup"><span data-stu-id="ae951-131">Add a [\<localServiceSettings>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) and set the `maxClockSkew` attribute to a value in the form of `"##:##:##"`.</span></span> <span data-ttu-id="ae951-132">Im folgenden Beispiel werden sieben Minuten eingestellt.</span><span class="sxs-lookup"><span data-stu-id="ae951-132">The following example sets it to 7 minutes.</span></span> <span data-ttu-id="ae951-133">Fügen Sie optional eine [\<LocalServiceSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) hinzu, und legen Sie das `maxClockSkew`-Attribut auf eine geeignete Einstellung fest.</span><span class="sxs-lookup"><span data-stu-id="ae951-133">Optionally, add a [\<localServiceSettings>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) and set the `maxClockSkew` attribute to an appropriate setting.</span></span>  
  
6. <span data-ttu-id="ae951-134">Fügen Sie ein Transportelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="ae951-134">Add a transport element.</span></span> <span data-ttu-id="ae951-135">Im folgenden Beispiel wird eine [\<httpTransport->](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)verwendet.</span><span class="sxs-lookup"><span data-stu-id="ae951-135">The following example uses an [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).</span></span>  
  
7. <span data-ttu-id="ae951-136">Für eine sichere Konversation müssen die Sicherheitseinstellungen beim Bootstrap im [\<secureConversationBootstrap->](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element auftreten.</span><span class="sxs-lookup"><span data-stu-id="ae951-136">For a secure conversation, the security settings must occur at the bootstrap in the [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element.</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="MaxClockSkewBinding">  
            <textMessageEncoding />  
            <security authenticationMode="Kerberos">  
               <localClientSettings maxClockSkew="00:07:00" />  
               <localServiceSettings maxClockSkew="00:07:00" />  
               <secureConversationBootstrap>  
                  <localClientSettings maxClockSkew="00:30:00" />  
                  <localServiceSettings maxClockSkew="00:30:00" />  
               </secureConversationBootstrap>  
            </security>  
            <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ae951-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae951-137">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ae951-138">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ae951-138">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
