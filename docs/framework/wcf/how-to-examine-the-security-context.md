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
ms.openlocfilehash: 40950614892ddfd4eb24194f0389e057a5a13378
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272943"
---
# <a name="how-to-examine-the-security-context"></a>Vorgehensweise: Prüfen des Sicherheitskontexts

Wenn Sie Windows Communication Foundation (WCF)-Dienste programmieren, können Sie mithilfe des Dienst Sicherheits Kontexts Details über die Client Anmelde Informationen und die Ansprüche ermitteln, die für die Authentifizierung mit dem Dienst verwendet werden. Dies geschieht anhand der Eigenschaften der <xref:System.ServiceModel.ServiceSecurityContext>-Klasse.  
  
 So können Sie z.&#160;B. die Identität des aktuellen Clients mit der <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A>-Eigenschaft oder der <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>-Eigenschaft abrufen. Mit der <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A>-Eigenschaft können Sie ermitteln, ob der Client anonym ist.  
  
 Sie können auch bestimmen, welche Ansprüche im Namen des Clients gestellt werden, indem Sie die Auflistung der Ansprüche der <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A>-Eigenschaft durchlaufen.  
  
### <a name="to-get-the-current-security-context"></a>So rufen Sie den aktuellen Sicherheitskontext ab  
  
- Greifen Sie auf die statische <xref:System.ServiceModel.ServiceSecurityContext.Current%2A>- Eigenschaft zu, um den aktuellen Sicherheitskontext abzurufen. Überprüfen Sie eine beliebige der Eigenschaften des aktuellen Kontexts für den Verweis.  
  
### <a name="to-determine-the-identity-of-the-caller"></a>So ermitteln Sie die Identität des Aufrufers  
  
1. Drucken Sie den Wert der <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A>-Eigenschaft und der <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>-Eigenschaft.  
  
### <a name="to-parse-the-claims-of-a-caller"></a>So analysieren Sie die Ansprüche eines Aufrufers  
  
1. Geben Sie die aktuelle <xref:System.IdentityModel.Policy.AuthorizationContext>-Klasse zurück. Verwenden Sie die <xref:System.ServiceModel.ServiceSecurityContext.Current%2A>-Eigenschaft, um den aktuellen Dienstsicherheitskontext zurückzugeben, geben Sie dann den `AuthorizationContext` mit der <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A>-Eigenschaft zurück.  
  
2. Analysieren Sie die Auflistung der <xref:System.IdentityModel.Claims.ClaimSet>-Objekte, die von der <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A>-Eigenschaft der <xref:System.IdentityModel.Policy.AuthorizationContext>-Klasse zurückgegeben werden.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel werden die Werte der <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>-Eigenschaft und der <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A>-Eigenschaft des aktuellen Sicherheitskontexts und der <xref:System.IdentityModel.Claims.Claim.ClaimType%2A>-Eigenschaft gedruckt sowie der Ressourcenwert des Anspruchs und die <xref:System.IdentityModel.Claims.Claim.Right%2A>-Eigenschaft jedes Anspruchs im aktuellen Sicherheitskontext.  
  
 [!code-csharp[c_PrincipalPermissionAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#4)]
 [!code-vb[c_PrincipalPermissionAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#4)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  

 Der Code verwendet die folgenden Namespaces:  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.IdentityModel.Policy>  
  
- <xref:System.IdentityModel.Claims>  
  
## <a name="see-also"></a>Weitere Informationen

- [Sichern von Diensten](securing-services.md)
- [Dienstidentität und Authentifizierung](./feature-details/service-identity-and-authentication.md)
