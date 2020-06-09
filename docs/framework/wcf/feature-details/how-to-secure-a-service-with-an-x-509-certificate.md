---
title: 'Vorgehensweise: Sichern eines Diensts mit einem X.509-Zertifikat'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d06c2aa-d0d7-4e5e-ad7e-77416aa1c10b
ms.openlocfilehash: 10d6db63368ee55040f85f922b9483982e8ff264
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596967"
---
# <a name="how-to-secure-a-service-with-an-x509-certificate"></a><span data-ttu-id="2ce45-102">Vorgehensweise: Sichern eines Diensts mit einem X.509-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="2ce45-102">How to: Secure a Service with an X.509 Certificate</span></span>
<span data-ttu-id="2ce45-103">Das Sichern eines Dienstanbieter mit einem X. 509-Zertifikat ist eine grundlegende Technik, die von den meisten Bindungen in Windows Communication Foundation (WCF) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2ce45-103">Securing a service with an X.509 certificate is a basic technique that most bindings in Windows Communication Foundation (WCF) use.</span></span> <span data-ttu-id="2ce45-104">Dieses Thema führt durch die Schritte der Konfiguration eines selbst gehosteten Diensts mit einem X.509-Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="2ce45-104">This topic walks through the steps of configuring a self-hosted service with an X.509 certificate.</span></span>  
  
 <span data-ttu-id="2ce45-105">Eine Voraussetzung ist ein gültiges Zertifikat, das zur Authentifizierung des Diensts verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2ce45-105">A prerequisite is a valid certificate that can be used to authenticate the server.</span></span> <span data-ttu-id="2ce45-106">Das Zertifikat muss von einer vertrauenswürdigen Zertifizierungsstelle zum Server ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2ce45-106">The certificate must be issued to the server by a trusted certificate authority.</span></span> <span data-ttu-id="2ce45-107">Wenn das Zertifikat ungültig ist, vertrauen die Clients, die versuchen, den Dienst zu verwenden, dem Dienst nicht, und es wird keine Verbindung aufgebaut.</span><span class="sxs-lookup"><span data-stu-id="2ce45-107">If the certificate is not valid, any client trying to use the service will not trust the service, and consequently no connection will be made.</span></span> <span data-ttu-id="2ce45-108">Weitere Informationen zur Verwendung von Zertifikaten finden Sie unter [Arbeiten mit Zertifikaten](working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="2ce45-108">For more information about using certificates, see [Working with Certificates](working-with-certificates.md).</span></span>  
  
### <a name="to-configure-a-service-with-a-certificate-using-code"></a><span data-ttu-id="2ce45-109">So konfigurieren Sie einen Dienst mit einem Zertifikat mithilfe von Code</span><span class="sxs-lookup"><span data-stu-id="2ce45-109">To configure a service with a certificate using code</span></span>  
  
1. <span data-ttu-id="2ce45-110">Erstellen Sie den Dienstvertrag und den implementierten Dienst.</span><span class="sxs-lookup"><span data-stu-id="2ce45-110">Create the service contract and the implemented service.</span></span> <span data-ttu-id="2ce45-111">Weitere Informationen finden Sie unter [Entwerfen und Implementieren von Diensten](../designing-and-implementing-services.md).</span><span class="sxs-lookup"><span data-stu-id="2ce45-111">For more information, see [Designing and Implementing Services](../designing-and-implementing-services.md).</span></span>  
  
2. <span data-ttu-id="2ce45-112">Erstellen Sie eine Instanz der <xref:System.ServiceModel.WSHttpBinding>-Klasse, und legen Sie deren Sicherheitsmodus auf <xref:System.ServiceModel.SecurityMode.Message> fest. Dies wird im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2ce45-112">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to <xref:System.ServiceModel.SecurityMode.Message>, as shown in the following code.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#1)]
     [!code-vb[C_SecureWithCertificate#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#1)]  
  
3. <span data-ttu-id="2ce45-113">Erstellen Sie zwei <xref:System.Type>-Variablen, je eine für den Vertragstyp und den implementierten Vertrag. Dies wird im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2ce45-113">Create two <xref:System.Type> variables, one each for the contract type and the implemented contract, as shown in the following code.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#2)]
     [!code-vb[C_SecureWithCertificate#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#2)]  
  
4. <span data-ttu-id="2ce45-114">Erstellen Sie eine Instanz der <xref:System.Uri>-Klasse für die Basisadresse des Diensts.</span><span class="sxs-lookup"><span data-stu-id="2ce45-114">Create an instance of the <xref:System.Uri> class for the base address of the service.</span></span> <span data-ttu-id="2ce45-115">Da den `WSHttpBinding` http-Transport verwendet, muss der Uniform Resource Identifier (URI) mit diesem Schema beginnen, oder Windows Communication Foundation (WCF) löst eine Ausnahme aus, wenn der Dienst geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="2ce45-115">Because the `WSHttpBinding` uses the HTTP transport, the Uniform Resource Identifier (URI) must begin with that schema, or Windows Communication Foundation (WCF) will throw an exception when the service is opened.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#3)]
     [!code-vb[C_SecureWithCertificate#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#3)]  
  
5. <span data-ttu-id="2ce45-116">Erstellen Sie eine neue Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse mit der Variablen des implementierten Vertragstyps und dem URI.</span><span class="sxs-lookup"><span data-stu-id="2ce45-116">Create a new instance of the <xref:System.ServiceModel.ServiceHost> class with the implemented contract type variable and the URI.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#4)]
     [!code-vb[C_SecureWithCertificate#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#4)]  
  
6. <span data-ttu-id="2ce45-117">Fügen Sie einen <xref:System.ServiceModel.Description.ServiceEndpoint> zum Dienst hinzu, indem Sie die <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ce45-117">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> to the service using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span> <span data-ttu-id="2ce45-118">Übergeben Sie den Vertrag, die Bindung und eine Endpunktadresse an den Konstruktor. Dies wird im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2ce45-118">Pass the contract, binding, and an endpoint address to the constructor, as shown in the following code.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#5)]
     [!code-vb[C_SecureWithCertificate#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#5)]  
  
7. <span data-ttu-id="2ce45-119">Optional.</span><span class="sxs-lookup"><span data-stu-id="2ce45-119">Optional.</span></span> <span data-ttu-id="2ce45-120">Um Metadaten vom Dienst abzufragen, erstellen Sie ein neues <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Objekt und legen Sie die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A>-Eigenschaft auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="2ce45-120">To retrieve metadata from the service, create a new <xref:System.ServiceModel.Description.ServiceMetadataBehavior> object and set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#6)]
     [!code-vb[C_SecureWithCertificate#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#6)]  
  
8. <span data-ttu-id="2ce45-121">Verwenden Sie die <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>-Methode der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>-Klasse, um das gültige Zertifikat zum Dienst hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2ce45-121">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to add the valid certificate to the service.</span></span> <span data-ttu-id="2ce45-122">Die Methode kann eine von diversen Methoden nutzen, um ein Zertifikat zu suchen.</span><span class="sxs-lookup"><span data-stu-id="2ce45-122">The method can use one of several methods to find a certificate.</span></span> <span data-ttu-id="2ce45-123">In diesem Beispiel wird die <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectName>-Enumeration verwendet.</span><span class="sxs-lookup"><span data-stu-id="2ce45-123">This example uses the <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectName> enumeration.</span></span> <span data-ttu-id="2ce45-124">Die Enumeration gibt an, dass der gelieferte Wert der Name der Entität ist, an die das Zertifikat herausgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="2ce45-124">The enumeration specifies that the supplied value is the name of the entity that the certificate was issued to.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#7)]
     [!code-vb[C_SecureWithCertificate#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#7)]  
  
9. <span data-ttu-id="2ce45-125">Rufen Sie die <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>-Methode auf, um die Dienstüberwachung zu starten.</span><span class="sxs-lookup"><span data-stu-id="2ce45-125">Call the <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> method to start the service listening.</span></span> <span data-ttu-id="2ce45-126">Sollten Sie eine Konsolenanwendung erstellen, rufen Sie die <xref:System.Console.ReadLine%2A>-Methode auf, um den Dienst im Überwachungsstatus zu halten.</span><span class="sxs-lookup"><span data-stu-id="2ce45-126">If you are creating a console application, call the <xref:System.Console.ReadLine%2A> method to keep the service in the listening state.</span></span>  
  
     [!code-csharp[C_SecureWithCertificate#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#8)]
     [!code-vb[C_SecureWithCertificate#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="2ce45-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2ce45-127">Example</span></span>  
 <span data-ttu-id="2ce45-128">Im folgenden Beispiel wird die <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>-Methode verwendet, um einen Dienst mit einem X.509-Zertifikat zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2ce45-128">The following example uses the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method to configure a service with an X.509 certificate.</span></span>  
  
 [!code-csharp[C_SecureWithCertificate#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewithcertificate/cs/source.cs#9)]
 [!code-vb[C_SecureWithCertificate#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewithcertificate/vb/source.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2ce45-129">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2ce45-129">Compiling the Code</span></span>  
 <span data-ttu-id="2ce45-130">Die folgenden Namespaces sind zum Kompilieren des Codes erforderlich:</span><span class="sxs-lookup"><span data-stu-id="2ce45-130">The following namespaces are required to compile the code:</span></span>  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.Web.Services.Description>  
  
- <xref:System.Security.Cryptography.X509Certificates>  
  
- <xref:System.Runtime.Serialization>  
  
## <a name="see-also"></a><span data-ttu-id="2ce45-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2ce45-131">See also</span></span>

- [<span data-ttu-id="2ce45-132">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="2ce45-132">Working with Certificates</span></span>](working-with-certificates.md)
