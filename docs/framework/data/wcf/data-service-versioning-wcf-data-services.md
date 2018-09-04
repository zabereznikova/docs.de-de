---
title: Datendienst-Versionskontrolle (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- versioning, WCF Data Services
- versioning [WCF Data Services]
- WCF Data Services, versioning
ms.assetid: e3e899cc-7f25-4f67-958f-063f01f79766
ms.openlocfilehash: 9a92346267012d3651d04648b357bbf530097e34
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43565638"
---
# <a name="data-service-versioning-wcf-data-services"></a>Datendienst-Versionskontrolle (WCF Data Services)
Die [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] ermöglicht es Ihnen, Datendienste zu erstellen, sodass Clients Daten als Ressourcen mit URIs zugreifen können, die auf einem Datenmodell basieren. OData unterstützt auch die Definition von Dienstvorgängen. Nach der ursprünglichen Bereitstellung und möglicherweise mehreren Bereitstellungen während ihrer Lebensdauer müssen diese Datendienste eventuell geändert werden. Dafür kann es verschiedene Gründe geben, z. B. veränderte Geschäftsanforderungen, Anforderungen an die Informationstechnologie oder andere Themen, die in die Dienste integriert werden müssen. Wenn Sie Änderungen an einem vorhandenen Datendienst vornehmen, müssen Sie berücksichtigen, ob eine neue Version des Datendiensts definiert wird und wie die Auswirkungen auf vorhandene Clientanwendungen am besten minimiert werden. Dieses Thema enthält einen Leitfaden, wann und wie eine neue Version eines Datendiensts erstellt wird. Es wird beschrieben, wie WCF Data Services verarbeitet einen Austausch zwischen Clients und Datendiensten, die verschiedene Versionen des OData-Protokolls unterstützen.

## <a name="versioning-a-wcf-data-service"></a>Versionskontrolle eines WCF Data Service
 Sobald ein Datendienst bereitgestellt wird und die Daten genutzt werden, können Änderungen am Datendienst zu Kompatibilitätsproblemen mit vorhandenen Clientanwendungen führen. Da Änderungen aber oft aufgrund der übergreifenden Geschäftsanforderungen des Diensts erforderlich sind, müssen Sie berücksichtigen, wann und wie eine neue Version des Datendiensts mit den geringsten Auswirkungen auf Clientanwendungen erstellt wird.

### <a name="data-model-changes-that-recommend-a-new-data-service-version"></a>Datenmodelländerungen, die eine neue Version des Datendiensts empfehlen
 Wenn Sie die Veröffentlichung einer neuen Version eines Datendiensts in Betracht ziehen, ist es wichtig, zu verstehen, wie die anderen Arten von Änderungen sich möglicherweise auf Clientanwendungen auswirken. Änderungen an einem Datendienst, die möglicherweise die Erstellung einer neuen Version eines Datendiensts erforderlich machen, können in die folgenden beiden Kategorien unterteilt werden:

-   Änderungen am Dienstvertrag – darunter Aktualisierungen für Dienstvorgänge, Änderungen hinsichtlich des Zugriffs auf Entitätenmengen (Feeds), Versionsänderungen und andere Änderungen bezüglich Dienstverhaltensweisen.

-   Änderungen am Datenvertrag – darunter Änderungen am Datenmodell, an Feedformaten oder Feedanpassungen.

 Die folgende Tabelle führt die Arten von Änderungen auf, für die das Veröffentlichen einer neuen Version des Datendiensts in Betracht gezogen werden sollte:

|Art der Änderung|Erfordert eine neue Version|Neue Version ist nicht erforderlich|
|--------------------|----------------------------|----------------------------|
|Dienstvorgänge|-Neuen Parameter hinzufügen<br />: Rückgabetyp ändern<br />– Entfernen des Dienstvorgangs|– Löschen des vorhandenen Parameters<br />: Hinzufügen von neuen Dienstvorgangs|
|Dienstverhaltensweisen|– Deaktivieren von anzahlanforderungen<br />– Deaktivieren von projektionsunterstützung<br />-Erhöhen Sie die erforderlichen datendienstversion|– Aktivieren von anzahlanforderungen<br />– Aktivieren von projektionsunterstützung<br />-Verringern der erforderlichen datendienstversion|
|Entitätenmengenberechtigungen|-Einschränken von entitätenmengenberechtigungen<br />– Ändern des Antwortcodes (neuer erster Ziffernwert) <sup>1</sup>|-Lockern von entitätenmengenberechtigungen<br />– Ändern des Antwortcodes (gleiche erster Ziffernwert)|
|Entitätseigenschaften|-Entfernen Sie die vorhandene Eigenschaft oder Beziehung<br />-NULL-Eigenschaft hinzufügen<br />-Ändern einer vorhandenen Eigenschaft|-Hinzufügen von nullable-Eigenschaft<sup>2</sup>|
|Entitätenmengen|– Entfernen einer Entitätenmenge|– Hinzufügen eines abgeleiteten Typs<br />– Ändern des Basistyps<br />– Hinzufügen einer Entitätenmenge|
|Feedanpassung|– Änderung entitätseigenschaftszuordnung||

 <sup>1</sup> Dies hängt möglicherweise wie stark eine Clientanwendung basiert auf einen bestimmten Fehlercode empfangen.

 <sup>2</sup> können Sie festlegen, die <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> Eigenschaft `true` , damit vom Client alle neuen Eigenschaften, die vom Datendienst gesendeten zu ignorieren, die nicht auf dem Client definiert sind. Wenn aber Einfügungen vorgenommen werden, werden die nicht vom Client einbezogenen Eigenschaften in der POST-Anforderung auf ihre Standardwerte festgelegt. Bei Aktualisierungen können vorhandene Daten in einer Eigenschaft, die dem Client nicht bekannt ist, mit Standardwerten überschrieben werden. In diesem Fall sollten Sie die Aktualisierung als MERGE-Anforderung senden. Dies ist die Standardeinstellung. Weitere Informationen finden Sie unter [Verwalten des Datendienstkontextes](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md).

### <a name="how-to-version-a-data-service"></a>So versionieren Sie einen Datendienst
 Bei Bedarf wird eine neue Datendienstversion definiert, indem eine neue Instanz des Diensts mit einem aktualisierten Dienstvertrag oder einem Datenmodell erstellt wird. Dieser neue Dienst wird dann mit einem neuen URI-Endpunkt verfügbar gemacht, der sich von der früheren Version unterscheidet. Beispiel:

-   Alte Version: `http://services.odata.org/Northwind/v1/Northwind.svc/`

-   Neue Version: `http://services.odata.org/Northwind/v2/Northwind.svc/`

 Wenn Sie einen Datendienst aktualisieren, müssen Clients auch auf Grundlage der neuen Datendienstmetadaten aktualisiert werden und den neuen Stamm-URI verwenden. Wenn möglich, sollten Sie die frühere Version des Datendiensts beibehalten, um Clients zu unterstützen, die noch nicht für die Verwendung der neuen Version aktualisiert wurden. Frühere Versionen eines Datendiensts können entfernt werden, wenn sie nicht mehr benötigt werden. Sie sollten erwägen, den Datendienstendpunkt-URI in einer externen Konfigurationsdatei beizubehalten.

## <a name="odata-protocol-versions"></a>OData-Protokollversionen
 Wenn neue Versionen von OData veröffentlicht werden, können Clientanwendungen nicht die gleiche Version des OData-Protokolls verwenden, die vom Datendienst unterstützt wird. Eine ältere Clientanwendung greift möglicherweise auf einen Datendienst zugreifen, der eine neuere Version von OData unterstützt. Eine Client-Anwendung auch eine neuere Version von der Clientbibliothek für WCF Data Services verwenden möglicherweise eine neuere Version von OData, als der Datendienst, der auf den zugegriffen wird, wird unterstützt.

 WCF Data Services nutzt die Unterstützung von OData auf die Behandlung solcher versionsszenarien. Es gibt auch Unterstützung für das Generieren und Verwenden von Datenmodellmetadaten für die Client-Datendienstklassen erstellen, wenn der Client eine andere Version von OData als Daten verwendet-Dienst verwendet. Weitere Informationen finden Sie unter [OData: Protocol Versioning](https://go.microsoft.com/fwlink/?LinkId=186071).

### <a name="version-negotiation"></a>Versionsaushandlung
 Der Datendienst kann so konfiguriert werden, um die höchste Version des OData-Protokolls zu definieren, die vom Dienst unabhängig von der vom Client angeforderten Version verwendet werden. Hierzu können Sie angeben einer <xref:System.Data.Services.Common.DataServiceProtocolVersion> Wert für die <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> Eigenschaft der <xref:System.Data.Services.DataServiceBehavior> vom Datendienst verwendet. Weitere Informationen finden Sie unter [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).

 Wenn eine Anwendung die WCF Data Services-Clientbibliotheken verwendet, um einen Datendienst zugreifen, diese Header automatisch von die Bibliotheken auf die richtigen Werte, je nach Version OData und die Funktionen, die in Ihrer Anwendung verwendet werden festgelegt. WCF Data Services verwendet standardmäßig die niedrigste Protokollversion, die den angeforderten Vorgang unterstützt.

 In der folgende Tabelle werden die Versionen von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] und [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)] enthalten, die die WCF Data Services-Unterstützung für bestimmte Versionen des OData-Protokolls.

