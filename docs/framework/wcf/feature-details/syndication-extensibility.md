---
title: Syndication-Erweiterbarkeit
ms.date: 03/30/2017
ms.assetid: 4d941175-74a2-4b15-81b3-086e8a95d25f
ms.openlocfilehash: 5e8f47b45897f46e15847c793c986e953523e66b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600723"
---
# <a name="syndication-extensibility"></a>Syndication-Erweiterbarkeit
Die Syndication-API ist darauf ausgelegt, ein formatunabhängiges Programmiermodell bereitzustellen, mit dem Fremdinhalte in verschiedenen Formaten ausgegeben und direkt übertragen werden können. Das abstrakte Datenmodell besteht aus den folgenden Klassen:  
  
- <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
- <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
- <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
- <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
- <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
 Diese Klassen sind nahezu deckungsgleich mit den in der Atom&#160;1.0-Spezifikation definierten Konstrukten, obwohl manche der Namen anders lauten.  
  
 Eine Hauptfunktion von Syndication-Protokollen ist die Erweiterbarkeit. Sowohl Atom&#160;1.0 als auch RSS&#160;2.0 lassen zu, dass Sie Syndication-Feeds Attribute und Elemente hinzufügen, die nicht in den Spezifikationen definiert sind. Das Programmiermodell für die Windows Communication Foundation (WCF)-Syndizierung bietet die folgenden Möglichkeiten, mit benutzerdefinierten Attributen und Erweiterungen zu arbeiten: lose typisierte Zugriffe und Ableiten einer neuen Klasse.  
  
## <a name="loosely-typed-access"></a>Zugriff mit flexibler Typbindung  
 Wenn Erweiterungen durch das Ableiten einer neuen Klasse hinzugefügt werden sollen, muss zusätzlicher Code geschrieben werden. Eine andere Möglichkeit besteht darin, mit flexibler Typbindung auf Erweiterungen zuzugreifen. Alle im abstrakten Datenmodell für Syndication definierten Typen enthalten Eigenschaften namens `AttributeExtensions` und `ElementExtensions` (mit einer Ausnahme, <xref:System.ServiceModel.Syndication.SyndicationContent> verfügt über die `AttributeExtensions`-Eigenschaft, nicht aber über die `ElementExtensions`-Eigenschaft). Diese Eigenschaften sind Auflistungen von Erweiterungen, die nicht von der `TryParseAttribute`-Methode bzw. der `TryParseElement`-Methode verarbeitet werden. Sie können auf diese unverarbeiteten Erweiterungen zugreifen, indem Sie <xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection.ReadElementExtensions%2A?displayProperty=nameWithType> für die `ElementExtensions`-Eigenschaft von <xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem>, <xref:System.ServiceModel.Syndication.SyndicationLink>, <xref:System.ServiceModel.Syndication.SyndicationPerson> und <xref:System.ServiceModel.Syndication.SyndicationCategory> aufrufen. Dieser Satz von Methoden findet alle Erweiterungen mit dem angegebenen Namen und Namespace, deserialisiert sie einzeln in Instanzen von `TExtension` und gibt sie als Auflistung von `TExtension`-Objekten zurück.  
  
## <a name="deriving-a-new-class"></a>Ableiten einer neuen Klasse  
 Sie können eine neue Klasse von jeder im abstrakten Datenmodell vorhandenen Klasse ableiten. Tun Sie dies beim Implementieren einer Anwendung, in der Sie für die meisten Feeds eine bestimmte Erweiterung verwenden. In diesem Thema enthalten die meisten der Feeds, mit denen das Programm arbeitet, eine `MyExtension`-Erweiterung. Um Ihre Programmiererfahrung zu vertiefen, führen Sie die folgenden Schritte aus:  
  
- Erstellen Sie eine Klasse zum Speichern der Erweiterungsdaten. Erstellen Sie in diesem Fall eine Klasse mit dem Namen MyExtension.  
  
- Leiten Sie eine Klasse mit dem Namen MyExtensionItem von <xref:System.ServiceModel.Syndication.SyndicationItem> ab, um zu Programmierzwecken eine Eigenschaft des Typs MyExtension verfügbar zu machen.  
  
- Überschreiben Sie <xref:System.ServiceModel.Syndication.SyndicationItem.TryParseElement%28System.Xml.XmlReader%2CSystem.String%29> in der MyExtensionItem-Klasse, um eine neue MyExtension-Instanz zu instanziieren, wenn MyExtension eingelesen wird.  
  
- Überschreiben Sie <xref:System.ServiceModel.Syndication.SyndicationItem.WriteElementExtensions%28System.Xml.XmlWriter%2CSystem.String%29> in der MyExtensionItem-Klasse, um den Inhalt der MyExtension-Eigenschaft an einen XML-Writer auszugeben.  
  
- Leiten Sie eine Klasse mit dem Namen MyExtensionFeed von <xref:System.ServiceModel.Syndication.SyndicationFeed> ab.  
  
- Überschreiben Sie <xref:System.ServiceModel.Syndication.SyndicationFeed.CreateItem> in der MyExtensionFeed-Klasse, um ein MyExtensionItem-Objekt statt des Standardobjekts vom Typ <xref:System.ServiceModel.Syndication.SyndicationItem> zu instanziieren. In <xref:System.ServiceModel.Syndication.SyndicationFeed> und <xref:System.ServiceModel.Syndication.SyndicationItem> sind einige Methoden definiert, mit denen sich Objekte des Typs <xref:System.ServiceModel.Syndication.SyndicationLink>, <xref:System.ServiceModel.Syndication.SyndicationCategory> und <xref:System.ServiceModel.Syndication.SyndicationPerson> erstellen lassen (beispielsweise <xref:System.ServiceModel.Syndication.SyndicationFeed.CreateLink>, <xref:System.ServiceModel.Syndication.SyndicationFeed.CreateCategory> und <xref:System.ServiceModel.Syndication.SyndicationFeed.CreatePerson>). Alle diese Methoden können zur Erstellung einer benutzerdefinierten abgeleiteten Klasse überschrieben werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über WCF Syndication](wcf-syndication-overview.md)
- [Architektur von Syndication](architecture-of-syndication.md)
