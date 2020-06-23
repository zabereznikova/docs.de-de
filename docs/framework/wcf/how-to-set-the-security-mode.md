---
title: 'Vorgehensweise: Festlegen des Sicherheitsmodus'
description: 'Erfahren Sie, wie Sie die drei allgemeinen WCF-Sicherheitsmodi für die meisten vordefinierten Bindungen festlegen: Transport, Message und TransportWithMessageCredential.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Mode property
- WCF, security mode
- WCF, security
ms.assetid: 6e01dd9f-b5dd-4474-b24c-06e124de4ff7
ms.openlocfilehash: 2f834e1930b7676592f6cbc29a577424d75ebc01
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244542"
---
# <a name="how-to-set-the-security-mode"></a><span data-ttu-id="738ed-103">Vorgehensweise: Festlegen des Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="738ed-103">How to: Set the Security Mode</span></span>

<span data-ttu-id="738ed-104">Die Windows Communication Foundation (WCF)-Sicherheit verfügt über drei allgemeine Sicherheitsmodi, die für die meisten vordefinierten Bindungen gefunden werden: Transport, Message und "Transport with Message Credential".</span><span class="sxs-lookup"><span data-stu-id="738ed-104">Windows Communication Foundation (WCF) security has three common security modes that are found on most predefined bindings: transport, message, and "transport with message credential."</span></span> <span data-ttu-id="738ed-105">Zwei weitere Modi sind bindungsspezifisch: „TransportCredentialOnly“ ist nur in der <xref:System.ServiceModel.BasicHttpBinding> und „Both“ nur in der <xref:System.ServiceModel.NetMsmqBinding> verfügbar.</span><span class="sxs-lookup"><span data-stu-id="738ed-105">Two additional modes are specific to two bindings: the "transport-credential only" mode found on the <xref:System.ServiceModel.BasicHttpBinding>, and the "Both" mode, found on the <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="738ed-106">In diesem Thema werden jedoch die drei allgemeinen Sicherheitsmodi behandelt: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message> und <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="738ed-106">However, this topic concentrates on the three common security modes: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message>, and <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>

<span data-ttu-id="738ed-107">Diese Modi werden nicht von allen vordefinierten Bindungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="738ed-107">Note that not every predefined binding supports all of these modes.</span></span> <span data-ttu-id="738ed-108">In diesem Thema wird der Modus mit der <xref:System.ServiceModel.WSHttpBinding>-Klasse und mit der <xref:System.ServiceModel.NetTcpBinding>-Klasse festgelegt, und es wird veranschaulicht, wie der Modus programmgesteuert und in der Konfiguration festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="738ed-108">This topic sets the mode with the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> classes and demonstrates how to set the mode both programmatically and through configuration.</span></span>

