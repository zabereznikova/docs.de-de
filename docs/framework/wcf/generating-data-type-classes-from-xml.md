---
title: "Generieren von Datentypklassen aus XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Generieren von Datentypklassen aus XML
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] enthält eine neue Funktion zum Generieren von Datentypklassen aus XML.  In diesem Thema wird beschrieben, wie Datentypen automatisch für den RSS\-Feed aus der MSDN Library generiert werden.  
  
### Abrufen von XML aus dem RSS\-Feed der MSDN Library  
  
1.  Navigieren Sie in Internet Explorer zum [MSDN RSS\-Feed](http://go.microsoft.com/fwlink/?LinkId=225209).  
  
2.  Klicken Sie mit der rechten Maustaste auf die Seite, und wählen Sie **Quelle anzeigen** aus.  
  
3.  Kopieren Sie den Text des Feeds, indem Sie **STRG\+A** drücken, um den gesamten Text auszuwählen, und **STRG\+C**, um ihn zu kopieren.  
  
### Erstellen der Datentypen  
  
1.  Öffnen Sie eine Codedatei, in der der Proxy verwendet werden soll.  Diese Datei sollte Teil eines [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]\-Projekts sein.  
  
2.  Platzieren Sie den Cursor an einer Position in der Datei außerhalb der vorhandenen Klassen.  
  
3.  Wählen Sie **Bearbeiten**, **Inhalte einfügen**, **XML als Klassen einfügen**.  
  
4.  Die Klassen `rss`, `rssChannel`, `rssChannelImage` und `rssChannelItem` werden mit den erforderlichen Membern erstellt, die für den Zugriff auf Elemente im RSS\-Feed benötigt werden.  
  
### Verwenden der generierten Klassen  
  
1.  Nachdem die Klassen generiert wurden, können sie wie jede andere Klasse im Code verwendet werden.  Im folgenden Codebeispiel wird eine neue Instanz der `rssChannelImage`\-Klasse zurückgegeben.  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
  
    ```