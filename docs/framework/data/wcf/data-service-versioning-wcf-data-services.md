---
title: Datendienst-Versionskontrolle (WCF Data Services)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- versioning, WCF Data Services
- versioning [WCF Data Services]
- WCF Data Services, versioning
ms.assetid: e3e899cc-7f25-4f67-958f-063f01f79766
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 545096292f34566b4bb6c3c44bb20ddac426af26
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="data-service-versioning-wcf-data-services"></a>Datendienst-Versionskontrolle (WCF Data Services)
Die [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] ermöglicht es Ihnen, Datendienste zu erstellen, sodass Clients Daten als Ressourcen mit URIs zugreifen können, die auf einem Datenmodell basieren. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] unterstützt auch die Definition von Dienstvorgängen. Nach der ursprünglichen Bereitstellung und möglicherweise mehreren Bereitstellungen während ihrer Lebensdauer müssen diese Datendienste eventuell geändert werden. Dafür kann es verschiedene Gründe geben, z. B. veränderte Geschäftsanforderungen, Anforderungen an die Informationstechnologie oder andere Themen, die in die Dienste integriert werden müssen. Wenn Sie Änderungen an einem vorhandenen Datendienst vornehmen, müssen Sie berücksichtigen, ob eine neue Version des Datendiensts definiert wird und wie die Auswirkungen auf vorhandene Clientanwendungen am besten minimiert werden. Dieses Thema enthält einen Leitfaden, wann und wie eine neue Version eines Datendiensts erstellt wird. Es wird auch beschrieben, wie [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] einen Austausch zwischen Clients und Datendiensten behandelt, die andere Versionen des [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Protokolls unterstützen.  
  
## <a name="versioning-a-wcf-data-service"></a>Versionskontrolle eines WCF Data Service  
 Sobald ein Datendienst bereitgestellt wird und die Daten genutzt werden, können Änderungen am Datendienst zu Kompatibilitätsproblemen mit vorhandenen Clientanwendungen führen. Da Änderungen aber oft aufgrund der übergreifenden Geschäftsanforderungen des Diensts erforderlich sind, müssen Sie berücksichtigen, wann und wie eine neue Version des Datendiensts mit den geringsten Auswirkungen auf Clientanwendungen erstellt wird.  
  
### <a name="data-model-changes-that-recommend-a-new-data-service-version"></a>Datenmodelländerungen, die eine neue Version des Datendiensts empfehlen  
 Wenn Sie die Veröffentlichung einer neuen Version eines Datendiensts in Betracht ziehen, ist es wichtig, zu verstehen, wie die anderen Arten von Änderungen sich möglicherweise auf Clientanwendungen auswirken. Änderungen an einem Datendienst, die möglicherweise die Erstellung einer neuen Version eines Datendiensts erforderlich machen, können in die folgenden beiden Kategorien unterteilt werden:  
  
-   Änderungen am Dienstvertrag – darunter Aktualisierungen für Dienstvorgänge, Änderungen hinsichtlich des Zugriffs auf Entitätenmengen (Feeds), Versionsänderungen und andere Änderungen bezüglich Dienstverhaltensweisen.  
  
-   Änderungen am Datenvertrag – darunter Änderungen am Datenmodell, an Feedformaten oder Feedanpassungen.  
  
 Die folgende Tabelle führt die Arten von Änderungen auf, für die das Veröffentlichen einer neuen Version des Datendiensts in Betracht gezogen werden sollte:  
  
|Art der Änderung|Erfordert eine neue Version|Neue Version ist nicht erforderlich|  
|--------------------|----------------------------|----------------------------|  
|Dienstvorgänge|-Neuen Parameter hinzufügen<br />– Ändern des Rückgabetyps<br />– Entfernen des Dienstvorgangs|-Löschen Sie vorhandene parameter<br />-Hinzufügen von neuen Dienstvorgangs|  
|Dienstverhaltensweisen|– Deaktivieren von anzahlanforderungen<br />– Deaktivieren von projektionsunterstützung<br />-Erhöhen der erforderlichen datendienstversion|-Aktivieren von anzahlanforderungen<br />-Aktivieren von projektionsunterstützung<br />-Verringern der erforderlichen datendienstversion|  
|Entitätenmengenberechtigungen|-Einschränken von entitätenmengenberechtigungen<br />– Ändern des Antwortcodes (neuer erster Ziffernwert) <sup>1</sup>|-Lockern von entitätenmengenberechtigungen<br />– Ändern des Antwortcodes (gleiche erster Ziffernwert)|  
|Entitätseigenschaften|-Entfernen Sie die vorhandene Eigenschaft oder Beziehung<br />-NULL-Eigenschaft hinzufügen<br />– Ändern einer vorhandenen Eigenschaft|-Fügen Sie nullable-Eigenschaft<sup>2</sup>|  
|Entitätenmengen|-Entfernen einer Entitätenmenge|– Hinzufügen eines abgeleiteten Typs<br />-Basistyp ändern<br />-Hinzufügen einer Entitätenmenge|  
|Feedanpassung|-Entitätseigenschaftszuordnung ändern||  
  
 <sup>1</sup> dies hängen wie strikt eine Clientanwendung basiert auf einen bestimmten Fehlercode empfangen.  
  
 <sup>2</sup> können Sie festlegen, die <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> Eigenschaft `true` , damit vom Client alle neuen Eigenschaften, die vom Datendienst gesendeten zu ignorieren, die nicht auf dem Client definiert sind. Wenn aber Einfügungen vorgenommen werden, werden die nicht vom Client einbezogenen Eigenschaften in der POST-Anforderung auf ihre Standardwerte festgelegt. Bei Aktualisierungen können vorhandene Daten in einer Eigenschaft, die dem Client nicht bekannt ist, mit Standardwerten überschrieben werden. In diesem Fall sollten Sie die Aktualisierung als MERGE-Anforderung senden. Dies ist die Standardeinstellung. Weitere Informationen finden Sie unter [Verwalten des Datendienstkontextes](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md).  
  
### <a name="how-to-version-a-data-service"></a>So versionieren Sie einen Datendienst  
 Bei Bedarf wird eine neue Datendienstversion definiert, indem eine neue Instanz des Diensts mit einem aktualisierten Dienstvertrag oder einem Datenmodell erstellt wird. Dieser neue Dienst wird dann mit einem neuen URI-Endpunkt verfügbar gemacht, der sich von der früheren Version unterscheidet. Beispiel:  
  
-   Alte Version: `http://services.odata.org/Northwind/v1/Northwind.svc/`  
  
-   Neue Version: `http://services.odata.org/Northwind/v2/Northwind.svc/`  
  
 Wenn Sie einen Datendienst aktualisieren, müssen Clients auch auf Grundlage der neuen Datendienstmetadaten aktualisiert werden und den neuen Stamm-URI verwenden. Wenn möglich, sollten Sie die frühere Version des Datendiensts beibehalten, um Clients zu unterstützen, die noch nicht für die Verwendung der neuen Version aktualisiert wurden. Frühere Versionen eines Datendiensts können entfernt werden, wenn sie nicht mehr benötigt werden. Sie sollten erwägen, den Datendienstendpunkt-URI in einer externen Konfigurationsdatei beizubehalten.  
  
## <a name="odata-protocol-versions"></a>OData-Protokollversionen  
 Wenn neue Versionen von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] werden freigegeben, Clientanwendungen möglicherweise nicht verwenden die gleiche Version von den [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Protokoll, das vom Datendienst unterstützt wird. Eine ältere Clientanwendung greift möglicherweise auf einen Datendienst zu, der eine neuere Version von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] unterstützt. Eine Clientanwendung eine neuere Version des auch mithilfe der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] -Clientbibliothek, die eine neuere Version von unterstützt [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] als Datendienst verfügt, die auf den zugegriffen wird.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]nutzt zur Unterstützung von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] zu solcher versionsszenarien. Es gibt auch Unterstützung für das Generieren und Verwenden von Datenmodellmetadaten für Client-Datendienstklassen erstellen, wenn der Client eine andere Version verwendet [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] als der Datendienst verwendet. Weitere Informationen finden Sie unter [OData: Versionskontrolle von Protokollen](http://go.microsoft.com/fwlink/?LinkId=186071).  
  
### <a name="version-negotiation"></a>Versionsaushandlung  
 Der Datendienst kann konfiguriert die höchste Version des definieren die [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Protokoll, das vom Dienst unabhängig von der Version, die vom Client angeforderte verwendet werden soll. Hierzu können Sie durch Angabe einer <xref:System.Data.Services.Common.DataServiceProtocolVersion> Wert für die <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> Eigenschaft von der <xref:System.Data.Services.DataServiceBehavior> vom Datendienst verwendet. Weitere Informationen finden Sie unter [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 Wenn eine Anwendung mithilfe der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clientbibliotheken auf einen Datendienst zugreift, legen die Bibliotheken diese Header je nach [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Version und den in der Anwendung verwendeten Funktionen automatisch auf die richtigen Werte fest. Standardmäßig [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] verwendet die niedrigste Protokollversion, die den angeforderten Vorgang unterstützt.  
  
 Die folgende Tabelle enthält die Versionen von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] und [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)], die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Unterstützung für bestimmte Versionen des [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Protokolls bieten.  
  
|[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Protokollversion|Unterstützt seit...|  
|-----------------------------------------------------------------------------------|----------------------------|  
|Version 1|-   [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]Servicepack 1 (SP1)<br />-   [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)]Version 3|  
|Version 2|-   [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]<br />-Ein Update für [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] SP1. Können Sie herunterladen und installieren Sie das Update aus der [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=158125).<br />-   [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)]Version 4|  
|Version 3|– Sie können herunterladen und installieren Sie eine Vorabversion, die unterstützt [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 3-Version aus der [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=203885).|  
  
### <a name="metadata-versions"></a>Metadatenversionen  
 Standardmäßig stellt [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] Datenmodelle mit Version 1.1 von CSDL dar. Dies ist immer bei Datenmodellen der Fall, die auf einem Reflektionsanbieter oder einem benutzerdefinierten Datendienstanbieter basieren. Wenn das Datenmodell jedoch mit [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] definiert wird, wird die CSDL-Version zurückgegeben, die von [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] verwendet wird. Die Version des Endes der CSDL wird bestimmt durch den Namespace des der [Schemaelement](http://msdn.microsoft.com/en-us/396074d8-f99c-4f50-a073-68bce848224f). [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]die Spezifikation [ \[MC-CSDL\]: Conceptual Schema Definition File Format](http://go.microsoft.com/fwlink/?LinkId=159072).  
  
 Das `DataServices`-Element der zurückgegebenen Metadaten enthält auch ein `DataServiceVersion`-Attribut, das den gleichen Wert wie der `DataServiceVersion`-Header in der Antwortnachricht hat. Clientanwendungen, z. B. die **Hinzufügen eines Dienstverweises** im Dialogfeld [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], verwenden Sie diese Informationen zum Generieren von Client-Datendienstklassen, die ordnungsgemäß mit der Version der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] , die den Datendienst hostet. Weitere Informationen finden Sie unter [OData: Versionskontrolle von Protokollen](http://go.microsoft.com/fwlink/?LinkId=186071).  
  
## <a name="see-also"></a>Siehe auch  
 [Datendienstanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
