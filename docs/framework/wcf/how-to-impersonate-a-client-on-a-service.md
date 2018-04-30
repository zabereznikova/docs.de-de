---
title: 'Vorgehensweise: Annahme der Clientidentität durch einen Dienst'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, impersonation
- impersonation
- WCF, security
ms.assetid: 431db851-a75b-4009-9fe2-247243d810d3
caps.latest.revision: 33
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 096a3dd1ae5035f6b015ec88ccd8f1ada1dc55ea
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-impersonate-a-client-on-a-service"></a>Vorgehensweise: Annahme der Clientidentität durch einen Dienst
Nimmt ein [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] -Dienst die Identität eines Clients an, kann der Dienst Aktionen im Namen des Clients durchführen. Bei Aktionen, die einer ACL-Überprüfung (ACL = Access Control List, Zugriffssteuerungsliste) unterliegen, wie der Zugriff auf Verzeichnisse und Dateien auf einem Computer oder der Zugriff auf eine SQL&#160;Server-Datenbank, wird die ACL-Überprüfung für das Clientbenutzerkonto durchgeführt. In diesem Thema werden die grundlegenden Schritte vorgestellt, die für die Aktivierung eines Clients in einer Windows-Domäne erforderlich sind, damit eine Ebene für den Clientidentitätswechsel festgelegt werden kann. Ein funktionsfähiges Beispiel hierfür finden Sie unter [Impersonating the Client](../../../docs/framework/wcf/samples/impersonating-the-client.md). Weitere Informationen zum Clientidentitätswechsel finden Sie unter [Delegierung und Identitätswechsel](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
> [!NOTE]
>  Wenn Client und Dienst auf demselben Computer ausgeführt werden und der Client unter einem Systemkonto (das heißt unter `Local System` oder `Network Service`) ausgeführt wird, kann kein Clientidentitätswechsel vorgenommen werden, wenn mit Token für den Sicherheitszustandskontext eine Sicherheitsverbindung hergestellt wird. Eine Windows&#160;Forms- oder Konsolenanwendung wird in der Regel unter dem derzeit angemeldeten Konto ausgeführt, sodass für dieses Konto standardmäßig ein Identitätswechsel durchgeführt werden kann. Wenn es sich bei dem Client jedoch um eine [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] -Seite handelt, die auf [!INCLUDE[iis601](../../../includes/iis601-md.md)] oder IIS&amp;#160;7.0 gehostet wird, wird der Client standardmäßig unter dem `Network Service` -Konto ausgeführt. Alle vom System bereitgestellten Bindungen, die Sicherheitssitzungen unterstützen, verwenden standardmäßig ein zustandsloses Token für den Sicherheitskontext. Wenn es sich bei dem Client jedoch um eine [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] -Seite handelt und sichere Sitzungen mit Sicherheitskontexttoken verwendet werden, kann kein Clientidentitätswechsel durchgeführt werden. Weitere Informationen zur Verwendung von zustandsbehafteten Sicherheitskontexttoken in einer sicheren Sitzung finden Sie unter [Vorgehensweise: Erstellen Sie ein Sicherheitskontexttoken für eine Sicherheitssitzung](../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
### <a name="to-enable-impersonation-of-a-client-from-a-cached-windows-token-on-a-service"></a>So aktivieren Sie die Annahme der Clientidentität durch einen Dienst über ein Windows-Token im Cache-Speicher  
  
1.  Erstellen Sie den Dienst. Ein Lernprogramm für diesen grundlegenden Vorgang finden Sie unter [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
2.  Verwenden Sie eine Bindung, die die Windows-Authentifizierung verwendet und eine Sitzung erstellt, z.&amp;#160;B. <xref:System.ServiceModel.NetTcpBinding> oder <xref:System.ServiceModel.WSHttpBinding>.  
  
3.  Wenden Sie beim Erstellen der Implementierung der Dienstschnittstelle die <xref:System.ServiceModel.OperationBehaviorAttribute> -Klasse auf die Methode an, für die ein Clientidentitätswechsel erforderlich ist. Legen Sie die <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> -Eigenschaft auf <xref:System.ServiceModel.ImpersonationOption.Required>fest.  
  
     [!code-csharp[c_SimpleImpersonation#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#2)]
     [!code-vb[c_SimpleImpersonation#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#2)]  
  
### <a name="to-set-the-allowed-impersonation-level-on-the-client"></a>So legen Sie die zulässige Ebene des Identitätswechsels auf dem Client fest  
  
1.  Erstellen Sie Dienstclientcode mit dem [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Weitere Informationen finden Sie unter [beim Zugriff auf Dienste, die mithilfe eines WCF-Clients](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md).  
  
2.  Nachdem Sie den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Client erstellt haben, legen Sie für die <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> -Eigenschaft der <xref:System.ServiceModel.Security.WindowsClientCredential> -Klasse einen der <xref:System.Security.Principal.TokenImpersonationLevel> -Enumerationswerte fest.  
  
    > [!NOTE]
    >  Damit <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>verwendet werden kann, muss die ausgehandelte Kerberos-Authentifizierung (auch *bilateraler* oder *mehrstufiger* Kerberos-Prozess genannt) verwendet werden. Eine Beschreibung des Implementierungsvorgangs finden Sie in [Best Practices für Sicherheit](../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).  
  
     [!code-csharp[c_SimpleImpersonation#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#1)]
     [!code-vb[c_SimpleImpersonation#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.OperationBehaviorAttribute>  
 <xref:System.Security.Principal.TokenImpersonationLevel>  
 [Durchführen eines Identitätswechsels für den Client](../../../docs/framework/wcf/samples/impersonating-the-client.md)  
 [Delegierung und Identitätswechsel](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)
