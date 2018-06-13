---
title: Generieren von Datentypklassen aus XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: 6b38a0aea3101c70b3c3ec0c8feb4ee88018b64e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498666"
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
