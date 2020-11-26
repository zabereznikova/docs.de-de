---
title: Generieren von Datentypklassen aus XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: a7920a8c8c4f279dd3fc52029c5da5e9b685efe2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238248"
---
# <a name="generating-data-type-classes-from-xml"></a>Generieren von Datentypklassen aus XML

.NET Framework 4,5 enthält ein neues Feature zum Generieren von Datentyp Klassen aus XML. In diesem Thema wird beschrieben, wie Datentypen für den RSS-Feed des .net-Blogs automatisch generiert werden.  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a>Abrufen des XML-Codes aus dem .net-Blog-RSS-Feed  
  
1. Navigieren Sie in Internet Explorer zum [.net-Blog-RSS-Feed](https://devblogs.microsoft.com/dotnet/feed/).  
  
2. Klicken Sie mit der rechten Maustaste auf die Seite, und wählen Sie **Quelle anzeigen**  
  
3. Kopieren Sie den Text des Feeds, indem Sie **STRG + A** drücken, um den gesamten Text auszuwählen, und **STRG + C** zum Kopieren.  
  
### <a name="creating-the-data-types"></a>Erstellen der Datentypen  
  
1. Öffnen Sie eine Codedatei, in der der Proxy verwendet werden soll. Diese Datei sollte Teil eines .NET Framework 4,5-Projekts sein.  
  
2. Platzieren Sie den Cursor an einer Position in der Datei außerhalb der vorhandenen Klassen.  
  
3. Wählen Sie **Bearbeiten**, **Sonderzeichen einfügen**, **XML als Klassen einfügen** aus.  
  
4. Klassen `link` , `rss` ,, `rssChannel` und `rssChannelImage` , `rssChannelItem` `rssChannelItemGuid` werden mit den erforderlichen Membern erstellt, um auf die Elemente im RSS-Feed zuzugreifen.  
  
### <a name="using-the-generated-classes"></a>Verwenden der generierten Klassen  
  
1. Nachdem die Klassen generiert wurden, können sie wie jede andere Klasse im Code verwendet werden. Im folgenden Codebeispiel wird eine neue Instanz der `rssChannelImage`-Klasse zurückgegeben.  
  
    ```csharp
    var channelImage = new rssChannelImage()
    {
        title = "MyImage",
        link = "http://www.contoso.com/images/channelImage.jpg",
        url = "http://www.contoso.com/entries/myEntry.html"
    };  
    ```
