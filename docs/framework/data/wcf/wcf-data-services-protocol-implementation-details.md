---
title: Details der WCF Data Services-Protokollimplementierung
ms.date: 03/30/2017
ms.assetid: 712d689b-fada-4cbb-bcdb-d65a3ef83b4c
ms.openlocfilehash: a9b996671f2d8b57593f80fb13e966c5f03a2801
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190389"
---
# <a name="wcf-data-services-protocol-implementation-details"></a>Details der WCF Data Services-Protokollimplementierung

## <a name="odata-protocol-implementation-details"></a>Details der OData-Protokollimplementierung  

Der Open Data Protocol (odata) erfordert, dass ein Datendienst, der das Protokoll implementiert, einen bestimmten minimalen Satz von Funktionen bereitstellt. Diese Funktionen werden in den Protokoll Dokumenten in Bezug auf "sollte" und "muss" beschrieben. Weitere optionale Funktionen werden im Hinblick auf "Mai" beschrieben. In diesem Artikel werden diese optionalen Funktionen beschrieben, die derzeit nicht von WCF Data Services implementiert werden.
  
### <a name="support-for-the-format-query-option"></a>Unterstützung für die $format-Abfrageoption  

 Das odata-Protokoll unterstützt JavaScript-Notation (JSON) und Atom-Feeds, und odata stellt die `$format` System Abfrage Option bereit, mit der ein Client das Format des Antwort Feeds anfordern kann. Diese Systemabfrageoption (falls sie vom Datendienst unterstützt wird) muss den Wert des Accept-Headers der Anforderung überschreiben. WCF Data Services unterstützt das Zurückgeben von JSON-und Atom-Feeds. Die Standardimplementierung unterstützt jedoch die `$format`-Abfrageoption nicht und verwendet nur den Wert des Accept-Headers, um das Format der Antwort zu bestimmen. Es gibt Situationen, in denen der Datendienst möglicherweise die `$format`-Abfrageoption unterstützen muss, z. B., wenn Clients den Accept-Header nicht festlegen können. Um diese Szenarien zu unterstützen, müssen Sie den Datendienst erweitern, um diese Option im URI zu verwenden.
  
## <a name="wcf-data-services-behaviors"></a>WCF Data Services - Verhaltensweisen  

 Die folgenden WCF Data Services Verhalten werden nicht explizit durch das odata-Protokoll definiert:  
  
### <a name="default-sorting-behavior"></a>Standardsortierverhalten  

 Wenn eine Abfrageanforderung, die an den Datendienst gesendet wird, eine `$top`-Systemabfrageoption oder eine `$skip`-Systemabfrageoption einschließt und die `$orderby`-Systemabfrageoption nicht einschließt, wird der zurückgegebene Feed nach den Schlüsseleigenschaften in aufsteigender Reihenfolge sortiert. Das liegt daran, dass die Reihenfolge erforderlich ist, um das richtige Paging von Ergebnissen sicherzustellen. Hierzu fügt der Datendienst der Abfrage einen Reihenfolgenausdruck hinzu. Dieses Verhalten tritt auch auf, wenn servergesteuertes Paging im Datendienst aktiviert wird. Weitere Informationen finden Sie unter [Konfigurieren des Daten Dienstanbieter](configuring-the-data-service-wcf-data-services.md). Wenn Sie die Reihenfolge des zurückgegebenen Feeds steuern möchten, sollten Sie `$orderby` in den Abfrage-URI einschließen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Definieren von WCF Data Services](defining-wcf-data-services.md)
- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
