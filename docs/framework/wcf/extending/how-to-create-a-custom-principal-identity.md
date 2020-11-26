---
title: 'Vorgehensweise: Erstellen einer benutzerdefinierten Prinzipalidentität'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IPrincipal
- IAuthorizationPolicy
- PrincipalPermissionMode
- PrincipalPermissionAttribute
ms.assetid: c4845fca-0ed9-4adf-bbdc-10812be69b61
ms.openlocfilehash: 6c50d6b0ac2baa2dc61431af4afb8dca3860456a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249305"
---
# <a name="how-to-create-a-custom-principal-identity"></a><span data-ttu-id="a26d4-102">Vorgehensweise: Erstellen einer benutzerdefinierten Prinzipalidentität</span><span class="sxs-lookup"><span data-stu-id="a26d4-102">How to: Create a Custom Principal Identity</span></span>

<span data-ttu-id="a26d4-103">Das <xref:System.Security.Permissions.PrincipalPermissionAttribute> ist ein deklaratives Mittel für die Steuerung des Zugriffs auf Dienstmethoden.</span><span class="sxs-lookup"><span data-stu-id="a26d4-103">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is a declarative means of controlling access to service methods.</span></span> <span data-ttu-id="a26d4-104">Wenn Sie dieses Attribut verwenden, gibt die <xref:System.ServiceModel.Description.PrincipalPermissionMode>-Enumeration den Modus für das Ausführen von Autorisierungsprüfungen an.</span><span class="sxs-lookup"><span data-stu-id="a26d4-104">When using this attribute, the <xref:System.ServiceModel.Description.PrincipalPermissionMode> enumeration specifies the mode for performing authorization checks.</span></span> <span data-ttu-id="a26d4-105">Wenn dieser Modus auf <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> festgelegt ist, kann der Benutzer eine benutzerdefinierte <xref:System.Security.Principal.IPrincipal>-Klasse angeben, die von der <xref:System.Threading.Thread.CurrentPrincipal%2A>-Eigenschaft zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a26d4-105">When this mode is set to <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom>, it enables the user to specify a custom <xref:System.Security.Principal.IPrincipal> class returned by the <xref:System.Threading.Thread.CurrentPrincipal%2A> property.</span></span> <span data-ttu-id="a26d4-106">In diesem Thema wird das Szenario veranschaulicht, wenn <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> zusammen mit einer benutzerdefinierten Autorisierungsrichtlinie und einem benutzerdefinierten Prinzipal verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a26d4-106">This topic illustrates the scenario when <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> is used in combination with a custom authorization policy and a custom principal.</span></span>  
  
 <span data-ttu-id="a26d4-107">Weitere Informationen zum Verwenden von finden Sie unter Gewusst <xref:System.Security.Permissions.PrincipalPermissionAttribute> [wie: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse](../how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span><span class="sxs-lookup"><span data-stu-id="a26d4-107">For more information about using the <xref:System.Security.Permissions.PrincipalPermissionAttribute>, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a26d4-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a26d4-108">Example</span></span>  

 [!code-csharp[PrincipalPermissionMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/principalpermissionmode/cs/source.cs#8)]
 [!code-vb[PrincipalPermissionMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/principalpermissionmode/vb/source.vb#8)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a26d4-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="a26d4-109">Compiling the Code</span></span>  

 <span data-ttu-id="a26d4-110">Verweise auf die folgenden Namespaces sind zum Kompilieren des Codes erforderlich:</span><span class="sxs-lookup"><span data-stu-id="a26d4-110">References to the following namespaces are needed to compile the code:</span></span>  
  
- <xref:System>  
  
- <xref:System.Collections.Generic>  
  
- <xref:System.Security.Permissions>  
  
- <xref:System.Security.Principal>  
  
- <xref:System.Threading>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.ServiceModel.Description>  
  
- <xref:System.IdentityModel.Claims>  
  
- <xref:System.IdentityModel.Policy>  
  
## <a name="see-also"></a><span data-ttu-id="a26d4-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a26d4-111">See also</span></span>

- <xref:System.ServiceModel.Description.PrincipalPermissionMode>
- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- [<span data-ttu-id="a26d4-112">Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst</span><span class="sxs-lookup"><span data-stu-id="a26d4-112">How to: Use the ASP.NET Role Provider with a Service</span></span>](../feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [<span data-ttu-id="a26d4-113">Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse</span><span class="sxs-lookup"><span data-stu-id="a26d4-113">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../how-to-restrict-access-with-the-principalpermissionattribute-class.md)
