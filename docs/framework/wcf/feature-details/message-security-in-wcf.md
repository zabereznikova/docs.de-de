---
title: "Nachrichtensicherheit in WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a80efb59-591a-4a37-bb3c-8fffa6ca0b7d
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Nachrichtensicherheit in WCF
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verfügt über zwei Hauptmodi zum Bereitstellen von Sicherheit \(`Transport` und `Message`\) und einen dritten Modus \(`TransportWithMessageCredential`\), der diese zwei Modi kombiniert.In diesem Thema werden die Nachrichtensicherheit und die Gründe für deren Verwendung erläutert.  
  
## Was ist Nachrichtensicherheit?  
 Durch Nachrichtensicherheit werden Nachrichten mithilfe der WS\-Sicherheitsspezifikation gesichert.Die WS\-Sicherheitsspezifikation enthält Erweiterungen des SOAP\-Messaging, durch die Vertraulichkeit, Integrität und Authentifizierung auf SOAP\-Nachrichtenebene \(statt der Transportebene\) sichergestellt werden.  
  
 Der Unterschied zwischen Nachrichtensicherheit und Transportsicherheit besteht kurz gesagt darin, dass bei der Nachrichtensicherheit die Sicherheitsanmeldeinformationen und Ansprüche zusammen mit dem Nachrichtenschutz in jeder Nachricht gekapselt werden \(Signierung oder Verschlüsselung\).Die direkte Anwendung der Sicherheit auf die Nachricht durch das Ändern des Nachrichteninhalts ermöglicht gesicherte Nachrichten, die in Bezug auf Sicherheitsaspekte unabhängig sind.Hierdurch werden bestimmte Szenarien unterstützt, die bei Verwendung von Transportsicherheit nicht möglich sind.  
  
## Gründe für die Verwendung von Nachrichtensicherheit  
 Bei Verwendung von Sicherheit auf Nachrichtenebene sind alle Sicherheitsinformationen in der Nachricht gekapselt.Die Sicherung von Nachrichten mit Sicherheit auf Nachrichtenebene anstelle von Sicherheit auf Transportebene bietet folgende Vorteile:  
  
-   End\-to\-End\-Sicherheit.Transportsicherheit, z. B. Secure Sockets Layer \(SSL\), schützt Nachrichten nur bei Punkt\-zu\-Punkt\-Kommunikation.Wenn die Nachricht vor dem Erreichen des eigentlichen Empfängers an einen oder mehrere SOAP\-Vermittler \(z. B. einen Router\) weitergeleitet wird, ist die Nachricht selbst nicht mehr geschützt, sobald ein Vermittler diese liest.Darüber hinaus stehen die Clientauthentifizierungsinformationen nur dem ersten Vermittler zur Verfügung und müssen bei Bedarf erneut an den endgültigen Empfänger übertragen werden.Dies gilt auch dann, wenn auf dem gesamten Übertragungsweg SSL\-Sicherheit zwischen den einzelnen Übertragungen verwendet wird.Da die Nachrichtensicherheit direkt auf die Nachricht angewendet wird und deren XML\-Inhalt sichert, bleibt die Sicherheit der Nachricht unabhängig von der Anzahl der Vermittler gewahrt, bevor die Nachricht den endgültigen Empfänger erreicht.Dies ermöglicht ein wahres End\-to\-End\-Sicherheitsszenario.  
  
-   Mehr Flexibilität.Es können statt der ganzen Nachricht auch nur Teile der Nachricht signiert oder verschlüsselt werden.Auf diese Weise können die Vermittler die Nachrichtenteile anzeigen, die für sie bestimmt sind.Wenn der Absender möchte, dass die Informationen in der Nachricht für die Vermittler teilweise sichtbar sind, deren Bearbeitung jedoch ausgeschlossen werden soll, kann er die Nachricht nur signieren und unverschlüsselt lassen.Da die Signatur Teil der Nachricht ist, kann der endgültige Empfänger überprüfen, ob die Informationen in der Nachricht unverändert geblieben sind.Ein Szenario könnte sein, dass ein SOAP\-Vermittlungsdienst Nachrichten entsprechend dem Aktionsheaderwert weiterleitet.Standardmäßig verschlüsselt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] den Aktionswert nicht, sondern signiert diesen, wenn Nachrichtensicherheit verwendet wird.Daher stehen die Informationen allen Vermittlern zur Verfügung, können von diesen jedoch nicht geändert werden.  
  
