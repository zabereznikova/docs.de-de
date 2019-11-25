---
title: 'Vorgehensweise: Angeben des Typs von Clientanmeldeinformationen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: df18f89ee18bfa33ecc0aced617d168c805e3515
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74138576"
---
# <a name="how-to-specify-the-client-credential-type"></a><span data-ttu-id="61a16-102">Vorgehensweise: Angeben des Typs von Clientanmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="61a16-102">How to: Specify the Client Credential Type</span></span>
<span data-ttu-id="61a16-103">Nach dem Festlegen eines Sicherheitsmodus (entweder Transport oder Nachricht) haben Sie die Möglichkeit, den Typ der Clientanmeldeinformationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="61a16-103">After setting a security mode (either transport or message), you have the option of setting the client credential type.</span></span> <span data-ttu-id="61a16-104">Diese Eigenschaft gibt an, welchen Anmeldeinformationstyp der Client dem Dienst zur Authentifizierung bereitstellen muss.</span><span class="sxs-lookup"><span data-stu-id="61a16-104">This property specifies what type of credential the client must provide to the service for authentication.</span></span> <span data-ttu-id="61a16-105">Weitere Informationen zum Festlegen des Sicherheitsmodus (ein notwendiger Schritt vor dem Festlegen des Client Anmelde Informations Typs) finden Sie unter [How: Legen Sie den Sicherheitsmodus ](how-to-set-the-security-mode.md) fest.</span><span class="sxs-lookup"><span data-stu-id="61a16-105">For more information about setting the security mode (a necessary step before setting the client credential type), see [How to: Set the Security Mode](how-to-set-the-security-mode.md).</span></span>  
  
### <a name="to-set-the-client-credential-type-in-code"></a><span data-ttu-id="61a16-106">So legen Sie den Clientanmeldeinformationstyp in Code fest</span><span class="sxs-lookup"><span data-stu-id="61a16-106">To set the client credential type in code</span></span>  
  
1. <span data-ttu-id="61a16-107">Erstellen Sie eine Instanz der Bindung, die der Dienst nutzt.</span><span class="sxs-lookup"><span data-stu-id="61a16-107">Create an instance of the binding that the service will use.</span></span> <span data-ttu-id="61a16-108">In diesem Beispiel wird die <xref:System.ServiceModel.WSHttpBinding>-Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="61a16-108">This example uses the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
2. <span data-ttu-id="61a16-109">Legen Sie für die <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>-Eigenschaft einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="61a16-109">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to an appropriate value.</span></span> <span data-ttu-id="61a16-110">In diesem Beispiel wird der Nachrichtenmodus verwendet.</span><span class="sxs-lookup"><span data-stu-id="61a16-110">This example uses the Message mode.</span></span>  
  
3. <span data-ttu-id="61a16-111">Legen Sie für die <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A>-Eigenschaft einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="61a16-111">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="61a16-112">In diesem Beispiel wird die Verwendung der Windows-Authentifizierung (<xref:System.ServiceModel.MessageCredentialType.Windows>) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="61a16-112">This example sets it to use Windows authentication (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span></span>  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a><span data-ttu-id="61a16-113">So legen Sie den Clientanmeldeinformationstyp in der Konfiguration fest</span><span class="sxs-lookup"><span data-stu-id="61a16-113">To set the client credential type in configuration</span></span>  
  
1. <span data-ttu-id="61a16-114">Fügen Sie der Konfigurationsdatei ein >-Element [\<system. Service Model](../configure-apps/file-schema/wcf/system-servicemodel.md) hinzu.</span><span class="sxs-lookup"><span data-stu-id="61a16-114">Add a [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) element to the configuration file.</span></span>  
  
2. <span data-ttu-id="61a16-115">Fügen Sie als untergeordnetes Element eine [\<bindings >](../configure-apps/file-schema/wcf/bindings.md) -Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="61a16-115">As a child element, add a [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
3. <span data-ttu-id="61a16-116">Fügen Sie eine entsprechende Bindung hinzu.</span><span class="sxs-lookup"><span data-stu-id="61a16-116">Add an appropriate binding.</span></span> <span data-ttu-id="61a16-117">In diesem Beispiel wird das [\<wsHttpBinding >](../configure-apps/file-schema/wcf/wshttpbinding.md) -Element verwendet.</span><span class="sxs-lookup"><span data-stu-id="61a16-117">This example uses the [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
4. <span data-ttu-id="61a16-118">Fügen Sie ein [\<binding >](../configure-apps/file-schema/wcf/bindings.md) -Element hinzu, und legen Sie das `name`-Attribut auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="61a16-118">Add a [\<binding>](../configure-apps/file-schema/wcf/bindings.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="61a16-119">In diesem Beispiel wird der Name "SecureBinding" verwendet.</span><span class="sxs-lookup"><span data-stu-id="61a16-119">This example uses the name "SecureBinding".</span></span>  
  
5. <span data-ttu-id="61a16-120">Fügen Sie eine `<security>`-Bindung hinzu.</span><span class="sxs-lookup"><span data-stu-id="61a16-120">Add a `<security>` binding.</span></span> <span data-ttu-id="61a16-121">Legen Sie für das `mode`-Attribut einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="61a16-121">Set the `mode` attribute to an appropriate value.</span></span> <span data-ttu-id="61a16-122">Im folgenden Beispiel wird das Attribut auf `"Message"` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="61a16-122">This example sets it to `"Message"`.</span></span>  
  
6. <span data-ttu-id="61a16-123">Fügen Sie entweder ein `<message>`-Element oder ein`<transport>`-Element hinzu, wie vom Sicherheitsmodus bestimmt.</span><span class="sxs-lookup"><span data-stu-id="61a16-123">Add either a `<message>` or `<transport>` element, as determined by the security mode.</span></span> <span data-ttu-id="61a16-124">Legen Sie für das `clientCredentialType`-Attribut einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="61a16-124">Set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="61a16-125">In diesem Beispiel wird `"Windows"` verwendet.</span><span class="sxs-lookup"><span data-stu-id="61a16-125">This example uses `"Windows"`.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="61a16-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61a16-126">See also</span></span>

- [<span data-ttu-id="61a16-127">Sichern von Diensten</span><span class="sxs-lookup"><span data-stu-id="61a16-127">Securing Services</span></span>](securing-services.md)
- [<span data-ttu-id="61a16-128">Vorgehensweise: Festlegen des Sicherheitsmodus </span><span class="sxs-lookup"><span data-stu-id="61a16-128">How to: Set the Security Mode</span></span>](how-to-set-the-security-mode.md)