|OData-Protokollversion|Unterstützt seit...|
|-----------------------------------------------------------------------------------|----------------------------|
|Version 1|-   [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] Servicepack 1 (SP1)<br />-   [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)] Version 3|
|Version 2|-   [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]<br />-Ein Update für [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] SP1. Sie können auch herunterladen und installieren Sie das Update aus dem [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=158125).<br />-   [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)] Version 4|
|Version 3|– Sie können auch herunterladen und installieren Sie eine Vorabversion, die OData Version 3 unterstützt die [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=203885).|

### <a name="metadata-versions"></a>Metadatenversionen
 Standardmäßig verwendet WCF Data Services Version 1.1 von CSDL, um ein Datenmodell darzustellen. Dies ist immer bei Datenmodellen der Fall, die auf einem Reflektionsanbieter oder einem benutzerdefinierten Datendienstanbieter basieren. Wenn das Datenmodell jedoch mit [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] definiert wird, wird die CSDL-Version zurückgegeben, die von [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] verwendet wird. Die CSDL-Version richtet sich nach den Namespace der [Schemaelement](https://msdn.microsoft.com/library/396074d8-f99c-4f50-a073-68bce848224f). Weitere Informationen finden Sie in der Spezifikation [ \[MC-CSDL\]: Conceptual Schema Definition File Format](https://go.microsoft.com/fwlink/?LinkId=159072).

 Das `DataServices`-Element der zurückgegebenen Metadaten enthält auch ein `DataServiceVersion`-Attribut, das den gleichen Wert wie der `DataServiceVersion`-Header in der Antwortnachricht hat. Clientanwendungen, z. B. die **Hinzufügen eines Dienstverweises** Dialogfeld in Visual Studio verwenden Sie diese Informationen zum Generieren von clientdatendienstklassen, die mit der Version von WCF Data Services ordnungsgemäß arbeiten, die den Datendienst hostet. Weitere Informationen finden Sie unter [OData: Protocol Versioning](https://go.microsoft.com/fwlink/?LinkId=186071).

## <a name="see-also"></a>Siehe auch

- [Datendienstanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
