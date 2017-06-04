---
title: "Datendienst-Versionskontrolle (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Versionskontrolle [WCF Data Services]"
  - "Versionskontrolle, WCF Data Services"
  - "WCF Data Services, Versionskontrolle"
ms.assetid: e3e899cc-7f25-4f67-958f-063f01f79766
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Datendienst-Versionskontrolle (WCF Data Services)
Der [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] ermöglicht es Ihnen, Datendienste zu erstellen, damit Clients auf Daten als Ressourcen mit URIs zugreifen können, die auf einem Datenmodell basieren.  [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] unterstützt auch die Definition von Dienstvorgängen.  Nach der ursprünglichen Bereitstellung und möglicherweise mehreren Bereitstellungen während ihrer Lebensdauer müssen diese Datendienste eventuell geändert werden. Dafür kann es verschiedene Gründe geben, z. B. veränderte Geschäftsanforderungen, Anforderungen an die Informationstechnologie oder andere Themen, die in die Dienste integriert werden müssen.  Wenn Sie Änderungen an einem vorhandenen Datendienst vornehmen, müssen Sie berücksichtigen, ob eine neue Version des Datendiensts definiert wird und wie die Auswirkungen auf vorhandene Clientanwendungen am besten minimiert werden.  Dieses Thema enthält einen Leitfaden, wann und wie eine neue Version eines Datendiensts erstellt wird.  Es wird auch beschrieben, wie [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] einen Austausch zwischen Clients und Datendiensten behandelt, die andere Versionen des [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Protokolls unterstützen.  
  
## Versionskontrolle eines WCF Data Service  
 Sobald ein Datendienst bereitgestellt wird und die Daten genutzt werden, können Änderungen am Datendienst zu Kompatibilitätsproblemen mit vorhandenen Clientanwendungen führen.  Da Änderungen aber oft aufgrund der übergreifenden Geschäftsanforderungen des Diensts erforderlich sind, müssen Sie berücksichtigen, wann und wie eine neue Version des Datendiensts mit den geringsten Auswirkungen auf Clientanwendungen erstellt wird.  
  
### Datenmodelländerungen, die eine neue Version des Datendiensts empfehlen  
 Wenn Sie die Veröffentlichung einer neuen Version eines Datendiensts in Betracht ziehen, ist es wichtig, zu verstehen, wie die anderen Arten von Änderungen sich möglicherweise auf Clientanwendungen auswirken.  Änderungen an einem Datendienst, die möglicherweise die Erstellung einer neuen Version eines Datendiensts erforderlich machen, können in die folgenden beiden Kategorien unterteilt werden:  
  
-   Änderungen am Dienstvertrag – darunter Aktualisierungen für Dienstvorgänge, Änderungen hinsichtlich des Zugriffs auf Entitätenmengen \(Feeds\), Versionsänderungen und andere Änderungen bezüglich Dienstverhaltensweisen.  
  
-   Änderungen am Datenvertrag – darunter Änderungen am Datenmodell, an Feedformaten oder Feedanpassungen.  
  
 Die folgende Tabelle führt die Arten von Änderungen auf, für die das Veröffentlichen einer neuen Version des Datendiensts in Betracht gezogen werden sollte:  
  
|Art der Änderung|Erfordert eine neue Version|Neue Version ist nicht erforderlich|  
|----------------------|---------------------------------|-----------------------------------------|  
|Dienstvorgänge|-   Neuen Parameter hinzufügen<br />-   Ändern des Rückgabetyps<br />-   Entfernen des Dienstvorgangs|-   Löschen des vorhandenen Parameters<br />-   Hinzufügen eines neuen Dienstvorgangs|  
|Dienstverhaltensweisen|-   Deaktivieren von Anzahlanforderungen<br />-   Deaktivieren von Projektionsunterstützung<br />-   Erhöhen der erforderlichen Datendienstversion|-   Aktivieren von Anzahlanforderungen<br />-   Aktivieren von Projektionsunterstützung<br />-   Verringern der erforderlichen Datendienstversion|  
|Entitätenmengenberechtigungen|-   Einschränken von Entitätenmengenberechtigungen<br />-   Ändern des Antwortcodes \(neuer erster Ziffernwert\) <sup>1</sup>|-   Lockern von Entitätenmengenberechtigungen<br />-   Ändern des Antwortcodes \(gleicher erster Ziffernwert\)|  
|Entitätseigenschaften|-   Entfernen von vorhandener Eigenschaft oder Beziehung<br />-   Hinzufügen einer Eigenschaft, die keine NULL\-Werte zulässt<br />-   Ändern einer vorhandenen Eigenschaft|-   Hinzufügen einer Eigenschaft, die NULL\-Werte zulässt<sup>2</sup>|  
|Entitätenmengen|-   Entfernen einer Entitätenmenge|-   Hinzufügen eines abgeleiteten Typs<br />-   Ändern eines Basistyps<br />-   Hinzufügen einer Entitätenmenge|  
|Feedanpassung|-   Ändern einer Entitätseigenschaftszuordnung||  
  
 <sup>1</sup> Dies hängt möglicherweise davon ab, wie stark eine Clientanwendung auf den Empfang eines bestimmten Fehlercodes basiert.  
  
 <sup>2</sup> Sie können die <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A>\-Eigenschaft auf `true` festlegen, sodass der Client alle neuen Eigenschaften ignoriert, die vom Datendienst gesendet werden und nicht im Client definiert werden.  Wenn aber Einfügungen vorgenommen werden, werden die nicht vom Client einbezogenen Eigenschaften in der POST\-Anforderung auf ihre Standardwerte festgelegt.  Bei Aktualisierungen können vorhandene Daten in einer Eigenschaft, die dem Client nicht bekannt ist, mit Standardwerten überschrieben werden.  In diesem Fall sollten Sie die Aktualisierung als MERGE\-Anforderung senden. Dies ist die Standardeinstellung.  Weitere Informationen finden Sie unter [Verwalten des Datendienstkontextes](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md).  
  
### So versionieren Sie einen Datendienst  
 Bei Bedarf wird eine neue Datendienstversion definiert, indem eine neue Instanz des Diensts mit einem aktualisierten Dienstvertrag oder einem Datenmodell erstellt wird.  Dieser neue Dienst wird dann mit einem neuen URI\-Endpunkt verfügbar gemacht, der sich von der früheren Version unterscheidet.  Beispiel:  
  
-   Alte Version: `http://services.odata.org/Northwind/v1/Northwind.svc/`  
  
-   Neue Version: `http://services.odata.org/Northwind/v2/Northwind.svc/`  
  
 Wenn Sie einen Datendienst aktualisieren, müssen Clients auch auf Grundlage der neuen Datendienstmetadaten aktualisiert werden und den neuen Stamm\-URI verwenden.  Wenn möglich, sollten Sie die frühere Version des Datendiensts beibehalten, um Clients zu unterstützen, die noch nicht für die Verwendung der neuen Version aktualisiert wurden.  Frühere Versionen eines Datendiensts können entfernt werden, wenn sie nicht mehr benötigt werden.  Sie sollten erwägen, den Datendienstendpunkt\-URI in einer externen Konfigurationsdatei beizubehalten.  
  
## OData\-Protokollversionen  
 Wenn neue Versionen von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] veröffentlicht werden, verwenden Clientanwendungen möglicherweise nicht die Version des [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Protokolls, die vom Datendienst unterstützt wird.  Eine ältere Clientanwendung greift möglicherweise auf einen Datendienst zu, der eine neuere Version von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] unterstützt.  Eine Clientanwendung kann möglicherweise auch eine neuere Version der [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Clientbibliothek verwenden, die eine neuere Version von [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] unterstützt als der Datendienst, auf den zugegriffen wird.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] nutzt die von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] bereitgestellte Unterstützung zur Behandlung solcher Versionsszenarien.  Zudem wird das Generieren und Erstellen von Clientdatendienstklassen mithilfe von Datenmodellmetadaten auch dann unterstützt, wenn der Client eine andere Version von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] verwendet als der Datendienst.  Weitere Informationen finden Sie unter [OData\-Protokollversionen](http://go.microsoft.com/fwlink/?LinkId=186071).  
  
### Versionsaushandlung  
 Der Datendienst kann so konfiguriert werden, dass die höchste Version des [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Protokolls definiert wird, die unabhängig von der vom Client angeforderten Version vom Dienst verwendet wird.  Hierzu geben Sie einen <xref:System.Data.Services.Common.DataServiceProtocolVersion>\-Wert für die <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A>\-Eigenschaft der vom Datendienst verwendeten <xref:System.Data.Services.DataServiceBehavior>\-Instanz an.  Weitere Informationen finden Sie unter [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 Wenn eine Anwendung mithilfe der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]\-Clientbibliotheken auf einen Datendienst zugreift, legen die Bibliotheken diese Header je nach [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Version und den in der Anwendung verwendeten Funktionen automatisch auf die richtigen Werte fest.  In der Standardeinstellung verwendet [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] die niedrigste Protokollversion, die den angeforderten Vorgang unterstützt.  
  
 Die folgende Tabelle enthält die Versionen von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] und [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)], die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]\-Unterstützung für bestimmte Versionen des [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Protokolls bieten.  
  
|[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Protokollversion|Unterstützt seit...|  
|------------------------------------------------------------------------------------|-------------------------|  
|Version 1|-   [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] Service Pack 1 \(SP1\)<br />-   [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)] Version 3|  
|Version 2|-   [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]<br />-   Update auf [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] SP1.  Sie können das Update vom [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=158125) herunterladen und anschließend installieren.<br />-   [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)] Version 4|  
|Version 3|-   Sie können eine Vorabversion, die [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Version 3 unterstützt, vom [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=203885) herunterladen und installieren.|  
  
### Metadatenversionen  
 Standardmäßig stellt [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] Datenmodelle mit Version 1.1 von CSDL dar.  Dies ist immer bei Datenmodellen der Fall, die auf einem Reflektionsanbieter oder einem benutzerdefinierten Datendienstanbieter basieren.  Wenn das Datenmodell jedoch mit [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] definiert wird, wird die CSDL\-Version zurückgegeben, die von [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] verwendet wird.  Die CSDL\-Version wird anhand des Namespace des [Schemaelements](http://msdn.microsoft.com/de-de/396074d8-f99c-4f50-a073-68bce848224f) bestimmt.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] in der Spezifikation [\[MC\-CSDL\]: Conceptual Schema Definition File Format](http://go.microsoft.com/fwlink/?LinkId=159072).  
  
 Das `DataServices`\-Element der zurückgegebenen Metadaten enthält auch ein `DataServiceVersion`\-Attribut, das den gleichen Wert wie der `DataServiceVersion`\-Header in der Antwortnachricht hat.  Clientanwendungen wie das Dialogfeld **Dienstverweis hinzufügen** in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] generieren mithilfe dieser Informationen Client\-Datendienstklassen, die korrekt mit der Version von [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] funktionieren, die den Datendienst hostet.  Weitere Informationen finden Sie unter [OData\-Protokollversionen](http://go.microsoft.com/fwlink/?LinkId=186071).  
  
## Siehe auch  
 [Datendiensteanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)   
 [Definieren von WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)