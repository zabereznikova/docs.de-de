---
title: "Details der WCF Data Services-Protokollimplementierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 712d689b-fada-4cbb-bcdb-d65a3ef83b4c
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Details der WCF Data Services-Protokollimplementierung
## Details der OData\-Protokollimplementierung  
 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] erfordert, dass ein Datendienst, der das Protokoll implementiert, einen bestimmten minimalen Satz von Funktionalitäten bereitstellt.  Diese Funktionen werden in den Protokolldokumenten mit den Begriffen "sollte" und "muss" beschrieben. Andere optionale Funktionalitäten werden mit dem Begriff "kann" beschrieben. In diesem Thema werden diese optionalen Funktionen, die derzeit nicht von [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] implementiert sind, beschrieben.  Weitere Informationen finden Sie in der [OData\-Protokolldokumentation](http://go.microsoft.com/fwlink/?LinkID=184554).  
  
### Unterstützung für die $format\-Abfrageoption  
 Das [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Protokoll unterstützt sowohl JSON\- \(JavaScript Notation\) als auch Atom\-Feeds, und [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] stellt die `$format`\-Systemabfrageoption bereit, um es einem Client zu ermöglichen, das Format des Antwortfeeds anzufordern.  Diese Systemabfrageoption \(falls sie vom Datendienst unterstützt wird\) muss den Wert des Accept\-Headers der Anforderung überschreiben.  [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] unterstützt das Zurückgeben von JSON\- und Atom\-Feeds.  Die Standardimplementierung unterstützt jedoch die `$format`\-Abfrageoption nicht und verwendet nur den Wert des Accept\-Headers, um das Format der Antwort zu bestimmen.  Es gibt Situationen, in denen der Datendienst möglicherweise die `$format`\-Abfrageoption unterstützen muss, z. B., wenn Clients den Accept\-Header nicht festlegen können.  Um diese Szenarien zu unterstützen, müssen Sie den Datendienst erweitern, um diese Option im URI zu verwenden.  Sie können dem Datendienst diese Funktionalität hinzufügen, indem Sie das Beispielprojekt [JSONP\- und URL\-gesteuerte Formatunterstützung für ADO.NET Data Services](http://go.microsoft.com/fwlink/?LinkId=208228) von der MSDN Code Gallery\-Website herunterladen und es zum Datendienstprojekt hinzufügen.  In diesem Beispiel wird die `$format`\-Abfrageoption entfernt und der Accept\-Header in `application/json` geändert.  Wenn Sie das Beispielprojekt einschließen und das `JSONPSupportBehaviorAttribute` zur Datendienstklasse hinzufügen, ermöglicht es dem Dienst, die `$format`\-Abfrageoption `$format=json` zu verwenden.  Eine weitere Anpassung dieses Beispielprojekts ist erforderlich, um auch `$format=atom` oder andere benutzerdefinierte Formate zu verwenden.  
  
## WCF Data Services \- Verhaltensweisen  
 Die folgenden [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]\-Verhaltensweisen werden nicht explizit vom [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Protokoll definiert:  
  
### Standardsortierverhalten  
 Wenn eine Abfrageanforderung, die an den Datendienst gesendet wird, eine `$top`\-Systemabfrageoption oder eine `$skip`\-Systemabfrageoption einschließt und die `$orderby`\-Systemabfrageoption nicht einschließt, wird der zurückgegebene Feed nach den Schlüsseleigenschaften in aufsteigender Reihenfolge sortiert.  Das liegt daran, dass die Reihenfolge erforderlich ist, um das richtige Paging von Ergebnissen sicherzustellen.  Hierzu fügt der Datendienst der Abfrage einen Reihenfolgenausdruck hinzu.  Dieses Verhalten tritt auch auf, wenn servergesteuertes Paging im Datendienst aktiviert wird.  Weitere Informationen finden Sie in [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md). Um die Reihenfolge des zurückgegebenen Feeds zu steuern, sollten Sie `$orderby` in den Abfrage\-URI einschließen.  
  
## Siehe auch  
 [Definieren von WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)   
 [WCF Data Services\-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)