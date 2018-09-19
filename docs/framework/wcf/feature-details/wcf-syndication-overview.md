---
title: Übersicht über WCF Syndication
ms.date: 03/30/2017
ms.assetid: af6d4c39-e5e8-4099-aee6-5261feff9107
ms.openlocfilehash: 60a919a03552f5195529ae0997e60d1fba55d7c3
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46322907"
---
# <a name="wcf-syndication-overview"></a>Übersicht über WCF Syndication
Windows Communication Foundation (WCF) bietet Unterstützung für das Verfügbarmachen von Syndication-Feeds von einem WCF-Dienst. Syndication ist ein Mechanismus der Anwendungsintegration, bei dem ein Server Anwendungsdaten in einem interoperablen, als Feed bezeichnetem Format verfügbar macht. Ein Feed ist eine Auflistung von Anwendungsdaten, die aus einigen feedeigenen Metadaten (Titel, Autor, URL und andere Metadaten) und einer Reihe von Feedelementen besteht. Innerhalb des Feeds sind die Feedelemente normalerweise in umgekehrter chronologischer Reihenfolge geordnet. Ein Feedelement besteht aus einem Standardsatz elementeigener Metadaten (Titel, URL, Erstellungsdatum, Kategorie und andere elementeigenen Metadaten) und einer beliebigen Anzahl anwendungsspezifischer Daten. Die beiden häufigsten Typen von Syndication-Feeds sind RSS Really Simple Syndication () 2.0 und Atom 1.0, die beide von WCF unterstützt werden.  
  
## <a name="object-model"></a>Objektmodell  
 WCF definiert einen Satz von Syndication-spezifischer Klassen, die Ihnen ermöglichen, mit Feeds, Feedelementen und den zugehörigen Metadaten in einem formatunabhängig zu arbeiten: <xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem>, <xref:System.ServiceModel.Syndication.SyndicationPerson>, <xref:System.ServiceModel.Syndication.SyndicationLink>, sowie weitere Syndication-spezifische Klassen. WCF definiert auch Infrastrukturklassen, die auf das WCF REST-Programmiermodell, einschließlich der Syndication-Unterstützung bieten aufbauen: <xref:System.ServiceModel.Syndication.Atom10FeedFormatter>, und <xref:System.ServiceModel.Syndication.Rss20FeedFormatter>. Die Feedformatierungsklassen unterstützen das Serialisieren des Objektmodells in und aus RSS&#160;2.0 und Atom&#160;1.0.  
  
## <a name="scenarios"></a>Szenarien  
 Eine heute häufige Verwendung der Syndication stellt das Bloggen dar, bei dem der Autor eines Blogs periodisch bestimmte Informationen veröffentlicht. Dies können Texte, Bilder, Audioelemente oder andere Informationstypen sein. Viele Zeitungen und Zeitschriften veröffentlichen mithilfe der Syndication auch Nachrichten, Geschichten oder Artikel. Mit dem Abonnement solcher Feeds erhält ein Benutzer ständig die neuesten Informationen von diesen Sites. Zwar wird Syndication meist mit Blogs und Herausgebern verbunden, jedoch kann Syndication mit jeder Anwendung verwendet werden, die eine Auflistung von Informationen verfügbar macht. So kann beispielsweise eine Fehler-Datenbank mithilfe von Syndication-Feeds verfügbar gemacht werden. Sie können einen WCF-Dienst, der einen Vorgang namens verfügbar macht erstellen `CodeDefects`. Dieser Vorgang übernimmt einen Parameter mit der Angabe der E-Mail-Adresse der Person, deren Fehler Sie abrufen wollen. Ein Client kann die folgende URL verwenden, um den Vorgang aufzurufen: http://someserver/bugDatabase/CodeDefects?user=johndoe.  
  
## <a name="syndication-formats"></a>Syndication-Formate  
 Die WCF-Syndication-Plattform unterstützt RSS 2.0 und Atom 1.0.  
  
## <a name="see-also"></a>Siehe auch  
 [WCF-Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
