---
title: "Peer-to-Peer-Zusammenarbeit | Microsoft Docs"
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
ms.assetid: b6216d88-bccb-4a59-9f1c-9f751708e811
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Peer-to-Peer-Zusammenarbeit
gleichberechtigt Netzwerkfunktionen sind die Auslastung der relativ leistungsstarken Computer \(Personalcomputer\) die am Rand des Internets für mehr als nur clientbasierte Rechenaufgaben vorhanden sind.  Der moderne Personalcomputer \(PC\) verfügt über einen sehr schnellen Prozessor, einen beträchtlichen Speicherplatz und eine große Festplatte, von der keine vollständig verwendet werden, wenn die allgemeine Rechenaufgaben wie E\-Mail und Webbrowsen ausführt.  Das moderne PC kann als Client und Server \(ein Peer\) für viele Typen Anwendungen leicht auftreten.  
  
-   Die gleichberechtigt Zusammenarbeits\-Infrastruktur ist eine vereinfachte Implementierung der gleichberechtigt Infrastruktur Microsoft Windows, die die Personen neben mir Dienst in Windows Vista und in späteren Plattformen nutzt.  Sie wird am besten für Peer\-aktivierte Anwendungen in einem Subnetzes verwendet, für das die Personen neben mir Dienst funktionieren, obwohl Internet\-Endpunkte oder \-Kontakte auch verarbeitet werden können.  Sie enthält den allgemeinen Kontakt\-Manager, der durch Live Messenger und andere Liv\-bewusste Anwendungen, Kontaktendpunkte, \-Verfügbarkeit und \-Vorhandensein zu bestimmen verwendet wird.  
  
## Zusammenarbeits\-Anwendungen  
 Eine typische gleichberechtigt Zusammenarbeits\-Anwendung wird aus den folgenden Schritten enthalten:  
  
-   Peer bestimmt die Identität eines Peers, der Bedeutung sind, an, eine Zusammenarbeitssitzung zu hosten  
  
-   Eine Anforderung, eine Sitzung zu hosten, wird ein gesendet, und der Hostpeer ist darauf, Zusammenarbeitsaktivität zu verwalten.  
  
-   Der Host lädt Kontakte auf dem Subnetz \(einschließlich den anfordernden Benutzer\) zu einer Sitzung ein.  
  
-   Alle Peers, die zusammenarbeiten möchten, können den Host ihren Kontaktmanagern hinzu.  
  
-   Die meisten Peers senden Einladungsantworten, ob akzeptiert oder, zurück zum Hostpeer rechtzeitig gesunken.  
  
-   Alle Peers, die zusammenarbeiten möchten, z Hostpeer abonnieren.  
  
-   Während die Peers ihre ursprüngliche Zusammenarbeitsaktivität ausführen, wird möglicherweise der Hostpeer Remote Peers seinem Kontaktmanager hinzu.  Er verarbeitet auch alle Einladungsantworten, um zu bestimmen, wer akzeptiert haben, das gesunken ist und nicht geantwortet verfügt.  Es Einladungen auf die abbrechen, die nicht geantwortet haben, oder führt möglicherweise etwas andere Aktivität aus.  
  
-   An diesem Punkt kann der Hostpeer eine Zusammenarbeitssitzung mit allen eingeladenen Peers starten, oder registrieren Sie eine Anwendung mit der Zusammenarbeitsinfrastruktur.  P2P\-Anwendungen verwenden die gleichberechtigt Zusammenarbeits\-Infrastruktur und den <xref:System.Net.PeerToPeer.Collaboration>\-Namespace, um die Kommunikation für Spiele, Anschlagbretter, Konferenz und andere serverless Vorhandenseins\-Anwendungen zu koordinieren.  
  
## gleichberechtigt Netzwerkfunktionens\-Sicherheit  
 In einer Active Directory\-Domäne stellen Domänencontroller Authentifizierungsdienste mithilfe Kerbeross.  In einer serverless Peerumgebung müssen die Peers ihre eigene Authentifizierung bereitstellen.  Für gleichberechtigt Netzwerkfunktionen kann jeder Knoten als ein Zertifizierungsstelle auftreten und die Anforderung eines Stammzertifikats in dessen Sicherheitsauswirkungen Stammspeicher jedes Peers entfernen.  Authentifizierung wird mithilfe der selbstsignierten Zertifikate bereitgestellt, formatiert als X.509\-Zertifikate.  Diese sind Zertifikate, die jedem Peer erstellt werden, der die beiden des öffentlichen Schlüssels\/des privaten Schlüssels und das Zertifikat generiert, das mit dem privaten Schlüssel signiert wird.  Das selbstsignierte Zertifikat für Authentifizierung und Informationen über die Partnerinstanz bereitzustellen verwendet.  Wie X.509\-Authentifizierung erstellt Peernetzwerkfunktionsauthentifizierung auf eine Kette von den Zertifikaten, die zurück auf einen öffentlichen Schlüssel aufzeichnen, der vertrauenswürdig ist.  
  
## Siehe auch  
 <xref:System.Net.PeerToPeer.Collaboration>   
 [Informationen zum System.NET.PeerToPeer.Collaboration\-Namespace](../../../docs/framework/network-programming/about-the-system-net-peertopeer-collaboration-namespace.md)