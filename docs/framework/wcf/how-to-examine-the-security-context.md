---
title: 'Vorgehensweise: Prüfen des Sicherheitskontexts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceSecurityContext class
- WCF, security
- Claimset class
ms.assetid: 389b5a57-4175-4bc0-ada0-fc750d51149f
author: BrucePerlerMS
ms.openlocfilehash: c2cb1f6d06961546a04b4a132bf9861c925ca421
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47113857"
---
# <a name="how-to-examine-the-security-context"></a><span data-ttu-id="8de64-102">Vorgehensweise: Prüfen des Sicherheitskontexts</span><span class="sxs-lookup"><span data-stu-id="8de64-102">How to: Examine the Security Context</span></span>
<span data-ttu-id="8de64-103">Bei der Programmierung von Windows Communication Foundation (WCF)-Dienste kann dienstsicherheitskontextes Sie Details zu den Clientanmeldeinformationen und Ansprüche verwendet, um die Authentifizierung mit dem Dienst zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="8de64-103">When programming Windows Communication Foundation (WCF) services, the service security context enables you to determine details about the client credentials and claims used to authenticate with the service.</span></span> <span data-ttu-id="8de64-104">Dies geschieht anhand der Eigenschaften der <xref:System.ServiceModel.ServiceSecurityContext>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="8de64-104">This is done by using the properties of the <xref:System.ServiceModel.ServiceSecurityContext> class.</span></span>  
  
 <span data-ttu-id="8de64-105">So können Sie z.&#160;B. die Identität des aktuellen Clients mit der <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A>-Eigenschaft oder der <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>-Eigenschaft abrufen.</span><span class="sxs-lookup"><span data-stu-id="8de64-105">For example, you can retrieve the identity of the current client by using the <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> or the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property.</span></span> <span data-ttu-id="8de64-106">Mit der <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A>-Eigenschaft können Sie ermitteln, ob der Client anonym ist.</span><span class="sxs-lookup"><span data-stu-id="8de64-106">To determine whether the client is anonymous, use the <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A> property.</span></span>  
  
 <span data-ttu-id="8de64-107">Sie können auch bestimmen, welche Ansprüche im Namen des Clients gestellt werden, indem Sie die Auflistung der Ansprüche der <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A>-Eigenschaft durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="8de64-107">You can also determine what claims are being made on behalf of the client by iterating through the collection of claims in the <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> property.</span></span>  
  
### <a name="to-get-the-current-security-context"></a><span data-ttu-id="8de64-108">So rufen Sie den aktuellen Sicherheitskontext ab</span><span class="sxs-lookup"><span data-stu-id="8de64-108">To get the current security context</span></span>  
  
-   <span data-ttu-id="8de64-109">Greifen Sie auf die statische <xref:System.ServiceModel.ServiceSecurityContext.Current%2A>- Eigenschaft zu, um den aktuellen Sicherheitskontext abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8de64-109">Access the static property <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> to get the current security context.</span></span> <span data-ttu-id="8de64-110">Überprüfen Sie eine beliebige der Eigenschaften des aktuellen Kontexts für den Verweis.</span><span class="sxs-lookup"><span data-stu-id="8de64-110">Examine any of the properties of the current context from the reference.</span></span>  
  
### <a name="to-determine-the-identity-of-the-caller"></a><span data-ttu-id="8de64-111">So ermitteln Sie die Identität des Aufrufers</span><span class="sxs-lookup"><span data-stu-id="8de64-111">To determine the identity of the caller</span></span>  
  
1.  <span data-ttu-id="8de64-112">Drucken Sie den Wert der <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A>-Eigenschaft und der <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8de64-112">Print the value of the <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> and <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> properties.</span></span>  
  
### <a name="to-parse-the-claims-of-a-caller"></a><span data-ttu-id="8de64-113">So analysieren Sie die Ansprüche eines Aufrufers</span><span class="sxs-lookup"><span data-stu-id="8de64-113">To parse the claims of a caller</span></span>  
  
1.  <span data-ttu-id="8de64-114">Geben Sie die aktuelle <xref:System.IdentityModel.Policy.AuthorizationContext>-Klasse zurück.</span><span class="sxs-lookup"><span data-stu-id="8de64-114">Return the current <xref:System.IdentityModel.Policy.AuthorizationContext> class.</span></span> <span data-ttu-id="8de64-115">Verwenden Sie die <xref:System.ServiceModel.ServiceSecurityContext.Current%2A>-Eigenschaft, um den aktuellen Dienstsicherheitskontext zurückzugeben, geben Sie dann den `AuthorizationContext` mit der <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A>-Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="8de64-115">Use the <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> property to return the current service security context, then return the `AuthorizationContext` using the <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> property.</span></span>  
  
2.  <span data-ttu-id="8de64-116">Analysieren Sie die Auflistung der <xref:System.IdentityModel.Claims.ClaimSet>-Objekte, die von der <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A>-Eigenschaft der <xref:System.IdentityModel.Policy.AuthorizationContext>-Klasse zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8de64-116">Parse the collection of <xref:System.IdentityModel.Claims.ClaimSet> objects returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8de64-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8de64-117">Example</span></span>  
 <span data-ttu-id="8de64-118">Im folgenden Beispiel werden die Werte der <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>-Eigenschaft und der <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A>-Eigenschaft des aktuellen Sicherheitskontexts und der <xref:System.IdentityModel.Claims.Claim.ClaimType%2A>-Eigenschaft gedruckt sowie der Ressourcenwert des Anspruchs und die <xref:System.IdentityModel.Claims.Claim.Right%2A>-Eigenschaft jedes Anspruchs im aktuellen Sicherheitskontext.</span><span class="sxs-lookup"><span data-stu-id="8de64-118">The following example prints the values of the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> and <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> properties of the current security context and the <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> property, the resource value of the claim, and the <xref:System.IdentityModel.Claims.Claim.Right%2A> property of every claim in the current security context.</span></span>  
  
 [!code-csharp[c_PrincipalPermissionAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#4)]
 [!code-vb[c_PrincipalPermissionAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8de64-119">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="8de64-119">Compiling the Code</span></span>  
 <span data-ttu-id="8de64-120">Der Code verwendet die folgenden Namespaces:</span><span class="sxs-lookup"><span data-stu-id="8de64-120">The code uses the following namespaces:</span></span>  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.IdentityModel.Policy>  
  
-   <xref:System.IdentityModel.Claims>  
  
## <a name="see-also"></a><span data-ttu-id="8de64-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8de64-121">See Also</span></span>  
 [<span data-ttu-id="8de64-122">Sichern von Diensten</span><span class="sxs-lookup"><span data-stu-id="8de64-122">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 [<span data-ttu-id="8de64-123">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="8de64-123">Service Identity and Authentication</span></span>](../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
