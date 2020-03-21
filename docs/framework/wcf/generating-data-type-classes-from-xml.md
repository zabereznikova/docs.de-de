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
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="028fd-102">Generieren von Datentypklassen aus XML</span><span class="sxs-lookup"><span data-stu-id="028fd-102">Generating Data Type Classes from XML</span></span>
<span data-ttu-id="028fd-103">.NET Framework 4.5 enthält eine neue Funktion zum Generieren von Datentypklassen aus XML.</span><span class="sxs-lookup"><span data-stu-id="028fd-103">.NET Framework 4.5 includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="028fd-104">In diesem Thema wird beschrieben, wie Datentypen automatisch für den .NET Blog RSS-Feed generiert werden.</span><span class="sxs-lookup"><span data-stu-id="028fd-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="028fd-105">Abrufen des XML-Codes aus dem .NET Blog RSS-Feed</span><span class="sxs-lookup"><span data-stu-id="028fd-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1. <span data-ttu-id="028fd-106">Navigieren Sie in Internet Explorer zum [.NET Blog RSS-Feed](https://devblogs.microsoft.com/dotnet/feed/).</span><span class="sxs-lookup"><span data-stu-id="028fd-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://devblogs.microsoft.com/dotnet/feed/).</span></span>  
  
2. <span data-ttu-id="028fd-107">Klicken Sie mit der rechten Maustaste auf die Seite, und wählen Sie **Quelle anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="028fd-107">Right-click the page and select **View Source**.</span></span>  
  
3. <span data-ttu-id="028fd-108">Kopieren Sie den Text des Feeds, indem Sie **Strg+A** drücken, um den gesamten Text auszuwählen, und **Strg+C** zum Kopieren.</span><span class="sxs-lookup"><span data-stu-id="028fd-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="028fd-109">Erstellen der Datentypen</span><span class="sxs-lookup"><span data-stu-id="028fd-109">Creating the data types</span></span>  
  
1. <span data-ttu-id="028fd-110">Öffnen Sie eine Codedatei, in der der Proxy verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="028fd-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="028fd-111">Diese Datei sollte Teil eines .NET Framework 4.5-Projekts sein.</span><span class="sxs-lookup"><span data-stu-id="028fd-111">This file should be part of a .NET Framework 4.5 project.</span></span>  
  
2. <span data-ttu-id="028fd-112">Platzieren Sie den Cursor an einer Position in der Datei außerhalb der vorhandenen Klassen.</span><span class="sxs-lookup"><span data-stu-id="028fd-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3. <span data-ttu-id="028fd-113">Wählen Sie **Bearbeiten**, **Einfügen von Spezial**, Xml als Klassen **einfügen**.</span><span class="sxs-lookup"><span data-stu-id="028fd-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4. <span data-ttu-id="028fd-114">Klassen `link`mit `rss` `rssChannel`dem `rssChannelImage` `rssChannelItem` Namen `rssChannelItemGuid` , , , und werden mit den erforderlichen Membern für den Zugriff auf die Elemente im RSS-Feed erstellt.</span><span class="sxs-lookup"><span data-stu-id="028fd-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="028fd-115">Verwenden der generierten Klassen</span><span class="sxs-lookup"><span data-stu-id="028fd-115">Using the generated classes</span></span>  
  
1. <span data-ttu-id="028fd-116">Nachdem die Klassen generiert wurden, können sie wie jede andere Klasse im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="028fd-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="028fd-117">Im folgenden Codebeispiel wird eine neue Instanz der `rssChannelImage`-Klasse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="028fd-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```csharp
    var channelImage = new rssChannelImage()
    {
        title = "MyImage",
        link = "http://www.contoso.com/images/channelImage.jpg",
        url = "http://www.contoso.com/entries/myEntry.html"
    };  
    ```
