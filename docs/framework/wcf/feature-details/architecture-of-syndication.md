---
title: Architektur von Syndication
ms.date: 03/30/2017
ms.assetid: ed4ca86e-e3d8-4acb-87aa-1921fbc353be
ms.openlocfilehash: 4083f7f7ef3fc986e9a7c430b8ed8cfe451c9d86
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075911"
---
# <a name="architecture-of-syndication"></a>Architektur von Syndication
Die Syndication-API ist darauf ausgelegt, ein Format-neutrales Programmiermodell zu bieten, mit dem es möglich ist, Schlagzeilen in verschiedenen Formaten zu schreiben und direkt zu übertragen. Das abstrakte Datenmodell besteht aus den folgenden Klassen:  
  
-   <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
 Diese Klassen sind nahezu deckungsgleich mit den in der Atom&amp;#160;1.0-Spezifikation definierten Konstrukten, obwohl manche der Namen anders lauten.  
  
 In Windows Communication Foundation (WCF) beruhen Syndication-Feeds als anderer Typ von einer, in dem der Rückgabetyp einer der abgeleiteten Klassen der ist, Dienstvorgang <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>. Der Abruf eines Feeds wird als Anforderung-Antwort-Nachrichtenaustausch erstellt. Ein Client sendet eine Anforderung an den Dienst, und der Dienst antwortet. Die Anforderungsnachricht wird über ein Infrastrukturprotokoll festgelegt (z.&amp;#160;B. unformatiertes HTTP), und die Antwortnachricht enthält eine Nutzlast in Form eines üblichen Syndication-Formats (RSS&amp;#160;2.0 oder Atom&amp;#160;1.0). Dienste, die diesen Nachrichtenaustausch implementieren, werden als Syndication-Dienste bezeichnet.  
  
 Der Vertrag für einen Syndication-Dienst besteht aus einer Gruppe von Vorgängen, die eine Instanz der <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>-Klasse zurückgibt. Im folgenden Beispiel wird eine Schnittstellendeklaration für einen Syndication-Dienst veranschaulicht.  
  
 [!code-csharp[S_UE_SyndicationBoth#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ue_syndicationboth/cs/service.cs#0)]  
  
 Syndication-Unterstützung basiert auf der WCF REST-Programmiermodell, das definiert die <xref:System.ServiceModel.WebHttpBinding> Bindung, die in Verbindung mit verwendet wird <xref:System.ServiceModel.Description.WebHttpBehavior> , Feeds als Dienste verfügbar zu machen. Weitere Informationen zu den WCF REST-Programmiermodell, finden Sie unter [Web-HTTP-Programmierung Überblick über WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md).  
  
> [!NOTE]
>  Die Atom&amp;#160;1.0-Spezifikation lässt zu, dass Sekundenbruchteile in beliebigen Datenkonstrukten angegeben werden. Beim Serialisieren und Deserialisieren ignoriert die WCF-Implementierung in Bruchteilen von Sekunden an.  
  
## <a name="object-model"></a>Objektmodell  
 Das Objektmodell für Syndication besteht aus den in den folgenden Tabellen dargestellten Klassengruppen.  
  
 Formatierungsklassen:  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|<xref:System.ServiceModel.Syndication.Atom10FeedFormatter>|Eine Klasse, die eine <xref:System.ServiceModel.Syndication.SyndicationFeed>-Instanz ins Atom&amp;#160;1.0-Format serialisiert.|  
|<xref:System.ServiceModel.Syndication.Atom10FeedFormatter%601>|Eine Klasse, die abgeleitete Klassen von <xref:System.ServiceModel.Syndication.SyndicationFeed> ins Atom&amp;#160;1.0-Format serialisiert.|  
|<xref:System.ServiceModel.Syndication.Atom10ItemFormatter>|Eine Klasse, die eine <xref:System.ServiceModel.Syndication.SyndicationItem>-Instanz ins Atom&amp;#160;1.0-Format serialisiert.|  
|<xref:System.ServiceModel.Syndication.Atom10ItemFormatter%601>|Eine Klasse, die abgeleitete Klassen von <xref:System.ServiceModel.Syndication.SyndicationItem> ins Atom&amp;#160;1.0-Format serialisiert.|  
|<xref:System.ServiceModel.Syndication.Rss20FeedFormatter>|Eine Klasse, die eine <xref:System.ServiceModel.Syndication.SyndicationFeed>-Instanz ins RSS&amp;#160;2.0-Format serialisiert.|  
|<xref:System.ServiceModel.Syndication.Rss20FeedFormatter%601>|Eine Klasse, die abgeleitete Klassen von <xref:System.ServiceModel.Syndication.SyndicationFeed> ins RSS&amp;#160;2.0-Format serialisiert.|  
|<xref:System.ServiceModel.Syndication.Rss20ItemFormatter>|Eine Klasse, die eine <xref:System.ServiceModel.Syndication.SyndicationItem>-Instanz ins RSS&amp;#160;2.0-Format serialisiert.|  
|<xref:System.ServiceModel.Syndication.Rss20ItemFormatter%601>|Eine Klasse, die abgeleitete Klassen von <xref:System.ServiceModel.Syndication.SyndicationItem> ins RSS&amp;#160;2.0-Format serialisiert.|  
  
 Objektmodellklassen:  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|<xref:System.ServiceModel.Syndication.SyndicationCategory>|Eine Klasse, die die Kategorie eines Syndication-Feeds darstellt.|  
|<xref:System.ServiceModel.Syndication.SyndicationContent>|Eine Basisklasse, die Syndication-Inhalte darstellt.|  
|<xref:System.ServiceModel.Syndication.SyndicationElementExtension>|Eine Klasse, die eine Syndication-Elementerweiterung darstellt.|  
|<xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection>|Eine Auflistung von <xref:System.ServiceModel.Syndication.SyndicationElementExtension>-Objekten.|  
|<xref:System.ServiceModel.Syndication.SyndicationFeed>|Eine Klasse, die ein Feedobjekt der obersten Ebene darstellt.|  
|<xref:System.ServiceModel.Syndication.SyndicationItem>|Eine Klasse, die ein Feedelement darstellt.|  
|<xref:System.ServiceModel.Syndication.SyndicationLink>|Eine Klasse, die eine Verknüpfung innerhalb eines Syndication-Feeds oder -Elements darstellt.|  
|<xref:System.ServiceModel.Syndication.SyndicationPerson>|Eine Klasse, die ein Atom-Personenkonstrukt darstellt.|  
|<xref:System.ServiceModel.Syndication.SyndicationVersions>|Eine Klasse, die die unterstützten Syndication-Protokollversionen darstellt.|  
|<xref:System.ServiceModel.Syndication.TextSyndicationContent>|Eine Klasse, die jeden dem Endbenutzer anzuzeigenden <xref:System.ServiceModel.Syndication.SyndicationItem>-Inhalt darstellt.|  
|<xref:System.ServiceModel.Syndication.TextSyndicationContentKind>|Eine Enumeration, die die verschiedenen unterstützten Typen von Text-Syndication-Inhalten darstellt.|  
|<xref:System.ServiceModel.Syndication.UrlSyndicationContent>|Eine Klasse, die Syndication-Inhalte darstellt, die aus der URL zu einer anderen Ressource bestehen.|  
|<xref:System.ServiceModel.Syndication.XmlSyndicationContent>|Eine Klasse, die Syndication-Inhalte darstellt, die nicht in einem Browser angezeigt werden sollen.|  
  
 Die Kerndatenabstraktionen im Objektmodell sind Feed und Element, was den Klassen <xref:System.ServiceModel.Syndication.SyndicationFeed> und <xref:System.ServiceModel.Syndication.SyndicationItem> entspricht. Ein Feed stellt eine Reihe von Metadaten auf Feedebene (z.&amp;#160;B. Titel, Beschreibung und Autor), einen Speicherort für unbekannte Erweiterungen und eine Gruppe von Elementen, die aus dem restlichen Inhalt des Feeds bestehen, zur Verfügung. Ein Element macht eine Reihe von Metadaten auf Elementebene (z.&amp;#160;B. Titel, Zusammenfassung und Veröffentlichungsdatum), einen Speicherort für unbekannte Erweiterungen und ein Inhaltselement, das aus dem restlichen Inhalt des Elements besteht, verfügbar. Die Kernabstraktionen von Feed und Element werden von zusätzlichen Klassen unterstützt, die übliche, in den Spezifikationen zu Atom&amp;#160;1.0 und RSS referenzierte Datenkonstrukte darstellen.  
  
 Die in einer Feed-Instanz enthaltenen Informationen können in eine Reihe von XML-Formaten konvertiert werden. Die Konvertierungsprozesse in und aus XML werden von der <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>-Klasse verwaltet. Diese Klasse ist abstrakt. Für Atom&amp;#160;1.0 und RSS&amp;#160;2.0 sowie <xref:System.ServiceModel.Syndication.Atom10FeedFormatter> und <xref:System.ServiceModel.Syndication.Rss20FeedFormatter> werden konkrete Implementierungen bereitgestellt. Um abgeleitete Feedklassen einzusetzen, verwenden Sie entweder <xref:System.ServiceModel.Syndication.Atom10FeedFormatter%601> oder <xref:System.ServiceModel.Syndication.Rss20FeedFormatter%601>, da Sie damit eine abgeleitete Feedklasse angeben können. Um abgeleitete Elementklassen einzusetzen, verwenden Sie entweder <xref:System.ServiceModel.Syndication.Atom10ItemFormatter%601> oder <xref:System.ServiceModel.Syndication.Rss20ItemFormatter%601>, da Sie damit eine abgeleitete Feedklasse angeben können. Verwender von Drittanbietern können ihre eigene Implementierung von <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> ableiten, um andere Syndication-Formate zu unterstützen.  
  
## <a name="extensibility"></a>Erweiterungen  
  
-   Eine Hauptfunktion von Syndication-Protokollen ist die Erweiterbarkeit. Sowohl Atom&amp;#160;1.0 als auch RSS&amp;#160;2.0 lassen zu, dass Sie Syndication-Feeds Attribute und Elemente hinzufügen, die nicht in den Spezifikationen definiert sind. Der WCF-Syndication-Programmiermodell bietet zwei Möglichkeiten zum Arbeiten mit benutzerdefinierten Attributen und Erweiterungen: ableiten, eine neue Klasse und typenlosen Zugriff. Weitere Informationen finden Sie unter [Syndication-Erweiterbarkeit](../../../../docs/framework/wcf/feature-details/syndication-extensibility.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über WCF Syndication](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md)
- [Zuordnung des WCF-Syndication-Objektmodells zu Atom und RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md)
- [WCF-Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
