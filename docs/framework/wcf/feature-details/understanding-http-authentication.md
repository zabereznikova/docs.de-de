---
title: "Grundlagen der HTTP-Authentifizierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9376309a-39e3-4819-b47b-a73982b57620
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Grundlagen der HTTP-Authentifizierung
Die Authentifizierung besteht in der Identifizierung, ob ein Client berechtigt ist, auf eine Ressource zuzugreifen.Das HTTP\-Protokoll unterstützt die Authentifizierung zum Aushandeln des Zugriffs auf eine sichere Ressource.  
  
 Die anfängliche Anforderung von einem Client ist normalerweise eine anonyme Anforderung, die keine Authentifizierungsinformationen enthält.Die HTTP\-Serveranwendungen können die anonyme Anforderung ablehnen, während angegeben wird, dass eine Authentifizierung erforderlich ist.Die Serveranwendung sendet WWW\-Authentifizierungsheader, um die unterstützten Authentifizierungsschemen anzugeben.Dieses Dokument beschreibt mehrere Authentifizierungsschemen für HTTP und erläutert deren Unterstützung in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## HTTP\-Authentifizierungsschemen  
 Der Server kann mehrere Authentifizierungsschemen für den Client zur Auswahl angeben. Die folgende Tabelle beschreibt einige der Authentifizierungsschemas, die häufig in Windows\-Anwendungen gefunden werden.  
  
|Authentifizierungsschema|Beschreibung|  
|------------------------------|------------------|  
|Anonymous|Eine anonyme Anforderung enthält keine Authentifizierungsinformationen.Dies entspricht der Freigabe des Zugriffs auf die Ressource für alle Benutzer.|  
|Basic|Die Basic\-Authentifizierung sendet eine Base64\-codierte Zeichenfolge mit einem Benutzernamen und einem Kennwort für den Client.Base64 ist keine Verschlüsselung und kann wie der Versand des Benutzernamens und des Kennworts im Klartext verstanden werden.Wenn eine Ressource geschützt werden muss, sollten Sie möglicherweise ein anderes Authentifizierungsschema als die Basic\-Authentifizierung verwenden.|  
|Digest|Die Digest\-Authentifizierung ist ein Abfrage\/Rückmeldungsschema, das die Basic\-Authentifizierung ersetzen soll.Der Server sendet eine Zeichenfolge zufälliger Daten, auch *Nonce* genannt, als Aufforderung an den Client.Der Client reagiert mit einem Hash, das neben anderen Informationen den Benutzernamen, das Kennwort und die Nonce enthält.Die Komplexität dieses Austauschs und der Datenhash erschweren die Wiederverwendung der Benutzeranmeldeinformationen mit diesem Authentifizierungsschema.<br /><br /> Für die Digest\-Authentifizierung ist die Verwendung von Windows\-Domänenkonten erforderlich.Der Digest\-*Bereich* ist der Windows\-Domänenname.Sie können daher einen Server verwenden, der unter einem Betriebssystem ausgeführt wird, das keine Windows\-Domänen mit der Digest\-Authentifizierung unterstützt, z. B. Windows XP Home Edition.Umgekehrt muss ein Domänenkonto explizit während der Authentifizierung angegeben werden, wenn der Client unter einem Betriebssystem ausgeführt wird, das keine Windows\-Domänen unterstützt.|  
|NTLM|Die NT LAN Manager \(NTLM\)\-Authentifizierung ist ein Abfrage\/Rückmeldungsschema, das eine sicherere Variante der Digest\-Authentifizierung darstellt.NTLM verwendet die Windows\-Anmeldeinformationen, um die Abfragedaten anstelle des unverschlüsselten Benutzernamens und Kennworts zu transformieren.Die NTLM\-Authentifizierung erfordert mehrere Austausche zwischen dem Client und dem Server.Der Server sowie dazwischen liegende Proxys müssen beständige Verbindungen unterstützen, um die Authentifizierung erfolgreich abzuschließen.|  
|Negotiate|Beim Aushandeln der Authentifizierung wird automatisch, je nach Verfügbarkeit, zwischen dem Kerberos\-Protokoll und der NTLM\-Authentifizierung gewählt.Das Kerberos\-Protokoll wird verwendet, wenn es zur Verfügung steht, anderenfalls wird versucht NTML zu verwenden.Die Kerberos\-Authentifizierung stellt eine wesentliche Verbesserung der NTLM\-Authentifizierung dar.Die Kerberos\-Authentifizierung ist schneller als NTLM und ermöglicht den Einsatz einer gegenseitigen Authentifizierung und die Weiterleitung der Anmeldeinformationen an Remote\-Computer.|  
|Windows Live ID|Der zugrunde liegende Windows\-HTTP\-Dienst umfasst die Authentifizierung mit Verbundprotokollen.Die Standard\-HTTP\-Transporte in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützen jedoch nicht die Verwendung von Verbundsauthentifizierungsschemen wie Microsoft Windows Live ID.Support für diese Funktion steht derzeit durch die Verwendung der Nachrichtensicherheit zur Verfügung.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Verbund und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).|  
  
## Auswählen eines Authentifizierungsschemas  
 Bei potenziellen Authentifizierungsschemen für einen HTTP\-Server müssen u. a. die folgenden Aspekte beachtet werden:  
  
-   Überprüfen Sie, ob die Ressourcen geschützt werden müssen.Für die HTTP\-Authentifizierung müssen mehr Daten übertragen werden, zudem kann die Interoperabilität mit Clients eingeschränkt werden.Lassen Sie den anonymen Zugriff auf Ressourcen zu, die nicht geschützt werden müssen.  
  
-   Wenn die Ressource geschützt werden muss, überlegen Sie, welche Authentifizierungsschemen die gewünschte Sicherheitsstufe bieten.Das "schwächste", hier erläuterte Standardauthentifizierungsschema ist die Basic\-Authentifizierung.Die Basic\-Authentifizierung schützt nicht die Benutzeranmeldeinformationen.Das "stärkste" Standardauthentifizierungsschema ist die Negotiate\-Authentifizierung, die zum Kerberos\-Protokoll führt.  
  
-   Ein Server sollte kein Schema enthalten \(in den WWW\-Authentifizierungsheadern\), das die geschützten Ressourcen nicht akzeptieren bzw. angemessen sichern kann.Clients können aus den unterschiedlichen Authentifizierungsschemen des Servers wählen.Einige Clients wählen standardmäßig ein schwaches Authentifizierungsschema oder das erste Authentifizierungsschema in der Liste des Servers.  
  
## Siehe auch  
 [Übersicht über die Transportsicherheit](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)   
 [Identitätswechsel und Transportsicherheit](../../../../docs/framework/wcf/feature-details/using-impersonation-with-transport-security.md)   
 [Delegierung und Identitätswechsel](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)