-   Unterstützung mehrerer Transporte.Sie können gesicherte Nachrichten über viele verschiedene Transporte senden, z. B. benannte Pipes und TCP, ohne sich hinsichtlich Sicherheit auf das Protokoll verlassen zu müssen.Bei Sicherheit auf Transportebene sind alle Sicherheitsinformationen auf eine einzelne Transportverbindung beschränkt und nicht im Nachrichteninhalt selbst verfügbar.Bei Nachrichtensicherheit wird die Nachricht unabhängig von dem für die Übertragung der Nachricht verwendeten Transport gesichert, und der Sicherheitskontext ist direkt in die Nachricht eingebettet.  
  
-   Unterstützung eines umfangreichen Satzes von Anmeldeinformationen und Ansprüchen.Die Nachrichtensicherheit basiert auf der WS\-Sicherheitsspezifikation. Diese bietet ein erweiterungsfähiges Framework, mit dem jegliche Art von Anspruch innerhalb der SOAP\-Nachricht übertragen werden kann.Im Gegensatz zur Transportsicherheit ist der Satz von Authentifizierungsmechanismen oder Ansprüchen, die Sie verwenden können, nicht durch die Transportfunktionen beschränkt.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] umfasst mehrere Typen der Authentifizierung und Anspruchübertragung und kann bei Bedarf auf zusätzliche Typen erweitert werden.Aus diesen Gründen ist beispielsweise ein Szenario mit verbundenen Anmeldeinformationen ohne Nachrichtensicherheit nicht möglich.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] über Verbundszenarien, die von WCF unterstützt werden, finden Sie unter [Verbund und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
## Vergleich von Nachrichten\- und Transportsicherheit  
  
### Vor\- und Nachteile der Sicherheit auf Transportebene  
 Die Transportsicherheit bietet folgende Vorteile:  
  
-   Es ist nicht erforderlich, dass die Kommunikationspartner mit den Konzepten der Sicherheit auf XML\-Ebene vertraut sind.Dies trägt zu einer besseren Interoperabilität bei, z. B. wenn zum Sichern der Kommunikation HTTPS verwendet wird.  
  
-   Insgesamt höhere Leistung.  
  
-   Hardwarebeschleunigung ist verfügbar.  
  
-   Streaming ist möglich.  
  
 Die Transportsicherheit hat folgende Nachteile:  
  
-   Nur Hop\-to\-Hop \(übertragungsbasiert\).  
  
-   Beschränkter und nicht erweiterbarer Satz von Anmeldeinformationen.  
  
-   Transportabhängig.  
  
### Nachteile von Sicherheit auf Nachrichtenebene  
 Die Nachrichtensicherheit hat folgende Nachteile:  
  
-   Leistung  
  
-   Nachrichtenstreaming kann nicht verwendet werden.  
  
-   Erfordert die Implementierung von Sicherheitsmechanismen auf XML\-Ebene und Unterstützung der WS\-Sicherheitsspezifikation.Dies kann sich auf die Interoperabilität auswirken.  
  
## Siehe auch  
 [Sichern von Diensten und Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Transportsicherheit](../../../../docs/framework/wcf/feature-details/transport-security.md)   
 [Vorgehensweise: Verwenden von Transportsicherheit und Nachrichtenanmeldeinformationen](../../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md)   
 [Microsoft Patterns and Practices, Chapter 3: Implementing Transport and Message Layer Security \(in englischer Sprache\)](http://go.microsoft.com/fwlink/?LinkId=88897)