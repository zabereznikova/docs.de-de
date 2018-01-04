---
title: Generieren von Datentypklassen aus XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 30d6035e04f09ae1169ef8e89bcfb38470be9d12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="generating-data-type-classes-from-xml"></a>Generieren von Datentypklassen aus XML
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] enthält eine neue Funktion zum Generieren von Datentypklassen aus XML. Dieses Thema beschreibt, wie Datentypen automatisch für den .NET Blog RSS-feed zu generieren.  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a>Abrufen von XML aus dem .NET Blog RSS-feed  
  
1.  Wechseln Sie in Internet Explorer, um die [.NET Blog RSS-feed](https://blogs.msdn.microsoft.com/dotnet/feed/).  
  
2.  Mit der rechten Maustaste in der Seite, und wählen Sie **Quelltext anzeigen**.  
  
3.  Kopieren Sie den Text des Feeds durch Drücken von **STRG + A** auf den gesamten Text auszuwählen und **STRG + C** zu kopieren.  
  
### <a name="creating-the-data-types"></a>Erstellen der Datentypen  
  
1.  Öffnen Sie eine Codedatei, in der der Proxy verwendet werden soll. Diese Datei sollte Teil eines [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]-Projekts sein.  
  
2.  Platzieren Sie den Cursor an einer Position in der Datei außerhalb der vorhandenen Klassen.  
  
3.  Wählen Sie **bearbeiten**, **"Inhalte einfügen"**, **XML als Klassen einfügen**.  
  
4.  Klassen, die aufgerufen `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` und `rssChannelItemGuid` werden mit den erforderlichen Membern erstellt, für den Zugriff auf die Elemente im RSS-feed.  
  
### <a name="using-the-generated-classes"></a>Verwenden der generierten Klassen  
  
1.  Nachdem die Klassen generiert wurden, können sie wie jede andere Klasse im Code verwendet werden. Im folgenden Codebeispiel wird eine neue Instanz der `rssChannelImage`-Klasse zurückgegeben.  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```
