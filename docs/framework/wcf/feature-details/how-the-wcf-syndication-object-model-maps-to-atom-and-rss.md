---
title: Wie das WCF-Syndication-Objektmodell Atom und RSS zugeordnet wird
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0365eb37-98cc-4b13-80fb-f1e78847a748
ms.openlocfilehash: 67fbbb035a3a6683cefbf24e299f32579b674bbd
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597253"
---
# <a name="how-the-wcf-syndication-object-model-maps-to-atom-and-rss"></a>Wie das WCF-Syndication-Objektmodell Atom und RSS zugeordnet wird
Wenn Sie einen Windows Communication Foundation (WCF)-Syndizierungs Dienst entwickeln, erstellen Sie Feeds und Elemente mithilfe der folgenden Klassen:  
  
- <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
- <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
- <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
- <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
- <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
- <xref:System.ServiceModel.Syndication.TextSyndicationContent>  
  
- <xref:System.ServiceModel.Syndication.UrlSyndicationContent>  
  
- <xref:System.ServiceModel.Syndication.XmlSyndicationContent>  
  
 Ein <xref:System.ServiceModel.Syndication.SyndicationFeed> kann in jedes beliebige Syndication-Format serialisiert werden, für das ein Formatierungsprogramm definiert ist. WCF ist mit zwei Formatierern ausgeliefert: <xref:System.ServiceModel.Syndication.Atom10FeedFormatter> und <xref:System.ServiceModel.Syndication.Rss20FeedFormatter> .  
  
 Das Objektmodell um <xref:System.ServiceModel.Syndication.SyndicationFeed> und <xref:System.ServiceModel.Syndication.SyndicationItem> orientiert sich näher an der Atom&#160;1.0-Spezifikation als der RSS&#160;2.0-Spezifikation. Das liegt daran, dass Atom&#160;1.0 eine umfassendere Spezifikation ist, die Elemente definiert, die in der RSS&#160;2.0-Spezifikation nicht eindeutig sind oder fehlen. Aus diesem Grund haben viele Elemente im WCF-Syndizierungs-Objektmodell keine direkte Darstellung in der RSS 2,0-Spezifikation. Beim Serialisieren <xref:System.ServiceModel.Syndication.SyndicationFeed> <xref:System.ServiceModel.Syndication.SyndicationItem> von-Objekten und-Objekten in RSS 2,0 ermöglicht WCF das Serialisieren Atom-spezifischer Datenelemente als Namespace-qualifizierte Erweiterungs Elemente, die der Atom-Spezifikation entsprechen. Sie können diesen Vorgang anhand eines Parameters steuern, der an den <xref:System.ServiceModel.Syndication.Rss20FeedFormatter>-Konstruktor übergeben wird.  
  
 Für die Codebeispiele in diesem Thema wird eine der beiden hier definierten Methoden für die Serialisierung verwendet.  
  
 `SerializeFeed` serialisiert einen Syndication-Feed.  
  
 [!code-csharp[SyndicationMapping#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#10)]
 [!code-vb[SyndicationMapping#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#10)]  
  
 `SerializeItem` serialisiert ein Syndication-Element.  
  
 [!code-csharp[SyndicationMapping#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#11)]
 [!code-vb[SyndicationMapping#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#11)]  
  
## <a name="syndicationfeed"></a>SyndicationFeed  
 Das folgende Codebeispiel zeigt, wie die <xref:System.ServiceModel.Syndication.SyndicationFeed>-Klasse in Atom&#160;1.0 und RSS&#160;2.0 serialisiert wird.  
  
 [!code-csharp[SyndicationMapping#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#0)]
 [!code-vb[SyndicationMapping#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#0)]  
  
 Im folgenden XML wird gezeigt, wie die <xref:System.ServiceModel.Syndication.SyndicationFeed> in Atom&#160;1.0 serialisiert wird.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<feed xml:lang="EN-US" xmlns="http://www.w3.org/2005/Atom">  
  <title type="text">My Feed Title</title>  
  <subtitle type="text">My Feed Description</subtitle>  
  <id>FeedID</id>  
  <rights type="text">Copyright 2007</rights>  
  <updated>2007-08-29T13:57:17-07:00</updated>  
  <category term="categoryName" label="categoryLabel" scheme="categoryScheme" />  
  <logo>http://server/image.jpg</logo>  
  <generator>Sample Code</generator>  
  <link rel="alternate" href="http://myfeeduri/" />  
  <entry>  
    <id>ItemID</id>  
    <title type="text">Item Title</title>  
    <summary type="text">Item Summary</summary>  
    <published>2007-08-29T00:00:00-07:00</published>  
    <updated>2007-08-29T13:57:17-07:00</updated>  
    <author>  
      <name>Jesper Aaberg</name>  
      <uri>http://Jesper/Aaberg</uri>  
      <email>Jesper@Aaberg.com</email>  
    </author>  
    <contributor>  
      <name>Lene Aaling</name>  
      <uri>http://Lene/Aaling</uri>  
      <email>Lene@Aaling.com</email>  
    </contributor>  
    <link rel="alternate" href="http://myitemuri/" />  
    <category term="categoryName" label="categoryLabel" scheme="categoryScheme" />  
    <content type="text">Item Content</content>  
    <rights type="text">Copyright 2007</rights>  
    <source>  
      <title type="text">My Feed Title</title>  
      <subtitle type="text">My Feed Description</subtitle>  
      <id>FeedID</id>  
      <rights type="text">Copyright 2007</rights>  
      <updated>2007-08-29T13:57:17-07:00</updated>  
      <category term="categoryName" label="categoryLabel" scheme="categoryScheme" />  
      <logo>http://server/image.jpg</logo>  
      <generator>Sample Code</generator>  
      <link rel="alternate" href="http://myfeeduri/" />  
    </source>  
  </entry>  
</feed>  
```  
  
 Im folgenden XML wird gezeigt, wie die <xref:System.ServiceModel.Syndication.SyndicationFeed> in RSS&#160;2.0 serialisiert wird.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<rss xmlns:a10="http://www.w3.org/2005/Atom" version="2.0">  
  <channel>  
    <title>My Feed Title</title>  
    <link>http://myfeeduri/</link>  
    <description>My Feed Description</description>  
    <language>EN-US</language>  
    <copyright>Copyright 2007</copyright>  
    <lastBuildDate>Wed, 29 Aug 2007 13:57:17 -0700</lastBuildDate>  
    <category domain="categoryScheme">categoryName</category>  
    <generator>Sample Code</generator>  
    <image>  
      <url>http://server/image.jpg</url>  
      <title>My Feed Title</title>  
      <link>http://myfeeduri/</link>  
    </image>  
    <a10:id>FeedID</a10:id>  
    <item>  
      <guid isPermaLink="false">ItemID</guid>  
      <link>http://myitemuri/</link>  
      <author>Jesper@Aaberg.com</author>  
      <category domain="categoryScheme">categoryName</category>  
      <title>Item Title</title>  
      <description>Item Summary</description>  
      <source>My Feed Title</source>  
      <pubDate>Wed, 29 Aug 2007 00:00:00 -0700</pubDate>  
      <a10:updated>2007-08-29T13:57:17-07:00</a10:updated>  
      <a10:rights type="text">Copyright 2007</a10:rights>  
      <a10:content type="text">Item Content</a10:content>  
      <a10:contributor>  
        <a10:name>Lene Aaling</a10:name>  
        <a10:uri>http://Lene/Aaling</a10:uri>  
        <a10:email>Lene@Aaling.com</a10:email>  
      </a10:contributor>  
    </item>  
  </channel>  
</rss>  
```  
  
## <a name="syndicationitem"></a>SyndicationItem  
 Das folgende Codebeispiel zeigt, wie die <xref:System.ServiceModel.Syndication.SyndicationItem>-Klasse in Atom&#160;1.0 und RSS&#160;2.0 serialisiert wird.  
  
 [!code-csharp[SyndicationMapping#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#1)]
 [!code-vb[SyndicationMapping#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#1)]  
  
 Im folgenden XML wird gezeigt, wie die <xref:System.ServiceModel.Syndication.SyndicationItem> in Atom&#160;1.0 serialisiert wird.  
  
```xml  
<entry xmlns="http://www.w3.org/2005/Atom">  
  <id>ItemID</id>  
  <title type="text">Item Title</title>  
  <summary type="text">Item Summary</summary>  
  <published>2007-08-29T00:00:00-07:00</published>  
  <updated>2007-08-29T14:07:09-07:00</updated>  
  <author>  
    <name>Jesper Aaberg</name>  
    <uri>http://Contoso/Aaberg</uri>  
    <email>Jesper.Aaberg@contoso.com</email>  
  </author>  
  <author>  
    <name>Syed Abbas</name>  
    <uri>http://Contoso/Abbas</uri>  
    <email>Syed.Abbas@contoso.com</email>  
  </author>  
  <contributor>  
    <name>Lene Aaling</name>  
    <uri>http://Contoso/Aaling</uri>  
    <email>Lene.Aaling@contoso.com</email>  
  </contributor>  
  <contributor>  
    <name>Kim Abercrombie</name>  
    <uri>http://Contoso/Abercrombie</uri>  
    <email>Kim.Abercrombie@contoso.com</email>  
  </contributor>  
  <link rel="alternate" href="http://myitemuri/" />  
  <category term="categoryName" label="categoryLabel" scheme="categoryScheme" />  
  <category term="categoryName" label="categoryLabel" scheme="categoryScheme" />  
  <content type="text">Item Content</content>  
  <rights type="text">Copyright 2007</rights>  
  <source>  
    <title type="text">My Feed Title</title>  
    <subtitle type="text">My Feed Description</subtitle>  
    <link rel="alternate" href="http://myfeeduri/" />  
  </source>  
</entry>  
```  
  
 Im folgenden XML wird gezeigt, wie die <xref:System.ServiceModel.Syndication.SyndicationItem> in RSS&#160;2.0 serialisiert wird.  
  
```xml  
<item>  
  <guid isPermaLink="false">ItemID</guid>  
  <link>http://myitemuri/</link>  
  <author xmlns="http://www.w3.org/2005/Atom">  
    <name>Jesper Aaberg</name>  
    <uri>http://Jesper/Aaberg</uri>  
    <email>Jesper@Aaberg.com</email>  
  </author>  
  <author xmlns="http://www.w3.org/2005/Atom">  
    <name>Syed Abbas</name>  
    <uri>http://Contoso/Abbas</uri>  
    <email>Syed.Abbas@contoso.com</email>  
  </author>  
  <category domain="categoryScheme">categoryName</category>  
  <category domain="categoryScheme">categoryName</category>  
  <title>Item Title</title>  
  <description>Item Summary</description>  
  <source>My Feed Title</source>  
  <pubDate>Wed, 29 Aug 2007 00:00:00 -0700</pubDate>  
  <updated xmlns="http://www.w3.org/2005/Atom">2007-08-29T14:07:09-07:00</updated>  
  <rights type="text" xmlns="http://www.w3.org/2005/Atom">Copyright 2007</rights>  
  <content type="text" xmlns="http://www.w3.org/2005/Atom">Item Content</content>  
  <contributor xmlns="http://www.w3.org/2005/Atom">  
    <name>Lene Aaling</name>  
    <uri>http://Contoso/Aaling</uri>  
    <email>Lene.Aaling@contoso.com</email>  
  </contributor>  
  <contributor xmlns="http://www.w3.org/2005/Atom">  
    <name>Kim Abercrombie</name>  
    <uri>http://Contoso/Abercrombie</uri>  
    <email>Kim.Abercrombie@contoso.com</email>  
  </contributor>  
</item>  
```  
  
## <a name="syndicationperson"></a>SyndicationPerson  
 Das folgende Codebeispiel zeigt, wie die <xref:System.ServiceModel.Syndication.SyndicationPerson>-Klasse in Atom&#160;1.0 und RSS&#160;2.0 serialisiert wird.  
  
 [!code-csharp[SyndicationMapping#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#2)]
 [!code-vb[SyndicationMapping#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#2)]  
  
 Im folgenden XML wird gezeigt, wie die <xref:System.ServiceModel.Syndication.SyndicationPerson> in Atom&#160;1.0 serialisiert wird.  
  
```xml  
  <author>  
    <name>Jesper Aaberg</name>  
    <uri>http://Contoso/Aaberg</uri>  
    <email>Jesper.Aaberg@contoso.com</email>  
  </author>  
<contributor>  
    <name>Lene Aaling</name>  
    <uri>http://Contoso/Aaling</uri>  
    <email>Lene.Aaling@contoso.com</email>  
  </contributor>  
```  
  
 Das folgende XML zeigt, wie die <xref:System.ServiceModel.Syndication.SyndicationPerson>-Klasse in RSS&#160;2.0 serialisiert wird, wenn nur eine <xref:System.ServiceModel.Syndication.SyndicationPerson> in der `Authors`-Auflistung bzw. der `Contributors`-Auflistung vorhanden ist.  
  
```xml  
<author>Jesper.Aaberg@contoso.com</author>  
<a10:contributor>  
    <a10:name>Lene Aaling</a10:name>  
    <a10:uri>http://Contoso/Aaling</a10:uri>  
    <a10:email>Lene.Aaling@contoso.com</a10:email>  
</a10:contributor>  
```  
  
 Das folgende XML zeigt, wie die <xref:System.ServiceModel.Syndication.SyndicationPerson>-Klasse in RSS&#160;2.0 serialisiert wird, wenn mehr als eine <xref:System.ServiceModel.Syndication.SyndicationPerson> in der `Authors`-Auflistung bzw. der `Contributors`-Auflistung vorhanden ist.  
  
```xml  
<a10:author>  
    <a10:name>Jesper Aaberg</a10:name>  
    <a10:uri>http://Contoso/Aaberg</a10:uri>  
    <a10:email>Jesper.Aaberg@contoso.com</a10:email>  
</a10:author>  
<a10:author>  
    <a10:name>Syed Abbas</a10:name>  
    <a10:uri>http://Contoso/Abbas</a10:uri>  
    <a10:email>Syed.Abbas@contoso.com</a10:email>  
</a10:author>  
<a10:contributor>  
    <a10:name>Lene Aaling</a10:name>  
    <a10:uri>http://Contoso/Aaling</a10:uri>  
    <a10:email>Lene.Aaling@contoso.com</a10:email>  
</a10:contributor>  
<a10:contributor>  
    <a10:name>Kim Abercrombie</a10:name>  
    <a10:uri>http://Contoso/Abercrombie</a10:uri>  
    <a10:email>Kim.Abercrombie@contoso.com</a10:email>  
</a10:contributor>  
```  
  
## <a name="syndicationlink"></a>SyndicationLink  
 Das folgende Codebeispiel zeigt, wie die <xref:System.ServiceModel.Syndication.SyndicationLink>-Klasse in Atom&#160;1.0 und RSS&#160;2.0 serialisiert wird.  
  
 [!code-csharp[SyndicationMapping#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#3)]
 [!code-vb[SyndicationMapping#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#3)]  
  
 Im folgenden XML wird gezeigt, wie die <xref:System.ServiceModel.Syndication.SyndicationLink> in Atom&#160;1.0 serialisiert wird.  
  
 `<link rel="alternate" type="text/html" title="My Link Title" length="2048" href="http://contoso/MyLink" />`  
  
 Im folgenden XML wird gezeigt, wie die <xref:System.ServiceModel.Syndication.SyndicationLink> in RSS&#160;2.0 serialisiert wird.  
  
 `<a10:link rel="alternate" type="text/html" title="My Link Title" length="2048" href="http://contoso/MyLink" />`  
  
## <a name="syndicationcategory"></a>SyndicationCategory  
 Das folgende Codebeispiel zeigt, wie die <xref:System.ServiceModel.Syndication.SyndicationCategory>-Klasse in Atom&#160;1.0 und RSS&#160;2.0 serialisiert wird.  
  
 [!code-csharp[SyndicationMapping#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#4)]
 [!code-vb[SyndicationMapping#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#4)]  
  
 Im folgenden XML wird gezeigt, wie die <xref:System.ServiceModel.Syndication.SyndicationCategory> in Atom&#160;1.0 serialisiert wird.  
  
 `<category term="categoryName" label="categoryLabel" scheme="categoryScheme" />`  
  
 Im folgenden XML wird gezeigt, wie die <xref:System.ServiceModel.Syndication.SyndicationCategory> in RSS&#160;2.0 serialisiert wird.  
  
 `<category domain="categoryScheme">categoryName</category>`  
  
## <a name="textsyndicationcontent"></a>TextSyndicationContent  
 Im folgenden Codebeispiel wird gezeigt, wie die <xref:System.ServiceModel.Syndication.TextSyndicationContent>-Klasse in Atom&#160;1.0 und RSS&#160;2.0 serialisiert wird, wenn <xref:System.ServiceModel.Syndication.TextSyndicationContent> mit HTML-Inhalt erstellt wird.  
  
 [!code-csharp[SyndicationMapping#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#5)]
 [!code-vb[SyndicationMapping#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#5)]  
  
 Das folgende XML zeigt, wie die <xref:System.ServiceModel.Syndication.TextSyndicationContent>-Klasse mit HTML-Inhalt in Atom&#160;1.0 serialisiert wird.  
  
 `<content type="html"><html> some html </html></content>`  
  
 Das folgende XML zeigt, wie die <xref:System.ServiceModel.Syndication.TextSyndicationContent>-Klasse mit HTML-Inhalt in RSS&#160;2.0 serialisiert wird.  
  
 `<description><html> some html </html></description>`  
  
 Im folgenden Codebeispiel wird gezeigt, wie die <xref:System.ServiceModel.Syndication.TextSyndicationContent>-Klasse in Atom&#160;1.0 und RSS&#160;2.0 serialisiert wird, wenn <xref:System.ServiceModel.Syndication.TextSyndicationContent> mit Nur-Text-Inhalt erstellt wird.  
  
 [!code-csharp[SyndicationMapping#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#6)]
 [!code-vb[SyndicationMapping#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#6)]  
  
 Das folgende XML zeigt, wie die <xref:System.ServiceModel.Syndication.TextSyndicationContent>-Klasse mit Nur-Text-Inhalt in Atom&#160;1.0 serialisiert wird.  
  
 `<content type="text">Some Plain Text</content>`  
  
 Das folgende XML zeigt, wie die <xref:System.ServiceModel.Syndication.TextSyndicationContent>-Klasse mit Nur-Text-Inhalt in RSS&#160;2.0 serialisiert wird.  
  
 `<description>Some Plain Text</description>`  
  
 Im folgenden Codebeispiel wird gezeigt, wie die <xref:System.ServiceModel.Syndication.TextSyndicationContent>-Klasse in Atom&#160;1.0 und RSS&#160;2.0 serialisiert wird, wenn <xref:System.ServiceModel.Syndication.TextSyndicationContent> mit XHTML-Inhalt erstellt wird.  
  
 [!code-csharp[SyndicationMapping#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#7)]
 [!code-vb[SyndicationMapping#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#7)]  
  
 Das folgende XML zeigt, wie die <xref:System.ServiceModel.Syndication.TextSyndicationContent>-Klasse mit XHTML-Inhalt in Atom&#160;1.0 serialisiert wird.  
  
 `<content type="xhtml">`  
  
 `<html> some xhtml </html>`  
  
 `</content>`  
  
 Das folgende XML zeigt, wie die <xref:System.ServiceModel.Syndication.TextSyndicationContent>-Klasse mit XHTML-Inhalt in RSS&#160;2.0 serialisiert wird.  
  
 `<description><html> some xhtml </html></description>`  
  
## <a name="urlsyndicationcontent"></a>UrlSyndicationContent  
 Das folgende Codebeispiel zeigt, wie die <xref:System.ServiceModel.Syndication.UrlSyndicationContent>-Klasse in Atom&#160;1.0 und RSS&#160;2.0 serialisiert wird.  
  
 [!code-csharp[SyndicationMapping#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#8)]
 [!code-vb[SyndicationMapping#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#8)]  
  
 Das folgende XML zeigt, wie die <xref:System.ServiceModel.Syndication.UrlSyndicationContent>-Klasse in Atom&#160;1.0 serialisiert wird.  
  
 `<content type="audio" src="http://someurl/" />`  
  
 Das folgende XML zeigt, wie die <xref:System.ServiceModel.Syndication.UrlSyndicationContent>-Klasse mit XHTML-Inhalt in RSS&#160;2.0 serialisiert wird.  
  
 `<description />`  
  
 `<content type="audio" src="http://Contoso/someurl/" xmlns="http://www.w3.org/2005/Atom" />`  
  
## <a name="xmlsyndicationcontent"></a>XmlSyndicationContent  
 Das folgende Codebeispiel zeigt, wie die <xref:System.ServiceModel.Syndication.XmlSyndicationContent>-Klasse in Atom&#160;1.0 und RSS&#160;2.0 serialisiert wird.  
  
 [!code-csharp[SyndicationMapping#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#9)]
 [!code-vb[SyndicationMapping#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#9)]  
  
 Das folgende XML zeigt, wie die <xref:System.ServiceModel.Syndication.XmlSyndicationContent>-Klasse in Atom&#160;1.0 serialisiert wird.  
  
 `<content type="mytype">`  
  
 `<SomeData xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.datacontract.org/2004/07/FeedMapping" />`  
  
 `</content>`  
  
 Das folgende XML zeigt, wie die <xref:System.ServiceModel.Syndication.XmlSyndicationContent>-Klasse mit XHTML-Inhalt in RSS&#160;2.0 serialisiert wird.  
  
 `<content type="mytype" xmlns="http://www.w3.org/2005/Atom">`  
  
 `<SomeData xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.datacontract.org/2004/07/FeedMapping" />`  
  
 `</content>`  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über WCF Syndication](wcf-syndication-overview.md)
- [Architektur von Syndication](architecture-of-syndication.md)
- [Vorgehensweise: Erstellen eines grundlegenden RSS-Feeds](how-to-create-a-basic-rss-feed.md)
- [Vorgehensweise: Erstellen eines grundlegenden Atom-Feeds](how-to-create-a-basic-atom-feed.md)
- [Vorgehensweise: Verfügbarmachen eines Feeds als Atom und RSS](how-to-expose-a-feed-as-both-atom-and-rss.md)
