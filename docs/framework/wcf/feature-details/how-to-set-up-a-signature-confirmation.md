---
title: 'Vorgehensweise: Einrichten einer Signaturbestätigung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signature confirmation
- WCF, security
ms.assetid: 2424c137-c7c2-4aa9-8d5d-a066e12fefda
ms.openlocfilehash: 9423922753efee7aac32e430f97307c715e43464
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84586916"
---
# <a name="how-to-set-up-a-signature-confirmation"></a><span data-ttu-id="a7a75-102">Vorgehensweise: Einrichten einer Signaturbestätigung</span><span class="sxs-lookup"><span data-stu-id="a7a75-102">How to: Set Up a Signature Confirmation</span></span>

<span data-ttu-id="a7a75-103">*Signatur Bestätigung* ist ein Mechanismus für einen Nachrichten Initiator, mit dem sichergestellt wird, dass eine empfangene Antwort als Antwort auf die ursprüngliche Nachricht des Absenders generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a7a75-103">*Signature confirmation* is a mechanism for a message initiator to ensure that a received reply was generated in response to the sender's original message.</span></span> <span data-ttu-id="a7a75-104">Die Signaturbestätigung wird in der WS-Sicherheit 1.1-Spezifikation definiert.</span><span class="sxs-lookup"><span data-stu-id="a7a75-104">Signature confirmation is defined in the WS-Security 1.1 specification.</span></span> <span data-ttu-id="a7a75-105">Wenn ein Endpunkt WS-Sicherheit 1.0 unterstützt, können Sie keine Signaturbestätigung verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7a75-105">If an endpoint supports WS-Security 1.0, you cannot use signature confirmation.</span></span>

<span data-ttu-id="a7a75-106">In den folgenden Verfahren wird beschrieben, wie die Signaturbestätigung mit <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="a7a75-106">The following procedures specify how to enable signature confirmation using an <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="a7a75-107">Sie können das gleiche Verfahren mit <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7a75-107">You can use the same procedure with a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="a7a75-108">Die Prozedur baut auf den grundlegenden Schritten auf, die unter Gewusst [wie: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="a7a75-108">The procedure builds upon the basic steps found in [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

### <a name="to-enable-signature-confirmation-in-code"></a><span data-ttu-id="a7a75-109">So aktivieren Sie die Signaturbestätigung in Code</span><span class="sxs-lookup"><span data-stu-id="a7a75-109">To enable signature confirmation in code</span></span>

1. <span data-ttu-id="a7a75-110">Erstellen Sie eine Instanz der <xref:System.ServiceModel.Channels.BindingElementCollection>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="a7a75-110">Create an instance of the <xref:System.ServiceModel.Channels.BindingElementCollection> class.</span></span>

2. <span data-ttu-id="a7a75-111">Erstellen Sie eine Instanz der- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="a7a75-111">Create an instance of the  <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> class.</span></span>

3. <span data-ttu-id="a7a75-112">Legen Sie <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="a7a75-112">Set the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> to `true`.</span></span>

4. <span data-ttu-id="a7a75-113">Fügen Sie der Bindungsauflistung das Sicherheitselement hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7a75-113">Add the security element to the binding collection.</span></span>