<span data-ttu-id="738ed-109">Weitere Informationen finden Sie unter WCF-Sicherheit, [Übersicht über die Sicherheit](./feature-details/security-overview.md), [Sichern von Diensten](securing-services.md)und [Sichern von Diensten und Clients](./feature-details/securing-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="738ed-109">For more information, see WCF security, see [Security Overview](./feature-details/security-overview.md), [Securing Services](securing-services.md), and [Securing Services and Clients](./feature-details/securing-services-and-clients.md).</span></span> <span data-ttu-id="738ed-110">Weitere Informationen zum Transportmodus und zur Nachricht finden Sie unter [Transportsicherheit](./feature-details/transport-security.md) und [Nachrichten Sicherheit](./feature-details/message-security-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="738ed-110">For more information about transport mode and message, see [Transport Security](./feature-details/transport-security.md) and [Message Security](./feature-details/message-security-in-wcf.md).</span></span>

## <a name="to-set-the-security-mode-in-code"></a><span data-ttu-id="738ed-111">So legen Sie den Sicherheitsmodus im Code fest</span><span class="sxs-lookup"><span data-stu-id="738ed-111">To set the security mode in code</span></span>

1. <span data-ttu-id="738ed-112">Erstellen Sie eine Instanz der Bindungsklasse, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="738ed-112">Create an instance of the binding class that you are using.</span></span> <span data-ttu-id="738ed-113">Eine Liste der vordefinierten Bindungen finden Sie unter vom [System bereitgestellte Bindungen](system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="738ed-113">For a list of predefined bindings, see [System-Provided Bindings](system-provided-bindings.md).</span></span> <span data-ttu-id="738ed-114">In diesem Codebeispiel wird eine Instanz der <xref:System.ServiceModel.WSHttpBinding>-Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="738ed-114">This example creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class.</span></span>

2. <span data-ttu-id="738ed-115">Legen Sie die `Mode`-Eigenschaft des Objekts fest, das von der `Security`-Eigenschaft zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="738ed-115">Set the `Mode` property of the object returned by the `Security` property.</span></span>

     [!code-csharp[c_SettingSecurityMode#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#1)]
     [!code-vb[c_SettingSecurityMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#1)]

     <span data-ttu-id="738ed-116">Sie können den Modus auch auf Message festlegen, wie im folgenden Code veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="738ed-116">Alternatively, set the mode to message, as shown in the following code.</span></span>

     [!code-csharp[c_SettingSecurityMode#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#2)]
     [!code-vb[c_SettingSecurityMode#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#2)]

     <span data-ttu-id="738ed-117">Sie können den Modus auch auf TransportWithMessageCredentials festlegen, wie im folgenden Code veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="738ed-117">Or set the mode to transport with message credentials, as shown in the following code.</span></span>

     [!code-csharp[c_SettingSecurityMode#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#3)]
     [!code-vb[c_SettingSecurityMode#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#3)]

3. <span data-ttu-id="738ed-118">Sie können den Modus auch im Konstruktor der Bindung festlegen, wie im folgenden Codebeispiel veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="738ed-118">You can also set the mode in the constructor of the binding, as shown in the following code.</span></span>

     [!code-csharp[c_SettingSecurityMode#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#4)]
     [!code-vb[c_SettingSecurityMode#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#4)]

## <a name="setting-the-clientcredentialtype-property"></a><span data-ttu-id="738ed-119">Festlegen der ClientCredentialType-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="738ed-119">Setting the ClientCredentialType Property</span></span>

<span data-ttu-id="738ed-120">Durch Festlegen des Modus auf einen der drei Werte wird bestimmt, wie Sie die `ClientCredentialType`-Eigenschaft festlegen können.</span><span class="sxs-lookup"><span data-stu-id="738ed-120">Setting the mode to one of the three values determines how you set the `ClientCredentialType` property.</span></span> <span data-ttu-id="738ed-121">Wenn Sie beispielsweise die <xref:System.ServiceModel.WSHttpBinding>-Klasse verwenden, müssen Sie die `Transport`-Eigenschaft der <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>-Klasse auf einen entsprechenden Wert festlegen, wenn der Modus auf <xref:System.ServiceModel.HttpTransportSecurity> festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="738ed-121">For example, using the <xref:System.ServiceModel.WSHttpBinding> class, setting the mode to `Transport` means you must set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property of the <xref:System.ServiceModel.HttpTransportSecurity> class to an appropriate value.</span></span>

### <a name="to-set-the-clientcredentialtype-property-for-transport-mode"></a><span data-ttu-id="738ed-122">So legen Sie die ClientCredentialType-Eigenschaft für den Transport-Modus fest</span><span class="sxs-lookup"><span data-stu-id="738ed-122">To set the ClientCredentialType property for Transport mode</span></span>

1. <span data-ttu-id="738ed-123">Erstellen Sie eine Instanz der Bindung.</span><span class="sxs-lookup"><span data-stu-id="738ed-123">Create an instance of the binding.</span></span>

2. <span data-ttu-id="738ed-124">Legen Sie die `Mode` -Eigenschaft auf `Transport`fest.</span><span class="sxs-lookup"><span data-stu-id="738ed-124">Set the `Mode` property to `Transport`.</span></span>

3. <span data-ttu-id="738ed-125">Legen Sie für die `ClientCredential`-Eigenschaft einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="738ed-125">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="738ed-126">Im folgenden Code wird die Eigenschaft auf `Windows` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="738ed-126">The following code sets the property to `Windows`.</span></span>

     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]

### <a name="to-set-the-clientcredentialtype-property-for-message-mode"></a><span data-ttu-id="738ed-127">So legen Sie die ClientCredentialType-Eigenschaft für den Message-Modus fest</span><span class="sxs-lookup"><span data-stu-id="738ed-127">To set the ClientCredentialType property for Message mode</span></span>

1. <span data-ttu-id="738ed-128">Erstellen Sie eine Instanz der Bindung.</span><span class="sxs-lookup"><span data-stu-id="738ed-128">Create an instance of the binding.</span></span>

2. <span data-ttu-id="738ed-129">Legen Sie die `Mode` -Eigenschaft auf `Message`fest.</span><span class="sxs-lookup"><span data-stu-id="738ed-129">Set the `Mode` property to `Message`.</span></span>

3. <span data-ttu-id="738ed-130">Legen Sie für die `ClientCredential`-Eigenschaft einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="738ed-130">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="738ed-131">Im folgenden Code wird die Eigenschaft auf `Certificate` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="738ed-131">The following code sets the property to `Certificate`.</span></span>

     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]

### <a name="to-set-the-mode-and-clientcredentialtype-property-in-configuration"></a><span data-ttu-id="738ed-132">So legen Sie die Mode-Eigenschaft und die ClientCredentialType-Eigenschaft in der Konfiguration fest</span><span class="sxs-lookup"><span data-stu-id="738ed-132">To set the Mode and ClientCredentialType property in configuration</span></span>

1. <span data-ttu-id="738ed-133">Fügen Sie dem- [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) Element der Konfigurationsdatei ein entsprechendes Bindungs Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="738ed-133">Add an appropriate binding element to the [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="738ed-134">Im folgenden Beispiel wird ein-Element hinzugefügt [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="738ed-134">The following example adds a [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

2. <span data-ttu-id="738ed-135">Fügen Sie ein `<binding>` -Element hinzu, und legen Sie dessen- `name` Attribut auf einen geeigneten Wert fest</span><span class="sxs-lookup"><span data-stu-id="738ed-135">Add a `<binding>` element and set its `name` attribute to an appropriate value.</span></span>

3. <span data-ttu-id="738ed-136">Fügen Sie ein `<security>` -Element hinzu, und legen Sie das- `mode` Attribut auf `Message` , `Transport` oder fest `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="738ed-136">Add a `<security>` element and set the `mode` attribute to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>

4. <span data-ttu-id="738ed-137">Fügen Sie ein `Transport``<transport>`-Element hinzu, und legen Sie das -Attribut auf einen entsprechenden Wert fest, wenn der Modus auf `clientCredential` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="738ed-137">If the mode is set to `Transport`, add a `<transport>` element and set the `clientCredential` attribute to an appropriate value.</span></span>

     <span data-ttu-id="738ed-138">Im folgenden Beispiel wird der Modus auf "`Transport"` festgelegt, und anschließend wird das `clientCredentialType`-Attribut des `<transport>`-Elements auf "`Windows"` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="738ed-138">The following example sets the mode to "`Transport"`, and then sets the `clientCredentialType` attribute of the `<transport>` element to "`Windows"`.</span></span>

    ```xml
    <wsHttpBinding>
    <binding name="TransportSecurity">
        <security mode="Transport" >
           <transport clientCredentialType = "Windows" />
        </security>
    </binding>
    </wsHttpBinding >
    ```

     <span data-ttu-id="738ed-139">Sie können auch den `security mode` auf "`Message"` festlegen und anschließend ein `<"message">`-Element angeben.</span><span class="sxs-lookup"><span data-stu-id="738ed-139">Alternatively, set the `security mode` to "`Message"`, followed by a `<"message">` element.</span></span> <span data-ttu-id="738ed-140">Im folgenden Beispiel wird der `clientCredentialType` auf `Certificate"` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="738ed-140">This example sets the `clientCredentialType` to "`Certificate"`.</span></span>

    ```xml
    <wsHttpBinding>
    <binding name="MessageSecurity">
        <security mode="Message" >
           <message clientCredentialType = "Certificate" />
        </security>
    </binding>
    </wsHttpBinding >
    ```

     <span data-ttu-id="738ed-141">Die Verwendung des <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential>-Werts unterliegt besonderen Bedingungen, die nachfolgend beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="738ed-141">Using the <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> value is a special case, and is explained below.</span></span>

### <a name="using-transportwithmessagecredential"></a><span data-ttu-id="738ed-142">Verwenden von TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="738ed-142">Using TransportWithMessageCredential</span></span>

<span data-ttu-id="738ed-143">Wenn Sie den Sicherheitsmodus auf `TransportWithMessageCredential` festlegen, wird der tatsächliche Mechanismus, der die Sicherheitseinstellungen auf Transportebene bereitstellt, vom Transport bestimmt.</span><span class="sxs-lookup"><span data-stu-id="738ed-143">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="738ed-144">Beispielsweise verwendet das HTTP-Protokoll Secure Sockets Layer (SSL) über HTTP (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="738ed-144">For example, the HTTP protocol uses Secure Sockets Layer (SSL) over HTTP (HTTPS).</span></span> <span data-ttu-id="738ed-145">Daher werden alle Festlegungen der `ClientCredentialType`-Eigenschaft eines Transportsicherheitsobjekts (z. B. <xref:System.ServiceModel.HttpTransportSecurity>) ignoriert.</span><span class="sxs-lookup"><span data-stu-id="738ed-145">Therefore, setting the `ClientCredentialType` property of any transport security object (such as <xref:System.ServiceModel.HttpTransportSecurity>) is ignored.</span></span>  <span data-ttu-id="738ed-146">Dies bedeutet, dass Sie nur den `ClientCredentialType` des Nachrichtensicherheitsobjekts festlegen können (für die `WSHttpBinding`-Bindung, das <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>-Objekt).</span><span class="sxs-lookup"><span data-stu-id="738ed-146">In other words, you can only set the `ClientCredentialType` of the message security object (for the `WSHttpBinding` binding, the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp> object).</span></span>

<span data-ttu-id="738ed-147">Weitere Informationen finden Sie unter Vorgehens [Weise: Verwenden von Transport Sicherheit und Nachrichten Anmelde](./feature-details/how-to-use-transport-security-and-message-credentials.md)Informationen.</span><span class="sxs-lookup"><span data-stu-id="738ed-147">For more information, see [How to: Use Transport Security and Message Credentials](./feature-details/how-to-use-transport-security-and-message-credentials.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="738ed-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="738ed-148">See also</span></span>

- [<span data-ttu-id="738ed-149">Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="738ed-149">How to: Configure a Port with an SSL Certificate</span></span>](./feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="738ed-150">Vorgehensweise: Verwenden von Transportsicherheit und Nachrichtenanmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="738ed-150">How to: Use Transport Security and Message Credentials</span></span>](./feature-details/how-to-use-transport-security-and-message-credentials.md)
- [<span data-ttu-id="738ed-151">Transport Sicherheit</span><span class="sxs-lookup"><span data-stu-id="738ed-151">Transport Security</span></span>](./feature-details/transport-security.md)
- [<span data-ttu-id="738ed-152">Nachrichtensicherheit</span><span class="sxs-lookup"><span data-stu-id="738ed-152">Message Security</span></span>](./feature-details/message-security-in-wcf.md)
- [<span data-ttu-id="738ed-153">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="738ed-153">Security Overview</span></span>](./feature-details/security-overview.md)
- [<span data-ttu-id="738ed-154">Vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="738ed-154">System-Provided Bindings</span></span>](system-provided-bindings.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-wshttpbinding.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-basichttpbinding.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
