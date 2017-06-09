---
title: "Principal and Identity Objects | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "WindowsIdentity objects"
  - "GenericIdentity objects"
  - "GenericPrincipal objects"
  - "identity objects, about identity objects"
  - "security [.NET Framework], identity objects"
  - "principal objects, about principal objects"
  - "security [.NET Framework], principals"
  - "WindowsPrincipal objects"
ms.assetid: aa5930ad-f3d7-40aa-b6f6-c6edcd5c64f7
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Principal and Identity Objects
Verwalteter Code kann die Identität oder Rolle eines Principals über ein [Principal](frlrfSystemSecurityPrincipalIPrincipalClassTopic)\-Objekt bestimmen, das einen Verweis auf ein [Identity](frlrfSystemSecurityPrincipalIIdentityClassTopic)\-Objekt enthält.  Identitäts\- und Principalobjekte ähneln dem Konzept von Benutzer\- und Gruppenkonten.  In den meisten Netzwerkumgebungen stellen Benutzerkonten Personen oder Programme und Gruppenkonten bestimmte Kategorien von Benutzern sowie deren Rechte dar.  Entsprechend stellen Identitätsobjekte in .NET Framework Benutzer dar, während Rollen Mitgliedschaften und Sicherheitskontexte darstellen.  Das Principalobjekt kapselt in .NET Framework ein Identitätsobjekt und eine Rolle. .NET Framework\-Anwendungen gewähren dem Principal entsprechend seiner Identität oder, was häufiger der Fall ist, gemäß seiner Rolle bestimmte Rechte.  
  
## Identitätsobjekte  
 Das Identitätsobjekt kapselt Informationen über den zu prüfenden Benutzer bzw. die Entität.  Identitätsobjekte enthalten in der einfachsten Form einen Namen und einen Authentifizierungstyp.  Der Name kann ein Benutzername oder der Name eines Windows\-Kontos sein, und der Authentifizierungstyp kann entweder ein unterstütztes Anmeldeprotokoll, z. B. Kerberos V5, oder einen benutzerdefinierten Wert angeben.  .NET Framework definiert ein <xref:System.Security.Principal.GenericIdentity>\-Objekt, das für die meisten benutzerdefinierten Anmeldeszenarios verwendet werden kann, sowie ein spezielles <xref:System.Security.Principal.WindowsIdentity>\-Objekt, über das eine Anwendung Zugriff auf die Windows\-Authentifizierung erhält.  Zusätzlich können Sie eine eigene Identitätsklasse definieren, die Benutzerinformationen kapselt.  
  
 Die <xref:System.Security.Principal.IIdentity>\-Schnittstelle definiert Eigenschaften für den Zugriff auf einen Namen und einen Authentifizierungstyp wie Kerberos V5 oder NTLM.  Alle **Identity**\-Klassen implementieren die **IIdentity**\-Schnittstelle.  Es ist keine Beziehung zwischen einem **Identity**\-Objekt und dem Windows NT\-Prozesstoken erforderlich, unter dem ein Thread aktuell ausgeführt wird.  Wenn das **Identity**\-Objekt jedoch ein **WindowsIdentity**\-Objekt ist, wird davon ausgegangen, dass die Identität ein Windows NT\-Sicherheitstoken darstellt.  
  
