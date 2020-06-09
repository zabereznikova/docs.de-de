---
title: 'Vorgehensweise: Sichern von Metadatenendpunkten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9f71b6ae-737c-4382-8d89-0a7b1c7e182b
ms.openlocfilehash: c5efd921d3826ef814bf45d6895255981101d992
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592956"
---
# <a name="how-to-secure-metadata-endpoints"></a><span data-ttu-id="c4654-102">Vorgehensweise: Sichern von Metadatenendpunkten</span><span class="sxs-lookup"><span data-stu-id="c4654-102">How to: Secure Metadata Endpoints</span></span>

<span data-ttu-id="c4654-103">Metadaten für einen Dienst können vertrauliche Informationen über Ihre Anwendung enthalten, die böswillige Benutzer für ihre Zwecke missbrauchen können.</span><span class="sxs-lookup"><span data-stu-id="c4654-103">Metadata for a service can contain sensitive information about your application that a malicious user can leverage.</span></span> <span data-ttu-id="c4654-104">Die Consumer Ihres Diensts benötigen möglicherweise auch einen sicheren Mechanismus für den Zugriff auf Metadaten über Ihren Dienst.</span><span class="sxs-lookup"><span data-stu-id="c4654-104">Consumers of your service may also require a secure mechanism for obtaining metadata about your service.</span></span> <span data-ttu-id="c4654-105">Deshalb ist es manchmal notwendig, die Metadaten mit einem sicheren Endpunkt zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="c4654-105">Therefore, it is sometimes necessary to publish your metadata using a secure endpoint.</span></span>

