---
title: Generieren von Datentypklassen aus XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: d66cbd1806b90d21a483d0c470f953ddfb9c4fca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184131"
---
# <a name="generating-data-type-classes-from-xml"></a>Generieren von Datentypklassen aus XML
.NET Framework 4.5 enthält eine neue Funktion zum Generieren von Datentypklassen aus XML. In diesem Thema wird beschrieben, wie Datentypen automatisch für den .NET Blog RSS-Feed generiert werden.  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a>Abrufen des XML-Codes aus dem .NET Blog RSS-Feed  
  
1. Navigieren Sie in Internet Explorer zum [.NET Blog RSS-Feed](https://devblogs.microsoft.com/dotnet/feed/).  
  
2. Klicken Sie mit der rechten Maustaste auf die Seite, und wählen Sie **Quelle anzeigen**aus.  
  
3. Kopieren Sie den Text des Feeds, indem Sie **Strg+A** drücken, um den gesamten Text auszuwählen, und **Strg+C** zum Kopieren.  
  
### <a name="creating-the-data-types"></a>Erstellen der Datentypen  
  
1. Öffnen Sie eine Codedatei, in der der Proxy verwendet werden soll. Diese Datei sollte Teil eines .NET Framework 4.5-Projekts sein.  
  
2. Platzieren Sie den Cursor an einer Position in der Datei außerhalb der vorhandenen Klassen.  
  
3. Wählen Sie **Bearbeiten**, **Einfügen von Spezial**, Xml als Klassen **einfügen**.  
  
4. Klassen `link`mit `rss` `rssChannel`dem `rssChannelImage` `rssChannelItem` Namen `rssChannelItemGuid` , , , und werden mit den erforderlichen Membern für den Zugriff auf die Elemente im RSS-Feed erstellt.  
  
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
