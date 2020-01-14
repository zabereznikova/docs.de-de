---
title: Zugriffssteuerungsmechanismen
ms.date: 03/30/2017
helpviewer_keywords:
- WCF security
- access control [WCF]
ms.assetid: 9d576122-3f55-4425-9acf-b23d0781e966
ms.openlocfilehash: 7dcdcff9470a7c2777f856e8c1c2143a3a92b73b
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75938186"
---
# <a name="access-control-mechanisms"></a>Zugriffssteuerungsmechanismen
Sie können den Zugriff auf verschiedene Weise mit Windows Communication Foundation (WCF) steuern. In diesem Thema werden kurz die verschiedenen Mechanismen besprochen und Vorschläge dazu unterbreitet, wann die einzelnen Mechanismen eingesetzt werden sollten. Dies soll Ihnen die Wahl des richtigen Mechanismus erleichtern. Die Zugriffstechnologien sind in der Reihenfolge der Komplexität aufgelistet. Die einfachste Technologie ist das <xref:System.Security.Permissions.PrincipalPermissionAttribute>; die komplexeste ist das Identitätsmodell.  
  
 Zusätzlich zu diesen Mechanismen wird der Identitätswechsel und die Delegierung mit WCF in [Delegierung und](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)Identitätswechsel erläutert.  
  