<span data-ttu-id="c4654-106">Metadatenendpunkte werden in der Regel mithilfe der Standard Sicherheitsmechanismen geschützt, die in Windows Communication Foundation (WCF) zum Sichern von Anwendungs Endpunkten definiert sind.</span><span class="sxs-lookup"><span data-stu-id="c4654-106">Metadata endpoints are generally secured using the standard security mechanisms defined in Windows Communication Foundation (WCF) for securing application endpoints.</span></span> <span data-ttu-id="c4654-107">Weitere Informationen finden Sie unter [Sicherheitsübersicht](security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c4654-107">For more information, see [Security Overview](security-overview.md).</span></span>

<span data-ttu-id="c4654-108">In diesem Thema sind die Schritte zur Erstellung eines Endpunkts beschrieben, der durch ein Verbunddienst-SSL-Zertifikat gesichert ist, also anders ausgedrückt: die Schritte zur Erstellung eines HTTPS-Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="c4654-108">This topic walks through the steps to create an endpoint secured by a Secure Sockets Layer (SSL) certificate or, in other words, an HTTPS endpoint.</span></span>

### <a name="to-create-a-secure-https-get-metadata-endpoint-in-code"></a><span data-ttu-id="c4654-109">So erstellen Sie einen sicheren HTTPS-GET-Metadatenendpunkt in Code</span><span class="sxs-lookup"><span data-stu-id="c4654-109">To create a secure HTTPS GET metadata endpoint in code</span></span>

1. <span data-ttu-id="c4654-110">Konfigurieren Sie einen Anschluss mit einem entsprechenden X.509-Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="c4654-110">Configure a port with an appropriate X.509 certificate.</span></span> <span data-ttu-id="c4654-111">Das Zertifikat muss von einer vertrauenswürdigen Stelle stammen und für die Verwendung zum Zwecke der Dienstautorisierung beabsichtigt sein.</span><span class="sxs-lookup"><span data-stu-id="c4654-111">The certificate must come from a trusted authority, and it must have an intended use of "Service Authorization."</span></span> <span data-ttu-id="c4654-112">Sie müssen das Tool HttpCfg.exe verwenden, um das Zertifikat an den Anschluss anzufügen.</span><span class="sxs-lookup"><span data-stu-id="c4654-112">You must use the HttpCfg.exe tool to attach the certificate to the port.</span></span> <span data-ttu-id="c4654-113">Weitere Informationen finden [Sie unter Vorgehensweise: Konfigurieren eines Ports mit einem SSL-Zertifikat](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="c4654-113">See [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c4654-114">Der Betreff des Zertifikats oder das DNS (Domain Name System) muss mit dem Namen des Computers übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="c4654-114">The subject of the certificate or its Domain Name System (DNS) must match the name of the computer.</span></span> <span data-ttu-id="c4654-115">Dies ist deshalb wichtig, weil einer der ersten Schritte des HTTPS-Mechanismus darin besteht, zu überprüfen, ob das Zertifikat für denselben URI (Uniform Resource Identifier) ausgestellt wurde wie die Adresse, von der aus es aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c4654-115">This is essential because one of the first steps the HTTPS mechanism performs is to check that the certificate is issued to the same Uniform Resource Identifier (URI) as the address upon which it is invoked.</span></span>

2. <span data-ttu-id="c4654-116">Erstellen Sie eine neue Instanz der <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="c4654-116">Create a new instance of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class.</span></span>

3. <span data-ttu-id="c4654-117">Legen Sie die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>-Eigenschaft der <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Klasse auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="c4654-117">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> property of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class to `true`.</span></span>

4. <span data-ttu-id="c4654-118">Legen Sie für die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>-Eigenschaft einen geeigneten URL fest.</span><span class="sxs-lookup"><span data-stu-id="c4654-118">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> property to an appropriate URL.</span></span> <span data-ttu-id="c4654-119">Beachten Sie, dass die URL mit dem Schema beginnen muss, wenn Sie eine absolute Adresse angeben `https://` .</span><span class="sxs-lookup"><span data-stu-id="c4654-119">Note that if you specify an absolute address, the URL must begin with the scheme `https://`.</span></span> <span data-ttu-id="c4654-120">Wenn Sie eine relative Adresse angeben, müssen Sie eine HTTPS-Basisadresse für den Diensthost angeben.</span><span class="sxs-lookup"><span data-stu-id="c4654-120">If you specify a relative address, you must supply an HTTPS base address for your service host.</span></span> <span data-ttu-id="c4654-121">Wenn diese Eigenschaft nicht festgelegt ist, lautet die Standardadresse "" oder befindet sich direkt an der HTTPS-Basisadresse für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="c4654-121">If this property is not set, the default address is "", or directly at the HTTPS base address for the service.</span></span>

5. <span data-ttu-id="c4654-122">Fügen Sie der Verhaltenssammlung die Instanz hinzu, die von der <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>-Eigenschaft der <xref:System.ServiceModel.Description.ServiceDescription>-Klasse zurückgegeben wird, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c4654-122">Add the instance to the behaviors collection that the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> property of the <xref:System.ServiceModel.Description.ServiceDescription> class returns, as shown in the following code.</span></span>

    [!code-csharp[c_HowToSecureEndpoint#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#1)]
    [!code-vb[c_HowToSecureEndpoint#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#1)]

### <a name="to-create-a-secure-https-get-metadata-endpoint-in-configuration"></a><span data-ttu-id="c4654-123">So erstellen Sie einen sicheren HTTPS-GET-Metadatenendpunkt in der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c4654-123">To create a secure HTTPS GET metadata endpoint in configuration</span></span>

1. <span data-ttu-id="c4654-124">Fügen Sie [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) dem- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) Element der Konfigurationsdatei für den Dienst ein-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="c4654-124">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element of the configuration file for your service.</span></span>

2. <span data-ttu-id="c4654-125">Fügen Sie [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) dem-Element ein-Element hinzu [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) .</span><span class="sxs-lookup"><span data-stu-id="c4654-125">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) element to the [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

3. <span data-ttu-id="c4654-126">Fügen Sie [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) dem-Element ein-Element hinzu `<serviceBehaviors>` .</span><span class="sxs-lookup"><span data-stu-id="c4654-126">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element to the `<serviceBehaviors>` element.</span></span>

4. <span data-ttu-id="c4654-127">Legen Sie einen angemessenen Wert für das `name`-Attribut des `<behavior>`-Elements fest.</span><span class="sxs-lookup"><span data-stu-id="c4654-127">Set the `name` attribute of the `<behavior>` element to an appropriate value.</span></span> <span data-ttu-id="c4654-128">Das `name`-Attribut ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c4654-128">The `name` attribute is required.</span></span> <span data-ttu-id="c4654-129">Das nachstehende Beispiel verwendet den Wert `mySvcBehavior`.</span><span class="sxs-lookup"><span data-stu-id="c4654-129">The example below uses the value `mySvcBehavior`.</span></span>

5. <span data-ttu-id="c4654-130">Fügen Sie [\<serviceMetadata>](../../configure-apps/file-schema/wcf/servicemetadata.md) dem- `<behavior>` Element einen hinzu.</span><span class="sxs-lookup"><span data-stu-id="c4654-130">Add a [\<serviceMetadata>](../../configure-apps/file-schema/wcf/servicemetadata.md) to the `<behavior>` element.</span></span>

6. <span data-ttu-id="c4654-131">Legen Sie das `httpsGetEnabled`-Attribut des `<serviceMetadata>`-Elements auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="c4654-131">Set the `httpsGetEnabled` attribute of the `<serviceMetadata>` element to `true`.</span></span>

7. <span data-ttu-id="c4654-132">Legen Sie einen angemessenen Wert für das `httpsGetUrl`-Attribut des `<serviceMetadata>`-Elements fest.</span><span class="sxs-lookup"><span data-stu-id="c4654-132">Set the `httpsGetUrl` attribute of the `<serviceMetadata>` element to an appropriate value.</span></span> <span data-ttu-id="c4654-133">Beachten Sie, dass die URL mit dem Schema beginnen muss, wenn Sie eine absolute Adresse angeben `https://` .</span><span class="sxs-lookup"><span data-stu-id="c4654-133">Note that if you specify an absolute address, the URL must begin with the scheme `https://`.</span></span> <span data-ttu-id="c4654-134">Wenn Sie eine relative Adresse angeben, müssen Sie eine HTTPS-Basisadresse für den Diensthost angeben.</span><span class="sxs-lookup"><span data-stu-id="c4654-134">If you specify a relative address, you must supply an HTTPS base address for your service host.</span></span> <span data-ttu-id="c4654-135">Wenn diese Eigenschaft nicht festgelegt ist, lautet die Standardadresse "" oder befindet sich direkt an der HTTPS-Basisadresse für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="c4654-135">If this property is not set, the default address is "", or directly at the HTTPS base address for the service.</span></span>

8. <span data-ttu-id="c4654-136">Wenn Sie das-Verhalten mit einem-Dienst verwenden möchten, legen Sie das- `behaviorConfiguration` Attribut des- [\<service>](../../configure-apps/file-schema/wcf/service.md) Elements auf den Wert des Name-Attributs des Behavior-Elements fest.</span><span class="sxs-lookup"><span data-stu-id="c4654-136">To use the behavior with a service, set the `behaviorConfiguration` attribute of the [\<service>](../../configure-apps/file-schema/wcf/service.md) element to the value of the name attribute of the behavior element.</span></span> <span data-ttu-id="c4654-137">Der folgende Konfigurationscode zeigt ein vollständiges Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c4654-137">The following configuration code shows a complete example.</span></span>

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
     <system.serviceModel>
      <behaviors>
       <serviceBehaviors>
        <behavior name="mySvcBehavior">
         <serviceMetadata httpsGetEnabled="true"
              httpsGetUrl="https://localhost:8036/calcMetadata" />
        </behavior>
       </serviceBehaviors>
      </behaviors>
     <services>
      <service behaviorConfiguration="mySvcBehavior"
            name="Microsoft.Security.Samples.Calculator">
       <endpoint address="http://localhost:8037/ServiceModelSamples/calculator"
       binding="wsHttpBinding" bindingConfiguration=""
       contract="Microsoft.Security.Samples.ICalculator" />
      </service>
     </services>
    </system.serviceModel>
    </configuration>
    ```

## <a name="example"></a><span data-ttu-id="c4654-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c4654-138">Example</span></span>

<span data-ttu-id="c4654-139">Im folgenden Beispiel wird eine Instanz einer <xref:System.ServiceModel.ServiceHost>-Klasse erstellt und ein Endpunkt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c4654-139">The following example creates an instance of a <xref:System.ServiceModel.ServiceHost> class and adds an endpoint.</span></span> <span data-ttu-id="c4654-140">Anschließend erstellt der Code eine Instanz der <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Klasse und legt die Eigenschaften zur Erstellung eines sicheren Punkts für den Metadatenaustausch fest.</span><span class="sxs-lookup"><span data-stu-id="c4654-140">The code then creates an instance of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class and sets the properties to create a secure metadata exchange point.</span></span>

[!code-csharp[c_HowToSecureEndpoint#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#0)]
[!code-vb[c_HowToSecureEndpoint#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#0)]

## <a name="compiling-the-code"></a><span data-ttu-id="c4654-141">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c4654-141">Compiling the Code</span></span>

<span data-ttu-id="c4654-142">Das Codebeispiel verwendet die folgenden Namespaces:</span><span class="sxs-lookup"><span data-stu-id="c4654-142">The code example uses the following namespaces:</span></span>

- <xref:System.ServiceModel?displayProperty=nameWithType>

- <xref:System.ServiceModel.Description?displayProperty=nameWithType>

## <a name="see-also"></a><span data-ttu-id="c4654-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c4654-143">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>
- [<span data-ttu-id="c4654-144">Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="c4654-144">How to: Configure a Port with an SSL Certificate</span></span>](how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="c4654-145">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="c4654-145">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="c4654-146">Sicherheitsüberlegungen für Metadaten</span><span class="sxs-lookup"><span data-stu-id="c4654-146">Security Considerations with Metadata</span></span>](security-considerations-with-metadata.md)
- [<span data-ttu-id="c4654-147">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="c4654-147">Securing Services and Clients</span></span>](securing-services-and-clients.md)
