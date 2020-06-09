---
title: 'Vorgehensweise: Zulassen von Metadatenanforderungen während der Autorisierung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- allowing metadata requests while authorizing [WCF]
ms.assetid: 90cec34f-b619-452b-a056-8b1c0de49d05
ms.openlocfilehash: 6d172f9b659804179d23fb382376f83f4898edc5
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601308"
---
# <a name="how-to-allow-metadata-requests-while-authorizing"></a><span data-ttu-id="8a476-102">Vorgehensweise: Zulassen von Metadatenanforderungen während der Autorisierung</span><span class="sxs-lookup"><span data-stu-id="8a476-102">How To: Allow Metadata Requests While Authorizing</span></span>
<span data-ttu-id="8a476-103">Während der benutzerdefinierten Autorisierung ist es möglicherweise notwendig, eine Anforderung für Metadaten zuzulassen, die verarbeitet werden sollten.</span><span class="sxs-lookup"><span data-stu-id="8a476-103">During custom authorization, it may be necessary to allow a request for metadata to be processed.</span></span> <span data-ttu-id="8a476-104">Das folgende Thema durchläuft die Schritte, um so eine Anforderung zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8a476-104">The following topic walks through the steps to validate such a request.</span></span>  
  
 <span data-ttu-id="8a476-105">Weitere Informationen zur Windows Communication Foundation (WCF)-Autorisierung finden Sie unter [Autorisierung](authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="8a476-105">For more information about Windows Communication Foundation (WCF) authorization, see [Authorization](authorization-in-wcf.md).</span></span>  
  
### <a name="to-allow-metadata-requests-during-authorization"></a><span data-ttu-id="8a476-106">So lassen Sie Metadatenanforderungen während der Autorisierung zu</span><span class="sxs-lookup"><span data-stu-id="8a476-106">To allow metadata requests during authorization</span></span>  
  
1. <span data-ttu-id="8a476-107">Erstellen Sie eine Erweiterung der <xref:System.ServiceModel.ServiceAuthorizationManager>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="8a476-107">Create an extension of the <xref:System.ServiceModel.ServiceAuthorizationManager> class.</span></span>  
  
2. <span data-ttu-id="8a476-108">Überschreiben Sie die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> -Methode.</span><span class="sxs-lookup"><span data-stu-id="8a476-108">Override the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="8a476-109">Die Methode gibt `true` oder `false` abhängig davon zurück, ob Autorisierung zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="8a476-109">The method returns `true` or `false` depending on whether authorization is allowed.</span></span> <span data-ttu-id="8a476-110">Informationen zur aktuellen Prozedur finden Sie im <xref:System.ServiceModel.OperationContext>, der zur Methode als Parameter übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="8a476-110">Information about the current procedure is found in the <xref:System.ServiceModel.OperationContext> passed as a parameter to the method.</span></span>  
  
3. <span data-ttu-id="8a476-111">Überprüfen Sie in der Außerkraftsetzung den Vertragsnamen, Namespace und die Aktion, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8a476-111">In the override, check the contract name, namespace, and the action as shown in the following example.</span></span> <span data-ttu-id="8a476-112">Wenn die Bedingungen gültig sind, geben Sie `true.` zurück</span><span class="sxs-lookup"><span data-stu-id="8a476-112">If the conditions are valid, then return `true.`</span></span>  
  
4. <span data-ttu-id="8a476-113">Verwenden Sie den Erweiterbarkeitspunkt, um die Klasse bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8a476-113">Use the extensibility point to employ the class.</span></span> <span data-ttu-id="8a476-114">Weitere Informationen finden Sie unter Gewusst [wie: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst](../extending/how-to-create-a-custom-authorization-manager-for-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="8a476-114">For more information, see [How to: Create a Custom Authorization Manager for a Service](../extending/how-to-create-a-custom-authorization-manager-for-a-service.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a476-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8a476-115">Example</span></span>  
 <span data-ttu-id="8a476-116">Das folgende Beispiel zeigt das Außerkraftsetzen der <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="8a476-116">The following example shows an override of the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span>  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8a476-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a476-117">See also</span></span>

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [<span data-ttu-id="8a476-118">Autorisierung</span><span class="sxs-lookup"><span data-stu-id="8a476-118">Authorization</span></span>](authorization-in-wcf.md)
- [<span data-ttu-id="8a476-119">Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell</span><span class="sxs-lookup"><span data-stu-id="8a476-119">Managing Claims and Authorization with the Identity Model</span></span>](managing-claims-and-authorization-with-the-identity-model.md)
