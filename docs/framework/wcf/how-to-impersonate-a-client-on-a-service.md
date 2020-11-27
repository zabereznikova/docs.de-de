---
title: 'Vorgehensweise: Annahme der Clientidentität durch einen Dienst'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, impersonation
- impersonation
- WCF, security
ms.assetid: 431db851-a75b-4009-9fe2-247243d810d3
ms.openlocfilehash: 24a06df5b6fbb908aff3ef1b2166fd5162549ba2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290113"
---
# <a name="how-to-impersonate-a-client-on-a-service"></a>Vorgehensweise: Annahme der Clientidentität durch einen Dienst

Durch das Annehmen der Identität eines Clients auf einem Windows Communication Foundation (WCF)-Dienst kann der Dienst Aktionen im Namen des Clients durchführen. Bei Aktionen, die einer ACL-Überprüfung (ACL = Access Control List, Zugriffssteuerungsliste) unterliegen, wie der Zugriff auf Verzeichnisse und Dateien auf einem Computer oder der Zugriff auf eine SQL&#160;Server-Datenbank, wird die ACL-Überprüfung für das Clientbenutzerkonto durchgeführt. In diesem Thema werden die grundlegenden Schritte vorgestellt, die für die Aktivierung eines Clients in einer Windows-Domäne erforderlich sind, damit eine Ebene für den Clientidentitätswechsel festgelegt werden kann. Ein funktionsfähiges Beispiel hierfür finden Sie unter [Impersonating the Client](./samples/impersonating-the-client.md). Weitere Informationen zum Client Identitätswechsel finden Sie unter [Delegierung und](./feature-details/delegation-and-impersonation-with-wcf.md)Identitätswechsel.  
  
> [!NOTE]
> Wenn Client und Dienst auf demselben Computer ausgeführt werden und der Client unter einem Systemkonto (das heißt unter `Local System` oder `Network Service`) ausgeführt wird, kann kein Clientidentitätswechsel vorgenommen werden, wenn mit Token für den Sicherheitszustandskontext eine Sicherheitsverbindung hergestellt wird. Eine Windows&#160;Forms- oder Konsolenanwendung wird in der Regel unter dem derzeit angemeldeten Konto ausgeführt, sodass für dieses Konto standardmäßig ein Identitätswechsel durchgeführt werden kann. Wenn es sich bei dem Client jedoch um eine ASP.NET-Seite handelt und diese Seite in IIS 6,0 oder IIS 7,0 gehostet wird, wird der Client `Network Service` standardmäßig unter dem Konto ausgeführt. Alle vom System bereitgestellten Bindungen, die Sicherheitssitzungen unterstützen, verwenden standardmäßig ein zustandsloses Token für den Sicherheitskontext. Wenn es sich bei dem Client jedoch um eine ASP.NET-Seite handelt und sichere Sitzungen mit Zustands behafteten Sicherheitskontext Token verwendet werden, kann kein Client Identitätswechsel durchgeführt werden. Weitere Informationen zur Verwendung von Token für den Sicherheitszustands Kontext in einer sicheren Sitzung finden Sie unter Gewusst [wie: Erstellen eines Sicherheitskontext Tokens für eine sichere Sitzung](./feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
### <a name="to-enable-impersonation-of-a-client-from-a-cached-windows-token-on-a-service"></a>So aktivieren Sie die Annahme der Clientidentität durch einen Dienst über ein Windows-Token im Cache-Speicher  
  
1. Erstellen Sie den Dienst. Ein Lernprogramm für diesen grundlegenden Vorgang finden Sie unter [Getting Started Tutorial](getting-started-tutorial.md).  
  
2. Verwenden Sie eine Bindung, die die Windows-Authentifizierung verwendet und eine Sitzung erstellt, z.&#160;B. <xref:System.ServiceModel.NetTcpBinding> oder <xref:System.ServiceModel.WSHttpBinding>.  
  
3. Wenden Sie beim Erstellen der Implementierung der Dienstschnittstelle die <xref:System.ServiceModel.OperationBehaviorAttribute> -Klasse auf die Methode an, für die ein Clientidentitätswechsel erforderlich ist. Legen Sie die <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> -Eigenschaft auf <xref:System.ServiceModel.ImpersonationOption.Required>fest.  
  
     [!code-csharp[c_SimpleImpersonation#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#2)]
     [!code-vb[c_SimpleImpersonation#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#2)]  
  
### <a name="to-set-the-allowed-impersonation-level-on-the-client"></a>So legen Sie die zulässige Ebene des Identitätswechsels auf dem Client fest  
  
1. Erstellen Sie Dienstclientcode mit dem [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md). Weitere Informationen finden Sie unter [zugreifen auf Dienste mithilfe eines WCF-Clients](accessing-services-using-a-wcf-client.md).  
  
2. Nachdem Sie den WCF-Client erstellt haben, legen Sie die- <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> Eigenschaft der- <xref:System.ServiceModel.Security.WindowsClientCredential> Klasse auf einen der- <xref:System.Security.Principal.TokenImpersonationLevel> Enumerationswerte fest.  
  
    > [!NOTE]
    > Damit <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>verwendet werden kann, muss die ausgehandelte Kerberos-Authentifizierung (auch *bilateraler* oder *mehrstufiger* Kerberos-Prozess genannt) verwendet werden. Eine Beschreibung der Implementierung dieser Vorgehensweise finden Sie unter [bewährte Methoden für die Sicherheit](./feature-details/best-practices-for-security-in-wcf.md).  
  
     [!code-csharp[c_SimpleImpersonation#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#1)]
     [!code-vb[c_SimpleImpersonation#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.OperationBehaviorAttribute>
- <xref:System.Security.Principal.TokenImpersonationLevel>
- [Durchführen eines Identitätswechsels für den Client](./samples/impersonating-the-client.md)
- [Delegierung und Identitätswechsel](./feature-details/delegation-and-impersonation-with-wcf.md)
