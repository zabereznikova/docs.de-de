---
title: 'Vorgehensweise: Erstellen unterstützender Anmeldeinformationen'
ms.date: 03/30/2017
ms.assetid: d0952919-8bb4-4978-926c-9cc108f89806
ms.openlocfilehash: 1e11da11de68b1d3e24115387ec61ad22ec031b1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286304"
---
# <a name="how-to-create-a-supporting-credential"></a><span data-ttu-id="25a12-102">Vorgehensweise: Erstellen unterstützender Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="25a12-102">How to: Create a Supporting Credential</span></span>

<span data-ttu-id="25a12-103">Sie können über ein benutzerdefiniertes Sicherheitsschema verfügen, für das mehrere Anmeldeinformationen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="25a12-103">It is possible to have a custom security scheme that requires more than one credential.</span></span> <span data-ttu-id="25a12-104">Beispielsweise kann ein Dienst vom Client nicht nur den Benutzernamen und das Kennwort fordern, sondern auch Anmeldeinformationen, die belegen, dass der Client älter als 18 Jahre ist.</span><span class="sxs-lookup"><span data-stu-id="25a12-104">For example, a service may demand from the client not just a user name and password, but also a credential that proves the client is over the age of 18.</span></span> <span data-ttu-id="25a12-105">Die zweiten Anmelde Informationen sind *unterstützende* Anmelde Informationen.</span><span class="sxs-lookup"><span data-stu-id="25a12-105">The second credential is a *supporting credential*.</span></span> <span data-ttu-id="25a12-106">In diesem Thema wird erläutert, wie solche Anmelde Informationen in einem Windows Communication Foundation (WCF)-Client implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="25a12-106">This topic explains how to implement such credentials in an Windows Communication Foundation (WCF) client.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="25a12-107">Die Spezifikation für unterstützende Anmeldeinformationen ist Teil der WS-SecurityPolicy-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="25a12-107">The specification for supporting credentials is part of the WS-SecurityPolicy specification.</span></span> <span data-ttu-id="25a12-108">Weitere Informationen finden Sie unter [Webdienstesicherheit Spezifikationen](/previous-versions/dotnet/articles/ms951273(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="25a12-108">For more information, see [Web Services Security Specifications](/previous-versions/dotnet/articles/ms951273(v=msdn.10)).</span></span>  
  
## <a name="supporting-tokens"></a><span data-ttu-id="25a12-109">Unterstützende Token</span><span class="sxs-lookup"><span data-stu-id="25a12-109">Supporting Tokens</span></span>  

 <span data-ttu-id="25a12-110">Kurz gesagt: Wenn Sie Nachrichten Sicherheit verwenden, wird immer eine *primäre* Anmelde Information verwendet, um die Nachricht zu sichern (z. b. ein X. 509-Zertifikat oder ein Kerberos-Ticket).</span><span class="sxs-lookup"><span data-stu-id="25a12-110">In brief, when you use message security, a *primary credential* is always used to secure the message (for example, an X.509 certificate or a Kerberos ticket).</span></span>  
  
 <span data-ttu-id="25a12-111">Gemäß der Definition durch die Spezifikation verwendet eine Sicherheitsbindung *Token* , um den Nachrichtenaustausch zu sichern.</span><span class="sxs-lookup"><span data-stu-id="25a12-111">As defined by the specification, a security binding uses *tokens* to secure the message exchange.</span></span> <span data-ttu-id="25a12-112">Ein *Token* ist eine Darstellung von Sicherheits Anmelde Informationen.</span><span class="sxs-lookup"><span data-stu-id="25a12-112">A *token* is a representation of a security credential.</span></span>  
  
 <span data-ttu-id="25a12-113">Die Sicherheitsbindung verwendet zum Erstellen einer Signatur ein in ihrer Richtlinie identifiziertes primäres Token.</span><span class="sxs-lookup"><span data-stu-id="25a12-113">The security binding uses a primary token identified in the security binding policy to create a signature.</span></span> <span data-ttu-id="25a12-114">Diese Signatur wird als *Nachrichten Signatur* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="25a12-114">This signature is referred to as the *message signature*.</span></span>  
  
 <span data-ttu-id="25a12-115">Es können zusätzliche Token angegeben werden, um die von dem der Nachrichtensignatur zugeordneten Token bereitgestellten Ansprüche zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="25a12-115">Additional tokens can be specified to augment the claims provided by the token associated with the message signature.</span></span>  
  
## <a name="endorsing-signing-and-encrypting"></a><span data-ttu-id="25a12-116">Unterzeichnen, Signieren und Verschlüsseln</span><span class="sxs-lookup"><span data-stu-id="25a12-116">Endorsing, Signing, and Encrypting</span></span>  

 <span data-ttu-id="25a12-117">Eine unterstützende Anmelde Informationen führt dazu, dass ein *unterstützendes Token* innerhalb der Nachricht übertragen wird</span><span class="sxs-lookup"><span data-stu-id="25a12-117">A supporting credential results in a *supporting token* transmitted inside the message.</span></span> <span data-ttu-id="25a12-118">Die WS-SecurityPolicy-Spezifikation definiert vier Methoden zum Anhängen eines unterstützenden Tokens an die Nachricht, wie in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="25a12-118">The WS-SecurityPolicy specification defines four ways to attach a supporting token to the message, as described in the following table.</span></span>  
  
|<span data-ttu-id="25a12-119">Zweck</span><span class="sxs-lookup"><span data-stu-id="25a12-119">Purpose</span></span>|<span data-ttu-id="25a12-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="25a12-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="25a12-121">Signiert</span><span class="sxs-lookup"><span data-stu-id="25a12-121">Signed</span></span>|<span data-ttu-id="25a12-122">Das unterstützende Token ist im Sicherheitsheader enthalten und wird durch die Nachrichtensignatur signiert.</span><span class="sxs-lookup"><span data-stu-id="25a12-122">The supporting token is included in the security header and is signed by the message signature.</span></span>|  
|<span data-ttu-id="25a12-123">Unterzeichnend</span><span class="sxs-lookup"><span data-stu-id="25a12-123">Endorsing</span></span>|<span data-ttu-id="25a12-124">Ein unter zeichnendes *Token* signiert die Nachrichten Signatur.</span><span class="sxs-lookup"><span data-stu-id="25a12-124">An *endorsing token* signs the message signature.</span></span>|  
|<span data-ttu-id="25a12-125">Signiert und unterzeichnend</span><span class="sxs-lookup"><span data-stu-id="25a12-125">Signed and Endorsing</span></span>|<span data-ttu-id="25a12-126">Signierte, unterzeichnende Token signieren das gesamte aus der Nachrichtensignatur erstellte `ds:Signature`-Element und werden selbst durch die Nachrichtensignatur signiert; d. h., beide Token (das für die Nachrichtensignatur verwendete Token und das signierte unterzeichnende Token) signieren einander.</span><span class="sxs-lookup"><span data-stu-id="25a12-126">Signed, endorsing tokens sign the entire `ds:Signature` element produced from the message signature and are themselves signed by that message signature; that is, both tokens (the token used for the message signature and the signed endorsing token) sign each other.</span></span>|  
|<span data-ttu-id="25a12-127">Signiert und verschlüsselnd</span><span class="sxs-lookup"><span data-stu-id="25a12-127">Signed and Encrypting</span></span>|<span data-ttu-id="25a12-128">Signierte, verschlüsselte unterstützende Token sind signierte unterstützende Token, die beim Anzeigen im `wsse:SecurityHeader` auch verschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="25a12-128">Signed, encrypted supporting tokens are signed supporting tokens that are also encrypted when they appear in the `wsse:SecurityHeader`.</span></span>|  
  
## <a name="programming-supporting-credentials"></a><span data-ttu-id="25a12-129">Programmieren von unterstützenden Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="25a12-129">Programming Supporting Credentials</span></span>  

 <span data-ttu-id="25a12-130">Um einen Dienst zu erstellen, der unterstützende Token verwendet, müssen Sie einen erstellen [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="25a12-130">To create a service that uses supporting tokens you must create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md).</span></span> <span data-ttu-id="25a12-131">(Weitere Informationen finden Sie unter Gewusst [wie: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).)</span><span class="sxs-lookup"><span data-stu-id="25a12-131">(For more information, see [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).)</span></span>  
  
 <span data-ttu-id="25a12-132">Der erste Schritt beim Erstellen einer benutzerdefinierten Bindung ist das Erstellen eines Sicherheitsbindungselements, das einer der folgenden drei Typen sein kann:</span><span class="sxs-lookup"><span data-stu-id="25a12-132">The first step when creating a custom binding is to create a security binding element, which can be one of three types:</span></span>  
  
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
  
- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
  
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 <span data-ttu-id="25a12-133">Alle Klassen erben vom <xref:System.ServiceModel.Channels.SecurityBindingElement>, das vier relevante Eigenschaften umfasst:</span><span class="sxs-lookup"><span data-stu-id="25a12-133">All classes inherit from the <xref:System.ServiceModel.Channels.SecurityBindingElement>, which includes four relevant properties:</span></span>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.EndpointSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OperationSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalEndpointSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalOperationSupportingTokenParameters%2A>  
  
#### <a name="scopes"></a><span data-ttu-id="25a12-134">Bereiche</span><span class="sxs-lookup"><span data-stu-id="25a12-134">Scopes</span></span>  

 <span data-ttu-id="25a12-135">Für unterstützende Anmeldeinformationen existieren vier Bereiche:</span><span class="sxs-lookup"><span data-stu-id="25a12-135">Two scopes exist for supporting credentials:</span></span>  
  
- <span data-ttu-id="25a12-136">*Endpunkt unterstützende Token* unterstützen alle Vorgänge eines Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="25a12-136">*Endpoint supporting tokens* support all operations of an endpoint.</span></span> <span data-ttu-id="25a12-137">Die Anmeldeinformationen, die das unterstützende Token darstellt, können beim Aufrufen eines beliebigen Endpunktvorgangs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="25a12-137">That is, the credential that the supporting token represents can be used whenever any endpoint operations are invoked.</span></span>  
  
- <span data-ttu-id="25a12-138">Unter *stützende Token* unterstützen nur einen bestimmten Endpunkt Vorgang.</span><span class="sxs-lookup"><span data-stu-id="25a12-138">*Operation supporting tokens* support only a specific endpoint operation.</span></span>  
  
 <span data-ttu-id="25a12-139">Wie durch die Eigenschaftennamen angegeben, können unterstützende Anmeldeinformationen erforderlich oder optional sein.</span><span class="sxs-lookup"><span data-stu-id="25a12-139">As indicated by the property names, supporting credentials can be either required or optional.</span></span> <span data-ttu-id="25a12-140">Die unterstützenden Anmeldeinformationen werden verwendet, wenn sie vorhanden, aber nicht erforderlich sind; die Authentifizierung schlägt jedoch nicht fehl, wenn sie nicht vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="25a12-140">That is, if the supporting credential is used if it is present, although it is not necessary, but the authentication will not fail if it is not present.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="25a12-141">Prozeduren</span><span class="sxs-lookup"><span data-stu-id="25a12-141">Procedures</span></span>  
  
#### <a name="to-create-a-custom-binding-that-includes-supporting-credentials"></a><span data-ttu-id="25a12-142">So erstellen Sie eine benutzerdefinierte Bindung, die unterstützende Anmeldeinformationen enthält</span><span class="sxs-lookup"><span data-stu-id="25a12-142">To create a custom binding that includes supporting credentials</span></span>  
  
1. <span data-ttu-id="25a12-143">Erstellen Sie ein Sicherheitsbindungselement.</span><span class="sxs-lookup"><span data-stu-id="25a12-143">Create a security binding element.</span></span> <span data-ttu-id="25a12-144">Im nachfolgenden Beispiel wird ein <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> mit dem `UserNameForCertificate`-Authentifizierungsmodus erstellt.</span><span class="sxs-lookup"><span data-stu-id="25a12-144">The example below creates a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> with the `UserNameForCertificate` authentication mode.</span></span> <span data-ttu-id="25a12-145">Verwenden Sie die <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="25a12-145">Use the <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A> method.</span></span>  
  
2. <span data-ttu-id="25a12-146">Fügen Sie den unterstützenden Parameter der von der entsprechenden Eigenschaft (`Endorsing`, `Signed`, `SignedEncrypted` oder `SignedEndorsed`) zurückgegebenen Auflistung von Typen hinzu.</span><span class="sxs-lookup"><span data-stu-id="25a12-146">Add the supporting parameter to the collection of types returned by the appropriate property (`Endorsing`, `Signed`, `SignedEncrypted`, or `SignedEndorsed`).</span></span> <span data-ttu-id="25a12-147">Die Typen im <xref:System.ServiceModel.Security.Tokens>-Namespace umfassen häufig verwendete Typen wie die <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.</span><span class="sxs-lookup"><span data-stu-id="25a12-147">The types in the <xref:System.ServiceModel.Security.Tokens> namespace include commonly used types, such as the <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25a12-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="25a12-148">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="25a12-149">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="25a12-149">Description</span></span>  

 <span data-ttu-id="25a12-150">Im folgenden Beispiel wird eine Instanz des <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> erstellt und eine Instanz der <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters>-Klasse der von der unterzeichenden Eigenschaft zurückgegebenen Auflistung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="25a12-150">The following example creates an instance of the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and adds an instance of the <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> class to the collection the Endorsing property returned.</span></span>  
  
### <a name="code"></a><span data-ttu-id="25a12-151">Code</span><span class="sxs-lookup"><span data-stu-id="25a12-151">Code</span></span>  

 [!code-csharp[c_SupportingCredential#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_supportingcredential/cs/source.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="25a12-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25a12-152">See also</span></span>

- [<span data-ttu-id="25a12-153">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="25a12-153">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
