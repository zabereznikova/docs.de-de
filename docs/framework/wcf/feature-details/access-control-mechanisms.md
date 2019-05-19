---
title: Zugriffssteuerungsmechanismen
ms.date: 03/30/2017
helpviewer_keywords:
- WCF security
- access control [WCF]
ms.assetid: 9d576122-3f55-4425-9acf-b23d0781e966
ms.openlocfilehash: 9ebd1489c35bb3b023ed73cd86fac1b6a352012b
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882169"
---
# <a name="access-control-mechanisms"></a>Zugriffssteuerungsmechanismen
Sie können den Zugriff auf verschiedene Weise mit Windows Communication Foundation (WCF) steuern. In diesem Thema werden kurz die verschiedenen Mechanismen besprochen und Vorschläge dazu unterbreitet, wann die einzelnen Mechanismen eingesetzt werden sollten. Dies soll Ihnen die Wahl des richtigen Mechanismus erleichtern. Die Zugriffstechnologien sind in der Reihenfolge der Komplexität aufgelistet. Die einfachste Technologie ist das <xref:System.Security.Permissions.PrincipalPermissionAttribute>; die komplexeste ist das Identitätsmodell.  
  
 Zusätzlich zu diesen Methoden, Identitätswechsel und Delegierung mit WCF wird in erläutert [Delegierung und Identitätswechsel](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
## <a name="principalpermissionattribute"></a>PrincipalPermissionAttribute  
 Das <xref:System.Security.Permissions.PrincipalPermissionAttribute> wird verwendet, um den Zugriff auf eine Dienstmethode einzuschränken. Wenn das Attribut an eine Methode angewendet wird, kann es zum Anfordern der Identität des Aufrufers auf eine bestimmte oder die Mitgliedschaft in einer Windows-Gruppe oder Rolle von ASP.NET verwendet werden. Wenn der Client mit einem X.509-Zertifikat authentifiziert ist, erhält er eine primäre Identität, die aus dem Betreffnamen und dem Fingerabdruck des Zertifikats besteht.  
  
 Verwenden Sie das <xref:System.Security.Permissions.PrincipalPermissionAttribute>, um den Zugriff auf Ressourcen auf dem Computer zu kontrollieren, auf dem der Dienst ausgeführt wird, sofern der Benutzer des Diensts immer zur selben Windows-Domäne gehört, auf der der Dienst ausgeführt wird. Sie können ganz einfach Windows-Gruppen erstellen, die über festgelegte Zugriffsebenen verfügen (z. B. kein Zugriff, schreibgeschützter Zugriff oder Schreibzugriff).  
  
 Weitere Informationen zur Verwendung des Attributs finden Sie unter [Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md). Weitere Informationen zur Identität finden Sie unter [Dienstidentität und Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## <a name="aspnet-membership-provider"></a>ASP.NET-Mitgliedschaftsanbieter  
 Ein Feature von ASP.NET ist der Mitgliedschaftsanbieter. Obwohl der Mitgliedschaftsanbieter technisch gesehen kein Mechanismus zur Zugriffskontrolle ist, ermöglicht er eine Kontrolle des Zugriffs auf den Dienst, indem er die Anzahl der möglichen Identitäten begrenzt, die auf die Endpunkte des Diensts zugreifen können. Die Mitgliedschaftsfunktion umfasst eine Datenbank, in die der Benutzername und das Kennwort eingegeben werden können, mit denen Benutzer einer Website Konten auf der Site einrichten können. Um auf einen Dienst zuzugreifen, der den Mitgliedschaftsanbieter verwendet, muss sich der Benutzer mit seinem Benutzernamen und Kennwort anmelden.  
  
> [!NOTE]
>  Sie müssen zuerst Auffüllen die Datenbank mithilfe der Funktion, bevor sie ein WCF-Dienst für die Autorisierung verwenden kann.  
  
 Sie können die Mitgliedschaftsfunktion auch verwenden, wenn Sie bereits eine Mitgliedschaftsdatenbank aus einer vorhandenen Website mit ASP.NET Web und aktivieren die gleichen Benutzer Ihren Dienst mit dem gleichen Benutzernamen und Kennwörter verwenden möchten.  
  
 Weitere Informationen zur Verwendung der Mitgliedschaftsfunktion in einem WCF-Dienst finden Sie unter [Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).  
  
## <a name="aspnet-role-provider"></a>ASP.NET-Rollenanbieter  
 Ein weiteres Feature von ASP.NET ist die Möglichkeit zum Verwalten der Autorisierung mithilfe von Rollen. Der ASP.NET-Rollenanbieter kann es sich um ein Entwickler zum Erstellen von Rollen für Benutzer und jeder Benutzer eine Rolle oder Rollen zuweisen. Wie bei der Mitgliedschaftsanbieter, müssen Sie die Rollen und Zuweisungen werden in einer Datenbank gespeichert und können mit Tools von einer bestimmten Implementierung von den ASP.NET-Rollenanbieter aufgefüllt werden. Wie bei der Mitgliedschaftsfunktion können WCF-Entwickler die Informationen in der Datenbank um Dienstbenutzer nach Rollen zu autorisieren. Beispielsweise können Sie den Rollenanbieter gemeinsam mit dem oben beschriebenen `PrincipalPermissionAttribute`-Mechanismus zur Zugriffskontrolle verwenden.  
  
 Sie können auch den ASP.NET-Rollenanbieter verwenden, wenn Sie eine vorhandene ASP.NET-rollenanbieterdatenbank haben und den gleichen Satz von Regeln und benutzerzuweisungen in der WCF-Dienst verwenden möchten.  
  
 Weitere Informationen zur Verwendung der rollenanbieterfunktion finden Sie unter [Vorgehensweise: Verwenden des ASP.NET-Rollenanbieters mit einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).  
  
## <a name="authorization-manager"></a>Autorisierungs-Manager  
 Eine andere Funktion kombiniert den Autorisierungs-Manager (AzMan) mit den ASP.NET-Rollenanbieter um Clients zu autorisieren. Wenn ASP.NET auf einen Webdienst hostet, kann AzMan in die Anwendung integriert werden, damit die Autorisierung für den Dienst über AzMan erfolgt. ASP.NET-Rollen-Manager bietet eine API, die Sie Anwendungsrollen verwalten kann hinzufügen und Entfernen von Benutzern Rollen und Rollenmitgliedschaften überprüfen, aber das ist nicht zugelassen Abfragen, ob ein Benutzer autorisiert ist, um eine Aufgabe oder einen Vorgang auszuführen. AzMan ermöglicht es Ihnen, einzelne Vorgänge zu definieren und sie in Aufgaben zu kombinieren. Mit AZMan können Sie neben Rollenüberprüfungen auch feststellen, ob ein Benutzer eine Aufgabe ausführen kann. Rollenzuweisungen und Aufgabenautorisierungen können außerhalb der Anwendung konfiguriert oder programmgesteuert innerhalb der Anwendung ausgeführt werden. Das Snap-In der Microsoft Management Console (MMC) für die AzMan-Verwaltung ermöglicht Administratoren, die Aufgaben zu ändern, die eine Rolle während der Laufzeit ausführen kann, und die Rollenmitgliedschaft jedes Benutzers zu verwalten.  
  
 Sie können auch AzMan und den ASP.NET-Rollenanbieter verwenden, wenn Sie bereits Zugriff auf eine bestehende AzMan-Installation haben, und Ihre Dienstbenutzer über die Funktionen von der AzMan/Rollenanbieter-Kombination autorisieren möchten.  
  
 Weitere Informationen zu AzMan und den ASP.NET-Rollenanbieter finden Sie unter [so wird's gemacht: Use Authorization Manager (AzMan) mit ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=88951). Weitere Informationen zur Verwendung von AzMan und des Rollenanbieters für WCF-Dienste finden Sie unter [Vorgehensweise: Verwenden Sie den Rollenanbieter ASP.NET-Autorisierungs-Manager bei einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md).  
  
## <a name="identity-model"></a>Identitätsmodell  
 Das Identitätsmodell besteht aus einem Satz APIs, die Ihnen ermöglichen, Ansprüche und Richtlinien zu verwalten, um Clients zu autorisieren. Mit dem Identitätsmodell können Sie jeden Anspruch prüfen, der in den vom Benutzer zur Authentifizierung beim Dienst verwendeten Anmeldeinformationen enthalten ist. Anschließend können Sie die Ansprüche mit den Richtlinien für diesen Dienst vergleichen und den Zugriff entsprechend gewähren oder verweigern.  
  
 Verwenden Sie das Identitätsmodell, wenn Sie eine präzise Steuerung wünschen und bestimmte Kriterien festlegen möchten, bevor Sie den Zugriff gewähren. Wenn Sie z. B. das <xref:System.Security.Permissions.PrincipalPermissionAttribute> verwenden, besteht das Kriterium ganz einfach darin, dass der Benutzer authentifiziert sein und zu einer bestimmten Rolle gehören muss. Dagegen können Sie mit dem Identitätsmodell eine Richtlinie erstellen, die besagt, dass der Benutzer über 18 Jahre alt sein und einen gültigen Führerschein besitzen muss, bevor er ein Dokument anzeigen darf.  
  
 Ein Beispiel für den Nutzen, den Ihnen die anspruchsbasierte Zugriffssteuerung des Identitätsmodells bieten kann, ist die Verwendung von Verbundanmeldeinformationen im Szenario für ausgestellte Token. Weitere Informationen zu Verbund und ausgestellte Token, finden Sie unter [Verbund und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
 Weitere Informationen zu dem Identitätsmodell, finden Sie unter [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- [Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [Vorgehensweise: Verwenden des ASP.NET-Rollenanbieters mit einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [Vorgehensweise: Verwenden Sie den Rollenanbieter ASP.NET-Autorisierungs-Manager bei einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)
- [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
- [Delegierung und Identitätswechsel](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)
