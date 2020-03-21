---
title: Zugriffssteuerungsmechanismen
ms.date: 03/30/2017
helpviewer_keywords:
- WCF security
- access control [WCF]
ms.assetid: 9d576122-3f55-4425-9acf-b23d0781e966
ms.openlocfilehash: b423dac4d8324069eb1825666419b23b5afdca63
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185491"
---
# <a name="access-control-mechanisms"></a>Zugriffssteuerungsmechanismen
Mit Windows Communication Foundation (WCF) können Sie den Zugriff auf verschiedene Weise steuern. In diesem Thema werden kurz die verschiedenen Mechanismen besprochen und Vorschläge dazu unterbreitet, wann die einzelnen Mechanismen eingesetzt werden sollten. Dies soll Ihnen die Wahl des richtigen Mechanismus erleichtern. Die Zugriffstechnologien sind in der Reihenfolge der Komplexität aufgelistet. Die einfachste Technologie ist das <xref:System.Security.Permissions.PrincipalPermissionAttribute>; die komplexeste ist das Identitätsmodell.  
  
 Zusätzlich zu diesen Mechanismen werden Identitätswechsel und Delegierung mit WCF in [Delegation und Identitätswechsel](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)erläutert.  
  
## <a name="principalpermissionattribute"></a>PrincipalPermissionAttribute  
 Das <xref:System.Security.Permissions.PrincipalPermissionAttribute> wird verwendet, um den Zugriff auf eine Dienstmethode einzuschränken. Wenn das Attribut auf eine Methode angewendet wird, kann es verwendet werden, um die Identität oder Mitgliedschaft eines bestimmten Aufrufers in einer Windows-Gruppe oder ASP.NET Rolle anzufordern. Wenn der Client mit einem X.509-Zertifikat authentifiziert ist, erhält er eine primäre Identität, die aus dem Betreffnamen und dem Fingerabdruck des Zertifikats besteht.  
  
 Verwenden Sie das <xref:System.Security.Permissions.PrincipalPermissionAttribute>, um den Zugriff auf Ressourcen auf dem Computer zu kontrollieren, auf dem der Dienst ausgeführt wird, sofern der Benutzer des Diensts immer zur selben Windows-Domäne gehört, auf der der Dienst ausgeführt wird. Sie können ganz einfach Windows-Gruppen erstellen, die über festgelegte Zugriffsebenen verfügen (z. B. kein Zugriff, schreibgeschützter Zugriff oder Schreibzugriff).  
  
 Weitere Informationen zur Verwendung des Attributs finden Sie unter [Gewusst wie: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md). Weitere Informationen zur Identität finden Sie unter [Dienstidentität und Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## <a name="aspnet-membership-provider"></a>ASP.NET-Mitgliedschaftsanbieter  
 Ein Merkmal von ASP.NET ist der Mitgliedschaftsanbieter. Obwohl der Mitgliedschaftsanbieter technisch gesehen kein Mechanismus zur Zugriffskontrolle ist, ermöglicht er eine Kontrolle des Zugriffs auf den Dienst, indem er die Anzahl der möglichen Identitäten begrenzt, die auf die Endpunkte des Diensts zugreifen können. Die Mitgliedschaftsfunktion umfasst eine Datenbank, in die der Benutzername und das Kennwort eingegeben werden können, mit denen Benutzer einer Website Konten auf der Site einrichten können. Um auf einen Dienst zuzugreifen, der den Mitgliedschaftsanbieter verwendet, muss sich ein Benutzer mit seinem Benutzernamen und Kennwort anmelden.  
  
> [!NOTE]
> Sie müssen die Datenbank zunächst mit der ASP.NET-Funktion auffüllen, bevor ein WCF-Dienst sie für Autorisierungszwecke verwenden kann.  
  
 Sie können die Mitgliedschaftsfunktion auch verwenden, wenn Sie bereits über eine Mitgliedschaftsdatenbank von einer vorhandenen ASP.NET-Website verfügen und dieselben Benutzer die Nutzung Ihres Dienstes ermöglichen möchten, der mit denselben Benutzernamen und Kennwörtern autorisiert ist.  
  
 Weitere Informationen zur Verwendung der Mitgliedschaftsfunktion in einem WCF-Dienst finden Sie unter [Gewusst wie: Verwenden des ASP.NET Mitgliedschaftsanbieters](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).  
  
## <a name="aspnet-role-provider"></a>ASP.NET-Rollenanbieter  
 Ein weiteres Merkmal von ASP.NET ist die Möglichkeit, die Autorisierung mithilfe von Rollen zu verwalten. Der ASP.NET Rollenanbieter ermöglicht es einem Entwickler, Rollen für Benutzer zu erstellen und jeden Benutzer einer Rolle oder Rollen zuzuweisen. Wie beim Mitgliedschaftsanbieter werden die Rollen und Zuweisungen in einer Datenbank gespeichert und können mithilfe von Tools aufgefüllt werden, die von einer bestimmten Implementierung des ASP.NET Rollenanbieterbereitgestellter bereitgestellt werden. Wie bei der Mitgliedschaftsfunktion können WCF-Entwickler die Informationen in der Datenbank verwenden, um Dienstbenutzer nach Rollen zu autorisieren. Beispielsweise können Sie den Rollenanbieter gemeinsam mit dem oben beschriebenen `PrincipalPermissionAttribute`-Mechanismus zur Zugriffskontrolle verwenden.  
  
 Sie können auch den ASP.NET Rollenanbieter verwenden, wenn Sie über eine vorhandene ASP.NET Rollenanbieterdatenbank verfügen und denselben Satz von Regeln und Benutzerzuweisungen in Ihrem WCF-Dienst verwenden möchten.  
  
 Weitere Informationen zur Verwendung der Rollenanbieterfunktion finden Sie unter [Gewusst wie: Verwenden des ASP.NET Rollenanbieters mit einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).  
  
## <a name="authorization-manager"></a>Autorisierungs-Manager  
 Ein weiteres Feature kombiniert den Autorisierungs-Manager (AzMan) mit dem ASP.NET Rollenanbieter, um Clients zu autorisieren. Wenn ASP.NET einen Webdienst hostet, kann AzMan in die Anwendung integriert werden, sodass die Autorisierung für den Dienst über AzMan erfolgt. ASP.NET Rollen-Manager stellt eine API bereit, mit der Sie Anwendungsrollen verwalten, Benutzer zu Rollen hinzufügen und aus ihnen entfernen und die Rollenmitgliedschaft überprüfen können. AzMan ermöglicht es Ihnen, einzelne Vorgänge zu definieren und sie in Aufgaben zu kombinieren. Mit AZMan können Sie neben Rollenüberprüfungen auch feststellen, ob ein Benutzer eine Aufgabe ausführen kann. Rollenzuweisungen und Aufgabenautorisierungen können außerhalb der Anwendung konfiguriert oder programmgesteuert innerhalb der Anwendung ausgeführt werden. Das Snap-In der Microsoft Management Console (MMC) für die AzMan-Verwaltung ermöglicht Administratoren, die Aufgaben zu ändern, die eine Rolle während der Laufzeit ausführen kann, und die Rollenmitgliedschaft jedes Benutzers zu verwalten.  
  
 Sie können AzMan und den ASP.NET Rollenanbieter auch verwenden, wenn Sie bereits Zugriff auf eine vorhandene AzMan-Installation haben und Ihre Dienstbenutzer mithilfe der Funktionen der AzMan/Role-Anbieter-Kombination autorisieren möchten.  
  
 Weitere Informationen zu AzMan und dem ASP.NET Rollenanbieter finden Sie unter [How To: Use Authorization Manager (AzMan) with ASP.NET 2.0](https://docs.microsoft.com/previous-versions/msp-n-p/ff649313(v=pandp.10)). Weitere Informationen zur Verwendung von AzMan und dem Rollenanbieter für WCF-Dienste finden Sie unter [Gewusst wie: Verwenden des ASP.NET Autorisierungs-Manager-Rollenanbieters mit einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md).  
  
## <a name="identity-model"></a>Identitätsmodell  
 Das Identitätsmodell besteht aus einem Satz APIs, die Ihnen ermöglichen, Ansprüche und Richtlinien zu verwalten, um Clients zu autorisieren. Mit dem Identitätsmodell können Sie jeden Anspruch prüfen, der in den vom Benutzer zur Authentifizierung beim Dienst verwendeten Anmeldeinformationen enthalten ist. Anschließend können Sie die Ansprüche mit den Richtlinien für diesen Dienst vergleichen und den Zugriff entsprechend gewähren oder verweigern.  
  
 Verwenden Sie das Identitätsmodell, wenn Sie eine präzise Steuerung wünschen und bestimmte Kriterien festlegen möchten, bevor Sie den Zugriff gewähren. Wenn Sie z. B. das <xref:System.Security.Permissions.PrincipalPermissionAttribute> verwenden, besteht das Kriterium ganz einfach darin, dass der Benutzer authentifiziert sein und zu einer bestimmten Rolle gehören muss. Dagegen können Sie mit dem Identitätsmodell eine Richtlinie erstellen, die besagt, dass der Benutzer über 18 Jahre alt sein und einen gültigen Führerschein besitzen muss, bevor er ein Dokument anzeigen darf.  
  
 Ein Beispiel für den Nutzen, den Ihnen die anspruchsbasierte Zugriffssteuerung des Identitätsmodells bieten kann, ist die Verwendung von Verbundanmeldeinformationen im Szenario für ausgestellte Token. Weitere Informationen zu Verbund- und ausgestellten Token finden Sie unter [Föderation und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
 Weitere Informationen zum Identitätsmodell finden Sie unter [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- [Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [Vorgehensweise: Verwenden des ASP.NET-Autorisierungs-Manager-Rollenanbieters mit einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)
- [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
- [Delegierung und Identitätswechsel](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)