## <a name="principalpermissionattribute"></a>PrincipalPermissionAttribute  
 Das <xref:System.Security.Permissions.PrincipalPermissionAttribute> wird verwendet, um den Zugriff auf eine Dienstmethode einzuschränken. Wenn das-Attribut auf eine Methode angewendet wird, kann es verwendet werden, um die Identität eines bestimmten Aufrufers oder die Mitgliedschaft in einer Windows-Gruppe oder ASP.NET-Rolle zu fordern. Wenn der Client mit einem X.509-Zertifikat authentifiziert ist, erhält er eine primäre Identität, die aus dem Betreffnamen und dem Fingerabdruck des Zertifikats besteht.  
  
 Verwenden Sie das <xref:System.Security.Permissions.PrincipalPermissionAttribute>, um den Zugriff auf Ressourcen auf dem Computer zu kontrollieren, auf dem der Dienst ausgeführt wird, sofern der Benutzer des Diensts immer zur selben Windows-Domäne gehört, auf der der Dienst ausgeführt wird. Sie können ganz einfach Windows-Gruppen erstellen, die über festgelegte Zugriffsebenen verfügen (z. B. kein Zugriff, schreibgeschützter Zugriff oder Schreibzugriff).  
  
 Weitere Informationen zur Verwendung des-Attributs finden Sie unter Gewusst [wie: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md). Weitere Informationen zur Identität finden Sie unter [Dienst Identität und-Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## <a name="aspnet-membership-provider"></a>ASP.NET-Mitgliedschaftsanbieter  
 Eine Funktion von ASP.net ist der Mitgliedschafts Anbieter. Obwohl der Mitgliedschaftsanbieter technisch gesehen kein Mechanismus zur Zugriffskontrolle ist, ermöglicht er eine Kontrolle des Zugriffs auf den Dienst, indem er die Anzahl der möglichen Identitäten begrenzt, die auf die Endpunkte des Diensts zugreifen können. Die Mitgliedschaftsfunktion umfasst eine Datenbank, in die der Benutzername und das Kennwort eingegeben werden können, mit denen Benutzer einer Website Konten auf der Site einrichten können. Um auf einen Dienst zuzugreifen, der den Mitgliedschaftsanbieter verwendet, muss sich der Benutzer mit seinem Benutzernamen und Kennwort anmelden.  
  
> [!NOTE]
> Sie müssen die Datenbank zuerst mithilfe der ASP.net-Funktion auffüllen, bevor Sie von einem WCF-Dienst zu Autorisierungs Zwecken verwendet werden kann.  
  
 Sie können auch die Mitgliedschafts Funktion verwenden, wenn Sie bereits über eine Mitgliedschafts Datenbank von einer vorhandenen ASP.NET-Website verfügen, und Sie möchten, dass die gleichen Benutzer den Dienst verwenden können, der mit denselben Benutzernamen und Kenn Wörtern autorisiert ist.  
  
 Weitere Informationen zum Verwenden der Mitgliedschafts Funktion in einem WCF-Dienst finden Sie unter Gewusst [wie: Verwenden des ASP.net-Mitgliedschafts Anbieters](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).  
  
## <a name="aspnet-role-provider"></a>ASP.NET-Rollenanbieter  
 Eine weitere Funktion von ASP.net ist die Fähigkeit zum Verwalten der Autorisierung mithilfe von Rollen. Der ASP.NET-Rollen Anbieter ermöglicht Entwicklern das Erstellen von Rollen für Benutzer und das Zuweisen der einzelnen Benutzer zu Rollen oder Rollen. Ebenso wie der Mitgliedschafts Anbieter werden die Rollen und Zuweisungen in einer-Datenbank gespeichert und können mit Tools aufgefüllt werden, die von einer bestimmten Implementierung des ASP.NET-Rollen Anbieters bereitgestellt werden. Wie bei der Mitgliedschafts Funktion können WCF-Entwickler die Informationen in der-Datenbank verwenden, um Dienst Benutzer nach Rollen zu autorisieren. Beispielsweise können Sie den Rollenanbieter gemeinsam mit dem oben beschriebenen `PrincipalPermissionAttribute`-Mechanismus zur Zugriffskontrolle verwenden.  
  
 Sie können auch den ASP.NET-Rollen Anbieter verwenden, wenn Sie über eine vorhandene ASP.NET-Rollen Anbieter Datenbank verfügen und denselben Satz von Regeln und Benutzer Zuweisungen in Ihrem WCF-Dienst verwenden möchten.  
  
 Weitere Informationen zur Verwendung der Rollen Anbieter Funktion finden Sie unter Gewusst [wie: Verwenden des ASP.NET-Rollen Anbieters mit einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).  
  
## <a name="authorization-manager"></a>Autorisierungs-Manager  
 Ein weiteres Feature kombiniert den Autorisierungs-Manager (AzMan) mit dem ASP.NET-Rollen Anbieter, um Clients zu autorisieren. Wenn ASP.net einen Webdienst hostet, kann AzMan in die Anwendung integriert werden, damit die Autorisierung für den Dienst über AzMan erfolgt. ASP.net Role Manager bietet eine API, mit der Sie Anwendungs Rollen verwalten, Benutzer zu Rollen hinzufügen und aus Rollen entfernen und Rollen Mitgliedschaften überprüfen können. es ist jedoch nicht möglich, abzufragen, ob ein Benutzer berechtigt ist, eine benannte Aufgabe oder einen benannten Vorgang auszuführen. AzMan ermöglicht es Ihnen, einzelne Vorgänge zu definieren und sie in Aufgaben zu kombinieren. Mit AZMan können Sie neben Rollenüberprüfungen auch feststellen, ob ein Benutzer eine Aufgabe ausführen kann. Rollenzuweisungen und Aufgabenautorisierungen können außerhalb der Anwendung konfiguriert oder programmgesteuert innerhalb der Anwendung ausgeführt werden. Das Snap-In der Microsoft Management Console (MMC) für die AzMan-Verwaltung ermöglicht Administratoren, die Aufgaben zu ändern, die eine Rolle während der Laufzeit ausführen kann, und die Rollenmitgliedschaft jedes Benutzers zu verwalten.  
  
 Sie können auch AzMan und den ASP.NET-Rollen Anbieter verwenden, wenn Sie bereits Zugriff auf eine vorhandene AzMan-Installation haben und die Dienst Benutzer mithilfe der Funktionen der Kombination aus AzMan/Role Provider autorisieren möchten.  
  
 Weitere Informationen zu AzMan und dem Rollen Anbieter ASP.net finden Sie unter Gewusst [wie: Verwenden des Autorisierungs-Managers (AzMan) mit ASP.NET 2,0](https://docs.microsoft.com/previous-versions/msp-n-p/ff649313(v=pandp.10)). Weitere Informationen zur Verwendung von AzMan und dem Rollen Anbieter für WCF-Dienste finden Sie unter Gewusst [wie: Verwenden des ASP.net Authorization Manager-Rollen Anbieters mit einem-Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md).  
  
## <a name="identity-model"></a>Identitätsmodell  
 Das Identitätsmodell besteht aus einem Satz APIs, die Ihnen ermöglichen, Ansprüche und Richtlinien zu verwalten, um Clients zu autorisieren. Mit dem Identitätsmodell können Sie jeden Anspruch prüfen, der in den vom Benutzer zur Authentifizierung beim Dienst verwendeten Anmeldeinformationen enthalten ist. Anschließend können Sie die Ansprüche mit den Richtlinien für diesen Dienst vergleichen und den Zugriff entsprechend gewähren oder verweigern.  
  
 Verwenden Sie das Identitätsmodell, wenn Sie eine präzise Steuerung wünschen und bestimmte Kriterien festlegen möchten, bevor Sie den Zugriff gewähren. Wenn Sie z. B. das <xref:System.Security.Permissions.PrincipalPermissionAttribute> verwenden, besteht das Kriterium ganz einfach darin, dass der Benutzer authentifiziert sein und zu einer bestimmten Rolle gehören muss. Dagegen können Sie mit dem Identitätsmodell eine Richtlinie erstellen, die besagt, dass der Benutzer über 18 Jahre alt sein und einen gültigen Führerschein besitzen muss, bevor er ein Dokument anzeigen darf.  
  
 Ein Beispiel für den Nutzen, den Ihnen die anspruchsbasierte Zugriffssteuerung des Identitätsmodells bieten kann, ist die Verwendung von Verbundanmeldeinformationen im Szenario für ausgestellte Token. Weitere Informationen zu Verbund Token und ausgestellten Token finden Sie unter Verbund [-und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
 Weitere Informationen zum Identitäts Modell finden Sie unter [Verwalten von Ansprüchen und Autorisierung mit dem Identitäts Modell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- [Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [Vorgehensweise: Verwenden des ASP.NET-Rollenanbieters mit einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [Vorgehensweise: Verwenden des ASP.NET-Autorisierungs-Manager-Rollenanbieters mit einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)
- [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
- [Delegierung und Identitätswechsel](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)
