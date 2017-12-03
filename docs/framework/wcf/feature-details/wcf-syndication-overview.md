---
title: "Übersicht über WCF Syndication"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af6d4c39-e5e8-4099-aee6-5261feff9107
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4f1595cbb1d225e3dd4e73a354028745d4cd0428
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-syndication-overview"></a>Übersicht über WCF Syndication
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] unterstützt das Verfügbarmachen von Syndication-Feeds von einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst aus. Syndication ist ein Mechanismus der Anwendungsintegration, bei dem ein Server Anwendungsdaten in einem interoperablen, als Feed bezeichnetem Format verfügbar macht. Ein Feed ist eine Auflistung von Anwendungsdaten, die aus einigen feedeigenen Metadaten (Titel, Autor, URL und andere Metadaten) und einer Reihe von Feedelementen besteht. Innerhalb des Feeds sind die Feedelemente normalerweise in umgekehrter chronologischer Reihenfolge geordnet. Ein Feedelement besteht aus einem Standardsatz elementeigener Metadaten (Titel, URL, Erstellungsdatum, Kategorie und andere elementeigenen Metadaten) und einer beliebigen Anzahl anwendungsspezifischer Daten. Die beiden häufigsten Typen von Syndication-Feeds sind RSS&#160;2.0 (Really Simple Syndication) und Atom&#160;1.0, die beide von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt werden.  
  
## <a name="object-model"></a>Objektmodell  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] definiert eine Gruppe Syndication-spezifischer Klassen, die Ihnen ermöglichen, mit Feeds, Feedelementen und den zugehörigen Metadaten formatunabhängig zu arbeiten: <xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem>, <xref:System.ServiceModel.Syndication.SyndicationPerson>, <xref:System.ServiceModel.Syndication.SyndicationLink> sowie weitere Syndication-spezifische Klassen. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]definiert auch die Infrastrukturklassen, die auf den WCF REST-Programmiermodell, einschließlich der Syndication-Unterstützung bereitzustellen aufbauen: <xref:System.ServiceModel.Syndication.Atom10FeedFormatter>, und <!--zz <xref:System.ServiceModel.Syndication.RSS20FeedFormatter>--> `RSS20FeedFormatter`. Die Feedformatierungsklassen unterstützen das Serialisieren des Objektmodells in und aus RSS&#160;2.0 und Atom&#160;1.0.  
  
## <a name="scenarios"></a>Szenarien  
 Eine heute häufige Verwendung der Syndication stellt das Bloggen dar, bei dem der Autor eines Blogs periodisch bestimmte Informationen veröffentlicht. Dies können Texte, Bilder, Audioelemente oder andere Informationstypen sein. Viele Zeitungen und Zeitschriften veröffentlichen mithilfe der Syndication auch Nachrichten, Geschichten oder Artikel. Mit dem Abonnement solcher Feeds erhält ein Benutzer ständig die neuesten Informationen von diesen Sites. Zwar wird Syndication meist mit Blogs und Herausgebern verbunden, jedoch kann Syndication mit jeder Anwendung verwendet werden, die eine Auflistung von Informationen verfügbar macht. So kann beispielsweise eine Fehler-Datenbank mithilfe von Syndication-Feeds verfügbar gemacht werden. Sie können einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst erstellen, der einen Vorgang mit dem Namen `CodeDefects` verfügbar macht. Dieser Vorgang übernimmt einen Parameter mit der Angabe der E-Mail-Adresse der Person, deren Fehler Sie abrufen wollen. Ein Client kann die folgende URL verwenden, um den Vorgang aufzurufen: http://someserver/bugDatabase/CodeDefects? user=johndoe.  
  
## <a name="syndication-formats"></a>Syndication-Formate  
 Die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Syndication-Plattform unterstützt RSS&#160;2.0 und Atom&#160;1.0.  
  
## <a name="see-also"></a>Siehe auch  
 [WCF-Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
