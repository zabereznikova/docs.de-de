---
title: "Wiederholungsangriffe | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7a17e040-93cd-4432-81b9-9f62fec78c8f
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Wiederholungsangriffe
Ein *Wiederholungsangriff* tritt auf, wenn ein Angreifer einen Nachrichtenstream zwischen zwei Parteien kopiert und den Stream für eine oder mehrere Parteien wiedergibt.Wenn der Angriff nicht abgeschwächt wird, verarbeiten die angegriffenen Computer den Stream wie zulässige Nachrichten, was eine Reihe negativer Konsequenzen wie redundante Bestellungen eines Artikels zur Folge hat.  
  
## Bindungen sind möglicherweise Reflektionsangriffen ausgesetzt  
 Bei einem *Reflektionsangriff* werden Nachrichten wiederholt an den Absender zurückgeschickt, als würden sie eine Antwort vom Empfänger darstellen.Dieses Phänomen wird von der standardmäßigen *Wiedergabeerkennung* im [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Mechanismus nicht automatisch behandelt.  
  
 Reflektionsangriffe werden standardmäßig abgeschwächt, da das [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienstmodell Anforderungsnachrichten eine signierte Nachrichtenkennung hinzufügt und in Antwortnachrichten einen signierten `relates-to`\-Header erwartet.Infolgedessen kann die Anforderungsnachricht nicht als Antwort wiederholt werden.In sicheren Szenarien mit zuverlässigem Messaging werden Reflektionsangriffe aus folgenden Gründen abgemildert:  
  
-   Die Sequenzerstellung und die Sequenzerstellungsantwort verwenden unterschiedliche Nachrichtenschemas.  
  
-   Bei Simplexsequenzen können die vom Client gesendeten Nachrichten nicht wiedergegeben werden, da diese vom Client nicht interpretiert werden können.  
  
-   Bei Duplexsequenzen müssen die beiden Sequenzkennungen eindeutig sein.Ausgehende Nachrichten können daher nicht als eingehende Nachrichten wiederholt werden \(alle Header und Texte werden ebenfalls signiert\).  
  
 Aus diesem Grund sind nur Bindungen ohne WS\-Adressierung anfällig für Reflektionsangriffe: benutzerdefinierte Bindungen, deren WS\-Adressierung deaktiviert ist und die mit symmetrischen Schlüsseln gesichert sind.Die <xref:System.ServiceModel.BasicHttpBinding> verwendet standardmäßig keine WS\-Adressierung; die Absicherung durch symmetrische Schlüssel erfolgt jedoch auf eine Art und Weise, die sie anfällig gegenüber dieser Art von Angriffen macht.  
  
 Zur Risikominderung für benutzerdefinierte Bindungen sollte auf einen Sicherheitskontext verzichtet werden, oder es sollten Header für die WS\-Adressierung verwendet werden.  
  
## Webfarm: Angriff durch Wiederholen von Anforderungen an mehrere Knoten  
 Ein Client verwendet einen Dienst, der in einer Webfarm implementiert ist.Ein Angreifer wiederholt eine Anforderung, die an einen Knoten in der Farm gesendet wurde, für einen anderen Knoten in der Farm.Zusätzlich wird beim Neustart eines Diensts der Wiederholungscache geleert, sodass der Angriff wiederholt werden kann.\(Der Cache enthält die bereits verwendeten Signaturen von Nachrichten und verhindert so, dass diese mehrfach verwendet werden können.Wiederholungscaches werden nicht von mehreren Anwendungen in einer Webfarm verwendet.\)  
  
 Folgende Maßnahmen mindern das Risiko:  
  
-   Verwenden Sie die Nachrichtenmodussicherheit mit Token für den Sicherheitszustandskontext \(mit oder ohne sichere Konversation\).[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Vorgehensweise: Erstellen eines Tokens für den Sicherheitskontext einer sicheren Sitzung](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
-   Konfigurieren Sie den Dienst für die Sicherheit auf Transportebene.  
  
## Siehe auch  
 [Sicherheitsüberlegungen](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)   
 [Veröffentlichung von Informationen](../../../../docs/framework/wcf/feature-details/information-disclosure.md)   
 [Ausweitung von Berechtigungen](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)   
 [Dienstverweigerung \(Denial of Service\)](../../../../docs/framework/wcf/feature-details/denial-of-service.md)   
 [Verfälschungen](../../../../docs/framework/wcf/feature-details/tampering.md)   
 [Nicht unterstützte Szenarien](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)