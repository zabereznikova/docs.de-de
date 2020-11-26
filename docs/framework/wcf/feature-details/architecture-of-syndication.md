---
title: Architektur von Syndication
ms.date: 03/30/2017
ms.assetid: ed4ca86e-e3d8-4acb-87aa-1921fbc353be
ms.openlocfilehash: bc8c9cfbdc4f5d8ee01dfcf5098cfbc74afc2467
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234803"
---
# <a name="architecture-of-syndication"></a>Architektur von Syndication

Die Syndication-API ist darauf ausgelegt, ein Format-neutrales Programmiermodell zu bieten, mit dem es möglich ist, Schlagzeilen in verschiedenen Formaten zu schreiben und direkt zu übertragen. Das abstrakte Datenmodell besteht aus den folgenden Klassen:  
  
- <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
- <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
- <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
- <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
- <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
 Diese Klassen sind nahezu deckungsgleich mit den in der Atom&#160;1.0-Spezifikation definierten Konstrukten, obwohl manche der Namen anders lauten.  
  
 In Windows Communication Foundation (WCF) werden Syndizierungs Feeds als ein anderer Typ von Dienst Vorgang modelliert, wobei der Rückgabetyp eine der abgeleiteten Klassen von ist <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> . Der Abruf eines Feeds wird als Anforderung-Antwort-Nachrichtenaustausch erstellt. Ein Client sendet eine Anforderung an den Dienst, und der Dienst antwortet. Die Anforderungsnachricht wird über ein Infrastrukturprotokoll festgelegt (z.&#160;B. unformatiertes HTTP), und die Antwortnachricht enthält eine Nutzlast in Form eines üblichen Syndication-Formats (RSS&#160;2.0 oder Atom&#160;1.0). Dienste, die diesen Nachrichtenaustausch implementieren, werden als Syndication-Dienste bezeichnet.  
  
 Der Vertrag für einen Syndication-Dienst besteht aus einer Gruppe von Vorgängen, die eine Instanz der <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>-Klasse zurückgibt. Im folgenden Beispiel wird eine Schnittstellendeklaration für einen Syndication-Dienst veranschaulicht.  
  
 [!code-csharp[S_UE_SyndicationBoth#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ue_syndicationboth/cs/service.cs#0)]  
  
 Die Syndizierungs Unterstützung baut auf dem WCF REST-Programmiermodell auf, das die <xref:System.ServiceModel.WebHttpBinding> Bindung definiert, die in Verbindung mit verwendet wird, <xref:System.ServiceModel.Description.WebHttpBehavior> um Feeds als Dienste verfügbar zu machen. Weitere Informationen zum WCF-REST-Programmiermodell finden Sie unter Übersicht über das [WCF-Web-HTTP-Programmiermodell](wcf-web-http-programming-model-overview.md).  
  
> [!NOTE]
> Die Atom&#160;1.0-Spezifikation lässt zu, dass Sekundenbruchteile in beliebigen Datenkonstrukten angegeben werden. Beim Serialisieren und Deserialisieren ignoriert die WCF-Implementierung die Sekundenbruchteile.  
  
## <a name="object-model"></a>Objektmodell  

 Das Objektmodell für Syndication besteht aus den in den folgenden Tabellen dargestellten Klassengruppen.  
  
 Formatierungsklassen:  
  
|Klasse|BESCHREIBUNG|  
|-----------|-----------------|  
|<xref:System.ServiceModel.Syndication.Atom10FeedFormatter>|Eine Klasse, die eine <xref:System.ServiceModel.Syndication.SyndicationFeed>-Instanz ins Atom&#160;1.0-Format serialisiert.|  
|<xref:System.ServiceModel.Syndication.Atom10FeedFormatter%601>|Eine Klasse, die abgeleitete Klassen von <xref:System.ServiceModel.Syndication.SyndicationFeed> ins Atom&#160;1.0-Format serialisiert.|  
|<xref:System.ServiceModel.Syndication.Atom10ItemFormatter>|Eine Klasse, die eine <xref:System.ServiceModel.Syndication.SyndicationItem>-Instanz ins Atom&#160;1.0-Format serialisiert.|  
|<xref:System.ServiceModel.Syndication.Atom10ItemFormatter%601>|Eine Klasse, die abgeleitete Klassen von <xref:System.ServiceModel.Syndication.SyndicationItem> ins Atom&#160;1.0-Format serialisiert.|  
|<xref:System.ServiceModel.Syndication.Rss20FeedFormatter>|Eine Klasse, die eine <xref:System.ServiceModel.Syndication.SyndicationFeed>-Instanz ins RSS&#160;2.0-Format serialisiert.|  
|<xref:System.ServiceModel.Syndication.Rss20FeedFormatter%601>|Eine Klasse, die abgeleitete Klassen von <xref:System.ServiceModel.Syndication.SyndicationFeed> ins RSS&#160;2.0-Format serialisiert.|  
|<xref:System.ServiceModel.Syndication.Rss20ItemFormatter>|Eine Klasse, die eine <xref:System.ServiceModel.Syndication.SyndicationItem>-Instanz ins RSS&#160;2.0-Format serialisiert.|  
|<xref:System.ServiceModel.Syndication.Rss20ItemFormatter%601>|Eine Klasse, die abgeleitete Klassen von <xref:System.ServiceModel.Syndication.SyndicationItem> ins RSS&#160;2.0-Format serialisiert.|  
  
 Objektmodellklassen:  
  
|Klasse|BESCHREIBUNG|  
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
  
 Die Kerndatenabstraktionen im Objektmodell sind Feed und Element, was den Klassen <xref:System.ServiceModel.Syndication.SyndicationFeed> und <xref:System.ServiceModel.Syndication.SyndicationItem> entspricht. Ein Feed stellt eine Reihe von Metadaten auf Feedebene (z.&#160;B. Titel, Beschreibung und Autor), einen Speicherort für unbekannte Erweiterungen und eine Gruppe von Elementen, die aus dem restlichen Inhalt des Feeds bestehen, zur Verfügung. Ein Element macht eine Reihe von Metadaten auf Elementebene (z.&#160;B. Titel, Zusammenfassung und Veröffentlichungsdatum), einen Speicherort für unbekannte Erweiterungen und ein Inhaltselement, das aus dem restlichen Inhalt des Elements besteht, verfügbar. Die Kernabstraktionen von Feed und Element werden von zusätzlichen Klassen unterstützt, die übliche, in den Spezifikationen zu Atom&#160;1.0 und RSS referenzierte Datenkonstrukte darstellen.  
  
 Die in einer Feed-Instanz enthaltenen Informationen können in eine Reihe von XML-Formaten konvertiert werden. Die Konvertierungsprozesse in und aus XML werden von der <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>-Klasse verwaltet. Diese Klasse ist abstrakt. Für Atom&#160;1.0 und RSS&#160;2.0 sowie <xref:System.ServiceModel.Syndication.Atom10FeedFormatter> und <xref:System.ServiceModel.Syndication.Rss20FeedFormatter> werden konkrete Implementierungen bereitgestellt. Um abgeleitete Feedklassen einzusetzen, verwenden Sie entweder <xref:System.ServiceModel.Syndication.Atom10FeedFormatter%601> oder <xref:System.ServiceModel.Syndication.Rss20FeedFormatter%601>, da Sie damit eine abgeleitete Feedklasse angeben können. Um abgeleitete Elementklassen einzusetzen, verwenden Sie entweder <xref:System.ServiceModel.Syndication.Atom10ItemFormatter%601> oder <xref:System.ServiceModel.Syndication.Rss20ItemFormatter%601>, da Sie damit eine abgeleitete Feedklasse angeben können. Verwender von Drittanbietern können ihre eigene Implementierung von <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> ableiten, um andere Syndication-Formate zu unterstützen.  
  
## <a name="extensibility"></a>Erweiterbarkeit  
  
- Eine Hauptfunktion von Syndication-Protokollen ist die Erweiterbarkeit. Sowohl Atom&#160;1.0 als auch RSS&#160;2.0 lassen zu, dass Sie Syndication-Feeds Attribute und Elemente hinzufügen, die nicht in den Spezifikationen definiert sind. Das WCF-Syndizierungs-Programmiermodell bietet zwei Möglichkeiten, mit benutzerdefinierten Attributen und Erweiterungen zu arbeiten: das Ableiten einer neuen Klasse und lose typisierte Zugriffe. Weitere Informationen finden Sie unter [Syndikation Extensibility](syndication-extensibility.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über WCF Syndication](wcf-syndication-overview.md)
- [Wie das WCF-Syndication-Objektmodell Atom und RSS zugeordnet wird](how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md)
- [WCF-Web-HTTP-Programmiermodell](wcf-web-http-programming-model.md)
