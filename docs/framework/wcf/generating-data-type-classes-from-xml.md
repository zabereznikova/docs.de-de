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
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="17ad2-102">Generieren von Datentypklassen aus XML</span><span class="sxs-lookup"><span data-stu-id="17ad2-102">Generating Data Type Classes from XML</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<span data-ttu-id="17ad2-103"> enthält eine neue Funktion zum Generieren von Datentypklassen aus XML.</span><span class="sxs-lookup"><span data-stu-id="17ad2-103"> includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="17ad2-104">Dieses Thema beschreibt, wie Datentypen automatisch für den .NET Blog RSS-feed zu generieren.</span><span class="sxs-lookup"><span data-stu-id="17ad2-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="17ad2-105">Abrufen von XML aus dem .NET Blog RSS-feed</span><span class="sxs-lookup"><span data-stu-id="17ad2-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1.  <span data-ttu-id="17ad2-106">Wechseln Sie in Internet Explorer, um die [.NET Blog RSS-feed](https://blogs.msdn.microsoft.com/dotnet/feed/).</span><span class="sxs-lookup"><span data-stu-id="17ad2-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://blogs.msdn.microsoft.com/dotnet/feed/).</span></span>  
  
2.  <span data-ttu-id="17ad2-107">Mit der rechten Maustaste in der Seite, und wählen Sie **Quelltext anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="17ad2-107">Right-click the page and select **View Source**.</span></span>  
  
3.  <span data-ttu-id="17ad2-108">Kopieren Sie den Text des Feeds durch Drücken von **STRG + A** auf den gesamten Text auszuwählen und **STRG + C** zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="17ad2-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="17ad2-109">Erstellen der Datentypen</span><span class="sxs-lookup"><span data-stu-id="17ad2-109">Creating the data types</span></span>  
  
1.  <span data-ttu-id="17ad2-110">Öffnen Sie eine Codedatei, in der der Proxy verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="17ad2-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="17ad2-111">Diese Datei sollte Teil eines [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]-Projekts sein.</span><span class="sxs-lookup"><span data-stu-id="17ad2-111">This file should be part of a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="17ad2-112">Platzieren Sie den Cursor an einer Position in der Datei außerhalb der vorhandenen Klassen.</span><span class="sxs-lookup"><span data-stu-id="17ad2-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3.  <span data-ttu-id="17ad2-113">Wählen Sie **bearbeiten**, **"Inhalte einfügen"**, **XML als Klassen einfügen**.</span><span class="sxs-lookup"><span data-stu-id="17ad2-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4.  <span data-ttu-id="17ad2-114">Klassen, die aufgerufen `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` und `rssChannelItemGuid` werden mit den erforderlichen Membern erstellt, für den Zugriff auf die Elemente im RSS-feed.</span><span class="sxs-lookup"><span data-stu-id="17ad2-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="17ad2-115">Verwenden der generierten Klassen</span><span class="sxs-lookup"><span data-stu-id="17ad2-115">Using the generated classes</span></span>  
  
1.  <span data-ttu-id="17ad2-116">Nachdem die Klassen generiert wurden, können sie wie jede andere Klasse im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="17ad2-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="17ad2-117">Im folgenden Codebeispiel wird eine neue Instanz der `rssChannelImage`-Klasse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="17ad2-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```