5. <span data-ttu-id="a7a75-114">Erstellen Sie eine benutzerdefinierte Bindung, wie in Gewusst [wie: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)angegeben.</span><span class="sxs-lookup"><span data-stu-id="a7a75-114">Create a custom binding, as specified in [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

### <a name="to-enable-signature-confirmation-in-configuration"></a><span data-ttu-id="a7a75-115">So aktivieren Sie die Signaturbestätigung in der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="a7a75-115">To enable signature confirmation in configuration</span></span>

1. <span data-ttu-id="a7a75-116">Fügen Sie dem -Abschnitt der Konfigurationsdatei ein -Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7a75-116">Add a `<customBinding>` element to the `<bindings>` section of the configuration file.</span></span>

2. <span data-ttu-id="a7a75-117">Fügen Sie ein `<binding>`-Element hinzu, und legen Sie das Namensattribut auf einen passenden Wert fest.</span><span class="sxs-lookup"><span data-stu-id="a7a75-117">Add a `<binding>` element and set the name attribute to an appropriate value.</span></span>

3. <span data-ttu-id="a7a75-118">Fügen Sie ein entsprechendes Codierungselement hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7a75-118">Add an appropriate encoding element.</span></span> <span data-ttu-id="a7a75-119">Im folgenden Beispiel wird ein `<TextMessageEncoding>`-Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a7a75-119">The following example adds a `<TextMessageEncoding>` element.</span></span>

4. <span data-ttu-id="a7a75-120">Fügen Sie ein untergeordnetes `<security>``requireSignatureConfirmation` fest.</span><span class="sxs-lookup"><span data-stu-id="a7a75-120">Add a `<security>` child element and set the `requireSignatureConfirmation` attribute to `true`.</span></span>

5. <span data-ttu-id="a7a75-121">Optional.</span><span class="sxs-lookup"><span data-stu-id="a7a75-121">Optional.</span></span> <span data-ttu-id="a7a75-122">Fügen Sie ein untergeordnetes Element hinzu, [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) und legen Sie das- `requireSignatureConfirmation` Attribut auf fest, um die Signatur Bestätigung während des Bootstrap `true` zu aktivieren</span><span class="sxs-lookup"><span data-stu-id="a7a75-122">To enable signature confirmation during the bootstrap, add a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) child element and set the `requireSignatureConfirmation` attribute to `true`.</span></span>

6. <span data-ttu-id="a7a75-123">Fügen Sie ein entsprechendes Transportelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7a75-123">Add an appropriate transport element.</span></span> <span data-ttu-id="a7a75-124">Im folgenden Beispiel wird ein hinzugefügt [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) :</span><span class="sxs-lookup"><span data-stu-id="a7a75-124">The following example adds an [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md):</span></span>

    ```xml
    <bindings>
      <customBinding>
        <binding name="SignatureConfirmationBinding">
          <security requireSignatureConfirmation="true">
            <secureConversationBootstrap requireSignatureConfirmation="true" />
              </security>
           <textMessageEncoding />
             <httpTransport />
        </binding>
      </customBinding>
    </bindings>
    ```

## <a name="example"></a><span data-ttu-id="a7a75-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7a75-125">Example</span></span>

<span data-ttu-id="a7a75-126">Der folgende Code erstellt eine Instanz von <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> und legt die <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A>-Eigenschaft auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="a7a75-126">The following code creates an instance of the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and sets the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> property to `true`.</span></span> <span data-ttu-id="a7a75-127">Beachten Sie, dass in diesem Beispiel das im vorangehenden Beispiel gezeigte `<secureConversationBootstrap>`-Element nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a7a75-127">Note that this example does not use the `<secureConversationBootstrap>` element shown in the preceding example.</span></span> <span data-ttu-id="a7a75-128">In diesem Beispiel wird die Signaturbestätigung veranschaulicht, wenn ein Windows-(Kerberos-Protokoll)-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a7a75-128">This example demonstrates signature confirmation when using a Windows (Kerberos protocol) token.</span></span> <span data-ttu-id="a7a75-129">In diesem Fall wird die Signatur des Clients in allen Antworten vom Dienst zurückgegeben und vom Client bestätigt.</span><span class="sxs-lookup"><span data-stu-id="a7a75-129">In this case, the signature of the client is returned in all responses from the service and is confirmed by the client.</span></span>

[!code-csharp[c_SignatureConfirmation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_signatureconfirmation/cs/source.cs#1)]
[!code-vb[c_SignatureConfirmation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_signatureconfirmation/vb/source.vb#1)]

## <a name="see-also"></a><span data-ttu-id="a7a75-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a7a75-130">See also</span></span>

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>
- [<span data-ttu-id="a7a75-131">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="a7a75-131">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="a7a75-132">Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus</span><span class="sxs-lookup"><span data-stu-id="a7a75-132">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
