---
title: 'Vorgehensweise: Verwenden mehrerer Sicherheitstokens desselben Typs'
ms.date: 03/30/2017
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 25afbb268a0ef7772585a0f3829b56f135758b61
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2018
ms.locfileid: "44507918"
---
# <a name="how-to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="df882-102">Vorgehensweise: Verwenden mehrerer Sicherheitstokens desselben Typs</span><span class="sxs-lookup"><span data-stu-id="df882-102">How to: Use Multiple Security Tokens of the Same Type</span></span>
-   <span data-ttu-id="df882-103">In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]&#160;3.0 enthielt eine Clientnachricht nur ein Token eines beliebigen angegebenen Typs.</span><span class="sxs-lookup"><span data-stu-id="df882-103">In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0, a client message only contained one token of any given type.</span></span> <span data-ttu-id="df882-104">Jetzt können Clientnachrichten mehrere Token eines Typs enthalten.</span><span class="sxs-lookup"><span data-stu-id="df882-104">Now client messages can contain multiple tokens of a type.</span></span> <span data-ttu-id="df882-105">In diesem Thema wird das Einfügen mehrerer Token desselben Typs in eine Clientnachricht erläutert.</span><span class="sxs-lookup"><span data-stu-id="df882-105">This topic shows how to include multiple tokens of the same type in a client message.</span></span>  
  
-   <span data-ttu-id="df882-106">Ein Dienst kann nicht auf diese Weise konfiguriert werden, da ein Dienst lediglich ein einzelnes unterstützendes Token enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="df882-106">Note that you cannot configure a service in this way: a service can contain only one supporting token.</span></span>  
  
### <a name="to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="df882-107">Gewusst wie: Verwenden mehrerer Sicherheitstokens desselben Typs</span><span class="sxs-lookup"><span data-stu-id="df882-107">To use multiple security tokens of the same type</span></span>  
  
1.  <span data-ttu-id="df882-108">Erstellen Sie eine leere auszufüllende Bindungselementauflistung.</span><span class="sxs-lookup"><span data-stu-id="df882-108">Create an empty binding element collection to be populated.</span></span>  
  
     [!code-csharp[C_CustomBinding#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#9)]  
  
2.  <span data-ttu-id="df882-109">Erstellen Sie <xref:System.ServiceModel.Channels.SecurityBindingElement> durch Aufrufen von <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="df882-109">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> by calling <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.</span></span>  
  
     [!code-csharp[C_CustomBinding#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#10)]  
  
3.  <span data-ttu-id="df882-110">Erstellen Sie eine <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters>-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="df882-110">Create a <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters> collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#11)]  
  
4.  <span data-ttu-id="df882-111">Fügen Sie der Auflistung SAML-Tokens hinzu.</span><span class="sxs-lookup"><span data-stu-id="df882-111">Add SAML tokens to the collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#12)]  
  
5.  <span data-ttu-id="df882-112">Fügen Sie die Auflistung <xref:System.ServiceModel.Channels.SecurityBindingElement> hinzu.</span><span class="sxs-lookup"><span data-stu-id="df882-112">Add the collection to the <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span></span>  
  
     [!code-csharp[C_CustomBinding#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#13)]  
  
6.  <span data-ttu-id="df882-113">Fügen Sie der Bindungselementauflistung Bindungselemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="df882-113">Add binding elements to the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#14)]  
  
7.  <span data-ttu-id="df882-114">Geben Sie aus der Bindungselementauflistung eine neue benutzerdefinierte Bindung zurück.</span><span class="sxs-lookup"><span data-stu-id="df882-114">Return a new custom binding created from the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#15)]  
  
## <a name="example"></a><span data-ttu-id="df882-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="df882-115">Example</span></span>  
 <span data-ttu-id="df882-116">Nachfolgend ist die gesamte Methode aufgeführt, die durch die vorherige Prozedur beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="df882-116">The following is the entire method described by the preceding procedure.</span></span>  
  
 [!code-csharp[C_CustomBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#7)]  
  
## <a name="see-also"></a><span data-ttu-id="df882-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df882-117">See Also</span></span>  
 [<span data-ttu-id="df882-118">Sicherheitsarchitektur</span><span class="sxs-lookup"><span data-stu-id="df882-118">Security Architecture</span></span>](https://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
