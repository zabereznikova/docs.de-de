---
title: "Verbindungsgruppierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Internet, Verbindungen"
  - "Verbindungen [.NET Framework], Gruppierung"
  - "WebRequest-Klasse, Verbindungsgruppierung"
  - "Netzwerkressourcen, Verbindungen"
  - "Verbindungspooling"
ms.assetid: 2ec502e8-4ba0-4c22-9410-f28eaf4eee63
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Verbindungsgruppierung
Verbindung, die Mitarbeiterspezifische anfragen innerhalb einer Anwendung zu einem definierten Verbindungspool gruppiert.  Dies kann von einer Anwendung benötigt werden der mittleren Ebene, die an einen Hinterserver im Namen eines Benutzers hergestellt und verwendet ein Authentifizierungsprotokoll, das Delegierung, wie Kerberos oder über eine Anwendung der mittleren Ebene, die ihre eigenen Anmeldeinformationen enthält, wie im nachfolgenden Beispiel unterstützt.  Nehmen Sie beispielsweise einen Benutzer, Joe, Besuche eine interne Website an, die die Gehaltsabrechnungsinformationen anzeigt.  Nach dem Joe authentifiziert hat, verwendet der Anwendungsserver der mittleren Ebene Joes Anmeldeinformationen, um an den Hinterserver herzustellen, um die Gehaltsabrechnungsinformationen abzurufen.  Als Nächstes besucht Susan die Site anfordert und ihre Gehaltsabrechnungsinformationen an.  Da die Anwendung der mittleren Ebene bereits eine Beziehung mit Joes Anmeldeinformationen hergestellt hat, reagiert der Hinterserver mit Joes Informationen.  Wenn die Anwendung einer zuweist Verbindungsgruppe jede Anforderung, die dem Hinterserver gesendet werden, die vom Benutzernamen gebildet wird, dann jeder Benutzer gehört einem separaten Verbindungspool und Authentifizierungsinformationen kann mit einem anderen Benutzer nicht versehentlich freigeben.  
  
 Um eine Anforderung einer bestimmten Verbindungsgruppe zuzuweisen, müssen Sie einen Namen der <xref:System.Net.WebRequest.ConnectionGroupName%2A>\-Eigenschaft des <xref:System.Net.WebRequest> zuordnen bevor Sie die Anwendung bereitstellen.  
  
## Siehe auch  
 [Verwalten von Verbindungen](../../../docs/framework/network-programming/managing-connections.md)   
 [Gewusst wie: Zuweisen von Benutzerinformationen zu Gruppenverbindungen](../../../docs/framework/network-programming/how-to-assign-user-information-to-group-connections.md)