---
title: "Vorgehensweise: Annahme der Clientidentit&#228;t durch einen Dienst | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF, Identitätswechsel"
  - "Identitätswechsel"
  - "WCF, Sicherheit"
ms.assetid: 431db851-a75b-4009-9fe2-247243d810d3
caps.latest.revision: 33
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 33
---
# Vorgehensweise: Annahme der Clientidentit&#228;t durch einen Dienst
Nimmt ein [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Dienst die Identität eines Clients an, kann der Dienst Aktionen im Namen des Clients durchführen. Bei Aktionen, die einer ACL\-Überprüfung \(ACL \= Access Control List, Zugriffssteuerungsliste\) unterliegen, wie der Zugriff auf Verzeichnisse und Dateien auf einem Computer oder der Zugriff auf eine SQL&\#160;Server\-Datenbank, wird die ACL\-Überprüfung für das Clientbenutzerkonto durchgeführt. In diesem Thema werden die grundlegenden Schritte vorgestellt, die für die Aktivierung eines Clients in einer Windows\-Domäne erforderlich sind, damit eine Ebene für den Clientidentitätswechsel festgelegt werden kann. Ein funktionsfähiges Beispiel hierfür finden Sie unter [Durchführen eines Identitätswechsels für den Client](../../../docs/framework/wcf/samples/impersonating-the-client.md).[!INCLUDE[crabout](../../../includes/crabout-md.md)] zum Clientidentitätswechsel finden Sie unter [Delegierung und Identitätswechsel](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
> [!NOTE]
>  Wenn Client und Dienst auf demselben Computer ausgeführt werden und der Client unter einem Systemkonto \(das heißt unter `Local System` oder `Network Service`\) ausgeführt wird, kann kein Clientidentitätswechsel vorgenommen werden, wenn mit Token für den Sicherheitszustandskontext eine Sicherheitsverbindung hergestellt wird. Eine Windows&\#160;Forms\- oder Konsolenanwendung wird in der Regel unter dem derzeit angemeldeten Konto ausgeführt, sodass für dieses Konto standardmäßig ein Identitätswechsel durchgeführt werden kann. Wenn es sich bei dem Client jedoch um eine [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]\-Seite handelt, die auf [!INCLUDE[iis601](../../../includes/iis601-md.md)] oder IIS&\#160;7.0 gehostet wird, wird der Client standardmäßig unter dem `Network Service`\-Konto ausgeführt. Alle vom System bereitgestellten Bindungen, die Sicherheitssitzungen unterstützen, verwenden standardmäßig ein zustandsloses Token für den Sicherheitskontext. Wenn es sich bei dem Client jedoch um eine [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]\-Seite handelt und sichere Sitzungen mit Sicherheitskontexttoken verwendet werden, kann kein Clientidentitätswechsel durchgeführt werden.[!INCLUDE[crabout](../../../includes/crabout-md.md)] darüber, wie Sicherheitskontexttoken in einer sicheren Sitzung verwendet werden, finden Sie unter [Vorgehensweise: Erstellen eines Tokens für den Sicherheitskontext einer sicheren Sitzung](../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
### So aktivieren Sie die Annahme der Clientidentität durch einen Dienst über ein Windows\-Token im Cache\-Speicher  
  
1.  Erstellen Sie den Dienst. Ein Lernprogramm für diesen grundlegenden Vorgang finden Sie unter [Lernprogramm 'Erste Schritte'](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
2.  Verwenden Sie eine Bindung, die die Windows\-Authentifizierung verwendet und eine Sitzung erstellt, z.&\#160;B. <xref:System.ServiceModel.NetTcpBinding> oder <xref:System.ServiceModel.WSHttpBinding>.  
  
3.  Wenden Sie beim Erstellen der Implementierung der Dienstschnittstelle die <xref:System.ServiceModel.OperationBehaviorAttribute>\-Klasse auf die Methode an, für die ein Clientidentitätswechsel erforderlich ist. Legen Sie die <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A>\-Eigenschaft auf <xref:System.ServiceModel.ImpersonationOption> fest.  
  
     [!code-csharp[c_SimpleImpersonation#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#2)]
     [!code-vb[c_SimpleImpersonation#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#2)]  
  
### So legen Sie die zulässige Ebene des Identitätswechsels auf dem Client fest  
  
1.  Erstellen Sie Dienstclientcode mit dem [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).[!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Zugreifen auf Dienste mithilfe eines WCF\-Clients](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md).  
  
2.  Nachdem Sie den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Client erstellt haben, legen Sie für die <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A>\-Eigenschaft der <xref:System.ServiceModel.Security.WindowsClientCredential>\-Klasse einen der <xref:System.Security.Principal.TokenImpersonationLevel>\-Enumerationswerte fest.  
  
    > [!NOTE]
    >  Damit <xref:System.Security.Principal.TokenImpersonationLevel> verwendet werden kann, muss die ausgehandelte Kerberos\-Authentifizierung \(auch *bilateraler* oder *mehrstufiger* Kerberos\-Prozess genannt\) verwendet werden. Eine Beschreibung des Implementierungsvorgangs finden Sie unter [Best Practices für Sicherheit](../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).  
  
     [!code-csharp[c_SimpleImpersonation#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#1)]
     [!code-vb[c_SimpleImpersonation#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#1)]  
  
## Siehe auch  
 <xref:System.ServiceModel.OperationBehaviorAttribute>   
 <xref:System.Security.Principal.TokenImpersonationLevel>   
 [Durchführen eines Identitätswechsels für den Client](../../../docs/framework/wcf/samples/impersonating-the-client.md)   
 [Delegierung und Identitätswechsel](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)