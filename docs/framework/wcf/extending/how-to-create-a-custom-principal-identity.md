---
title: "Vorgehensweise: Erstellen einer benutzerdefinierten Prinzipalidentität"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IPrincipal
- IAuthorizationPolicy
- PrincipalPermissionMode
- PrincipalPermissionAttribute
ms.assetid: c4845fca-0ed9-4adf-bbdc-10812be69b61
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 393bc7a33a522f483dc4daf1531c23afe421c261
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-custom-principal-identity"></a>Vorgehensweise: Erstellen einer benutzerdefinierten Prinzipalidentität
Das <xref:System.Security.Permissions.PrincipalPermissionAttribute> ist ein deklaratives Mittel für die Steuerung des Zugriffs auf Dienstmethoden. Wenn Sie dieses Attribut verwenden, gibt die <xref:System.ServiceModel.Description.PrincipalPermissionMode>-Enumeration den Modus für das Ausführen von Autorisierungsprüfungen an. Wenn dieser Modus auf <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> festgelegt ist, kann der Benutzer eine benutzerdefinierte <xref:System.Security.Principal.IPrincipal>-Klasse angeben, die von der <xref:System.Threading.Thread.CurrentPrincipal%2A>-Eigenschaft zurückgegeben wird. In diesem Thema wird das Szenario veranschaulicht, wenn <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> zusammen mit einer benutzerdefinierten Autorisierungsrichtlinie und einem benutzerdefinierten Prinzipal verwendet wird.  
  
 Weitere Informationen zum Verwenden der <xref:System.Security.Permissions.PrincipalPermissionAttribute>, finden Sie unter [Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[PrincipalPermissionMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/principalpermissionmode/cs/source.cs#8)]
 [!code-vb[PrincipalPermissionMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/principalpermissionmode/vb/source.vb#8)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Verweise auf die folgenden Namespaces sind zum Kompilieren des Codes erforderlich:  
  
-   <xref:System>  
  
-   <xref:System.Collections.Generic>  
  
-   <xref:System.Security.Permissions>  
  
-   <xref:System.Security.Principal>  
  
-   <xref:System.Threading>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.ServiceModel.Description>  
  
-   <xref:System.IdentityModel.Claims>  
  
-   <xref:System.IdentityModel.Policy>  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 [Vorgehensweise: Verwenden des ASP.NET-Rollenanbieters mit einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 [Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
