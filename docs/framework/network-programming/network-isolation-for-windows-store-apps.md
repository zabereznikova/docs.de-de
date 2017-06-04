---
title: "Netzwerkisolation f&#252;r Windows Store-Apps | Microsoft Docs"
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
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Netzwerkisolation f&#252;r Windows Store-Apps
Klassen in <xref:System.Net>, in <xref:System.Net.Http> und in <xref:System.Net.Http.Headers>\-Namespaces können verwendet werden, um Windows Store\-Apps oder \-Desktop\-Apps zu entwickeln.  Wenn sie in einer Windows Store\-App verwendet werden, werden Klassen in diesen Namespaces von Netzwerkisolation, Teil des Anwendungssicherheitskonzepts verwendeten durch [!INCLUDE[win8](../../../includes/win8-md.md)] beeinflusst.  Die entsprechenden Netzwerkfunktionen müssen im Anwendungsmanifest für eine Windows Store\-App aktiviert werden, damit das System Netzwerkzugriff zulässig.  
  
## Prüfliste für die Netzwerkisolation  
 Verwenden Sie diese Prüfliste sicherstellen, dass Netzwerkisolation für die Windows Store\-App konfiguriert ist.  
  
1.  Bestimmen Sie die Richtung von den Netzzuganganforderungen, die durch die Anwendung benötigt werden.  Diese kann entweder Client\-initiierte ausgehende Anforderungen sein, oder unverlangte eingehende Anforderungen oder es könnten eine Kombination beider Netzwerkanforderungstypen sein.  
  
2.  Bestimmen Sie den Typ von Netzwerkressourcen, die diese App ist.  Eine Anwendung muss möglicherweise vertrauenswürdige Ressourcen auf POS1 oder einem Arbeitsplatznetzwerk kommunizieren.  Eine Anwendung muss möglicherweise Ressourcen im Internet kommunizieren.  Eine Anwendung könnte benötigt Zugriff auf beide Typen Netzwerkressourcen.  
  
3.  Konfigurieren Sie MinimumREQUIRED, das Isolationsfunktionen im Anwendungsmanifest vernetzt.  
  
4.  Erstellen Sie die Anwendung bereit aus, um sie mit der Netzwerkisolationstools zu testen, die für die Problembehandlung bereitgestellt werden.  
  
 Ausführlichere Informationen dazu, wie Netzwerk\- und \-Isolation bearbeitet verwendet für die Problembehandlung der Netzwerkisolation, [Erstellen Netzwerkisolationsfunktionen konfiguriert](http://go.microsoft.com/fwlink/?LinkID=228265) finden Sie unter in der [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] Entwicklerdokumentation konfiguriert.  
  
## Siehe auch  
 [Verbindung mit einem Webdienst](http://go.microsoft.com/fwlink/?LinkID=245696)   
 [Richtlinien und Prüfliste für die Netzwerkisolation](http://go.microsoft.com/fwlink/?LinkID=228265)   
 [Mobile\-Schnellstart\-Lernprogrammen: Verbindung mit HttpClient](http://go.microsoft.com/fwlink/?LinkId=245697)   
 [Erstellen HttpClient\-Handler verwendet](http://go.microsoft.com/fwlink/?LinkId=245699)   
 [Erstellen HttpClient\-Verbindungen gespeichert werden](http://go.microsoft.com/fwlink/?LinkId=245698)   
 [HttpClient\-Beispiel](http://go.microsoft.com/fwlink/?LinkId=242550)