## Principalobjekte  
 Das Principalobjekt stellt den Sicherheitskontext dar, in dem der Code ausgeführt wird.  Anwendungen, die die rollenbasierte Sicherheit implementieren, gewähren Rechte ausgehend von der einem Principalobjekt zugeordneten Rolle.  Ähnlich den Identitätsobjekten stellt .NET Framework ein <xref:System.Security.Principal.GenericPrincipal>\-Objekt und ein <xref:System.Security.Principal.WindowsPrincipal>\-Objekt bereit.  Sie können auch benutzerdefinierte Principalklassen definieren.  
  
 Die <xref:System.Security.Principal.IPrincipal>\-Schnittstelle definiert eine Eigenschaft für den Zugriff auf ein zugeordnetes **Identity**\-Objekt sowie eine Methode, mit der bestimmt werden kann, ob der durch das **Principal**\-Objekt identifizierte Benutzer zu einer angegebenen Rolle gehört.  Alle **Principal**\-Klassen implementieren die **IPrincipal**\-Schnittstelle und alle darüber hinaus erforderlichen Eigenschaften und Methoden.  Die Common Language Runtime stellt z. B. die **WindowsPrincipal**\-Klasse bereit, die zusätzliche Funktionen zum Zuordnen von Windows NT\- oder Windows 2000\-Gruppenmitgliedschaften zu Rollen implementiert.  
  
 Ein **Principal**\-Objekt ist an ein Aufrufkontextobjekt \(<xref:System.Runtime.Remoting.Messaging.CallContext>\) innerhalb einer Anwendungsdomäne \(<xref:System.AppDomain>\) gebunden.  Mit jeder neuen **AppDomain** wird gleichzeitig ein Standardaufrufkontext erstellt, sodass immer ein Aufrufkontext verfügbar ist, welches das **Principal**\-Objekt akzeptiert.  Wenn ein neuer Thread erstellt wird, wird für diesen ebenfalls ein neues **CallContext**\-Objekt erstellt.  Der Verweis auf das **Principal**\-Objekt wird automatisch vom erstellenden Thread in den **CallContext** des neuen Threads kopiert.  Wenn die Laufzeit nicht bestimmen kann, welches **Principal**\-Objekt zum Ersteller des Threads gehört, wird die Standardrichtlinie für die **Principal**\- und **Identity**\-Objekterstellung angewendet.  
  
 Eine konfigurierbare und für die Anwendungsdomäne spezifische Richtlinie definiert die Regeln, nach denen der einer neuen Anwendungsdomäne zuzuordnende **Principal**\-Objekttyp bestimmt wird.  Wenn die Sicherheitsrichtlinie dies zulässt, kann die Laufzeit **Principal**\-Objekte und **Identity**\-Objekte erstellen, die das dem aktuellen Ausführungsthread zugeordnete Betriebssystemtoken darstellen.  Standardmäßig verwendet die Laufzeit **Principal**\-Objekte und **Identity**\-Objekte, die nicht authentifizierte Benutzer darstellen.  Diese **Principal**\-Standardobjekte und **Identity**\-Standardobjekte werden von der Laufzeit erst dann erstellt, wenn ein Code auf diese zuzugreifen versucht.  
  
 Vertrauenswürdiger Code, der eine Anwendungsdomäne erstellt, kann die Richtlinie der Anwendungsdomäne festlegen, die das Erstellen der **Principal**\-Standardobjekte und **Identity**\-Standardobjekte steuert.  Diese für die Anwendungsdomäne spezifische Richtlinie gilt für alle Ausführungsthreads in dieser Anwendungsdomäne.  Ein nicht verwalteter, vertrauenswürdiger Host ist automatisch berechtigt, diese Richtlinie festzulegen. Verwalteter Code, der diese Richtlinie festlegt, muss zum Steuern der Domänenrichtlinie jedoch über <xref:System.Security.Permissions.SecurityPermission?displayProperty=fullName> verfügen.  
  
 Beim Übermitteln eines **Principal**\-Objekts zwischen Anwendungsdomänen innerhalb des gleichen Prozesses \(und daher auf dem gleichen Computer\) kopiert die Remoteinfrastruktur einen Verweis auf das dem Kontext der aufrufenden Domäne zugeordnete **Principal**\-Objekt in den Kontext der aufgerufenen Domäne.  
  
## Siehe auch  
 [How to: Create a WindowsPrincipal Object](../../../docs/standard/security/how-to-create-a-windowsprincipal-object.md)   
 [How to: Create GenericPrincipal and GenericIdentity Objects](../../../docs/standard/security/how-to-create-genericprincipal-and-genericidentity-objects.md)   
 [Replacing a Principal Object](../../../docs/standard/security/replacing-a-principal-object.md)   
 [Impersonating and Reverting](../../../docs/standard/security/impersonating-and-reverting.md)   
 [Role\-Based Security](../../../docs/standard/security/role-based-security.md)   
 [Key Security Concepts](../../../docs/standard/security/key-security-concepts.md)