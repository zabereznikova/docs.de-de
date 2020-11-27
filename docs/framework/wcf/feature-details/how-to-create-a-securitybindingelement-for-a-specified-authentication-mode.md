---
title: 'Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
ms.openlocfilehash: 7b71224c74d7e9e766fb17101219dc5718d5d6a6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286434"
---
# <a name="how-to-create-a-securitybindingelement-for-a-specified-authentication-mode"></a><span data-ttu-id="155f1-102">Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus</span><span class="sxs-lookup"><span data-stu-id="155f1-102">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>

<span data-ttu-id="155f1-103">Windows Communication Foundation (WCF) bietet mehrere Modi, in denen sich Clients und Dienste untereinander authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="155f1-103">Windows Communication Foundation (WCF) provides several modes by which clients and services authenticate to one another.</span></span> <span data-ttu-id="155f1-104">Sie können Sicherheitsbindungselemente für diese Authentifizierungsmodi erstellen. Dazu verwenden Sie statische Methoden für die <xref:System.ServiceModel.Channels.SecurityBindingElement>-Klasse oder die Konfiguration, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="155f1-104">You can create security binding elements for these authentication modes by using static methods on the <xref:System.ServiceModel.Channels.SecurityBindingElement> class or through configuration, as shown in the following example.</span></span>  
  
 <span data-ttu-id="155f1-105">Weitere Informationen zu den 18 Authentifizierungs Modi finden Sie unter [SecurityBindingElement-Authentifizierungs Modi](securitybindingelement-authentication-modes.md).</span><span class="sxs-lookup"><span data-stu-id="155f1-105">For more information about the 18 authentication modes, see [SecurityBindingElement Authentication Modes](securitybindingelement-authentication-modes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="155f1-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="155f1-106">Example</span></span>  

 <span data-ttu-id="155f1-107">Im folgenden Codebeispiel werden Methoden zum Erstellen von Bindungen für die verschiedenen Authentifizierungsmodi veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="155f1-107">The following code example shows methods for creating bindings for the various authentication modes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="155f1-108">Nachdem eine Instanz des <xref:System.ServiceModel.Channels.SecurityBindingElement>-Objekts erstellt wurde, sind einige Eigenschaften unveränderlich, wie beispielsweise <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> und <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="155f1-108">Once an instance of the <xref:System.ServiceModel.Channels.SecurityBindingElement> object is created, a number of properties are immutable, such as <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> and <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.</span></span> <span data-ttu-id="155f1-109">`set` für diese Eigenschaften aufzurufen, hat keinen Effekt.</span><span class="sxs-lookup"><span data-stu-id="155f1-109">Calling `set` on such properties does not change them.</span></span>  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="155f1-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="155f1-110">See also</span></span>

- [<span data-ttu-id="155f1-111">SecurityBindingElement-Authentifizierungsmodi</span><span class="sxs-lookup"><span data-stu-id="155f1-111">SecurityBindingElement Authentication Modes</span></span>](securitybindingelement-authentication-modes.md)
- [<span data-ttu-id="155f1-112">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="155f1-112">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
