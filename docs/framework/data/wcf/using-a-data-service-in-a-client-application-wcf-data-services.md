---
title: "Verwenden eines Datendiensts in einer Clientanwendung (WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, Clientbibliothek"
  - "WCF Data Services, Erste Schritte"
ms.assetid: 90872d0c-e989-4490-b3e9-54afb10d33d4
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Verwenden eines Datendiensts in einer Clientanwendung (WCF Data Services)
Sie können auf einen Dienst, der einen [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]\-Feed verfügbar macht, zugreifen, indem Sie im Webbrowser einen URI angeben.  Der URI stellt die Adresse einer Ressource bereit, und Anforderungsnachrichten werden an diese Adressen gesendet, um auf die zugrunde liegenden Daten, die die Ressource darstellt, zuzugreifen oder um diese zu ändern.  Der Browser gibt einen HTTP GET\-Befehl aus und gibt die angeforderte Ressource als [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feed zurück.  Weitere Informationen finden Sie unter [Zugreifen auf den Dienst in einem Webbrowser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
 Zwar kann ein Webbrowser nützlich sein kann, um zu testen, ob ein [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Dienst die erwarteten Daten zurückgibt. Allerdings wird auf [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Produktionsdienste, die zusätzlich das Erstellen, Aktualisieren und Löschen von Daten ermöglichen, in der Regel mithilfe von Anwendungscode oder Skriptsprachen einer Webseite zugegriffen.  Dieses Thema bietet eine Übersicht über den Zugriff auf [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feeds über eine Clientanwendung.  
  
## Zugreifen auf und Ändern von Daten mit REST\-Semantik  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] unterstützt die Interoperabilität zwischen Diensten, die [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feeds bzw. Anwendungen verfügbar machen, die [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feeds verarbeiten. Anwendungen greifen auf Daten in einem auf [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] basierenden Datendienst zu und ändern diese durch Senden von Anforderungsnachrichten einer bestimmten HTTP\-Aktion und mit einem URI, der eine Entitätsressource adressiert, für die die Aktion ausgeführt werden soll.  Erforderliche Entitätsdaten werden als speziell codierte Nutzlast im Nachrichtentext angegeben.  
  
### HTTP\-Aktionen  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] unterstützt die folgenden HTTP\-Aktionen zum Erstellen, Lesen, Aktualisieren und Löschen von Entitätsdaten, die die adressierte Ressource darstellt:  
  
-   **HTTP GET** \- Die Standardaktion, wenn auf eine Ressource von einem Browser aus zugegriffen wird.  In der Anforderungsnachricht wird keine Nutzlast angegeben, und es wird eine Antwortmethode mit einer Nutzlast zurückgegeben, die die angeforderten Daten enthält.  
  
-   **HTTP POST** – Fügt neue Entitätsdaten in die angegebene Ressource ein.  Einzufügende Daten werden in der Nutzlast der Anforderungsnachricht angegeben.  Die Nutzlast der Antwortnachricht enthält die Daten für die neu erstellte Entität.  Dazu gehören auch alle automatisch generierten Schlüsselwerte.  Der Header enthält auch den URI, der die neue Entitätsressource adressiert.  
  
-   **HTTP DELETE** – Löscht die Entitätsdaten, die durch die angegebene Ressource dargestellt werden.  Eine Nutzlast ist in der Anforderungs\- oder Antwortnachricht nicht vorhanden.  
  
-   **HTTP PUT** – Ersetzt in der angeforderten Ressource vorhandene Entitätsdaten durch neue Daten, die in der Nutzlast der Anforderungsmeldung zur Verfügung gestellt werden.  
  
-   **HTTP MERGE** – Da es ineffizient ist, in der Datenquelle einen Löschvorgang gefolgt von einem Einfügevorgang auszuführen, nur um Entitätsdaten zu ändern, wird von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] eine neue HTTP MERGE\-Aktion eingeführt.  Die Nutzlast der Anforderungsnachricht enthält die Eigenschaften, die für die adressierte Entitätsressource geändert werden müssen.  Da HTTP MERGE nicht in der HTTP\-Spezifikation definiert ist, ist möglicherweise eine zusätzliche Verarbeitung zum Weiterleiten einer HTTP MERGE\-Anforderung durch Server erforderlich, die [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] nicht unterstützen.  
  
 Weitere Informationen finden Sie unter [OData: Vorgänge](http://go.microsoft.com/fwlink/?LinkId=185792).  
  
### Nutzlastformate  
 Für eine HTTP PUT\-, HTTP POST\- oder HTTP MERGE\-Anforderung enthält die Nutzlast einer Anforderungsnachricht die Entitätsdaten, die Sie an den Datendienst senden.  Der Inhalt der Nutzlast hängt vom Datenformat der Nachricht ab.  Die HTTP\-Antworten auf alle Aktionen außer DELETE enthalten auch eine entsprechende Nutzlast.  [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] unterstützt die folgenden Nutzlastformate zum Zugreifen auf und Ändern von Daten mit dem Dienst:  
  
-   **Atom** – Eine XML\-basierte Nachrichtencodierung, die von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] als Erweiterung von Atom Publishing Protocol \(AtomPub\) definiert wird, um für Webfeeds, Podcasts, Wikis und XML\-basierte Internetfunktionalität den Datenaustausch über HTTP zu ermöglichen.  Weitere Informationen finden Sie unter [OData: Atom\-Format](http://go.microsoft.com/fwlink/?LinkId=185794).  
  
-   **JSON** – JSON \(JavaScript Object Notation\) ist ein einfaches Datenaustauschformat, das auf einem Teil der Programmiersprache JavaScript basiert.  Weitere Informationen finden Sie unter [OData: JSON\-Format](http://go.microsoft.com/fwlink/?LinkId=185795).  
  
 Das Nachrichtenformat der Nutzlast wird im Header der HTTP\-Anforderungsnachricht angefordert.  Weitere Informationen finden Sie unter [OData: Vorgänge](http://go.microsoft.com/fwlink/?LinkID=185792).  
  
## Zugreifen auf und Ändern von Daten mit Clientbibliotheken  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] enthält Clientbibliotheken, die Ihnen das Verwenden eines [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feeds aus .NET Framework\- und Silverlight\-basierten Clientanwendungen erleichtern.  Diese Bibliotheken vereinfachen das Senden und Empfangen von HTTP\-Nachrichten.  Sie übersetzen außerdem die Nachrichtennutzlast in CLR\-Objekte, die Entitätsdaten darstellen.  Die Clientbibliotheken enthalten die beiden Kernklassen <xref:System.Data.Services.Client.DataServiceContext> und <xref:System.Data.Services.Client.DataServiceQuery%601>.  Diese Klassen ermöglichen es Ihnen, einen Datendienst abzufragen und dann die zurückgegebenen Entitätsdaten als CLR\-Objekte zu verarbeiten.  Weitere Informationen finden Sie unter [WCF Data Services\-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md) und [WCF Data Services \(Silverlight\)](http://msdn.microsoft.com/de-de/c0cd9f4b-1372-48e4-9935-c8421239da30).  
  
 Sie können über das Dialogfeld **Dienstverweis hinzufügen** in Visual Studio einem Datendienst einen Verweis hinzufügen.  Dieses Tool fordert die Dienstmetadaten von einem Datendienst an, auf den verwiesen wird, und generiert den <xref:System.Data.Services.Client.DataServiceContext>, der einen Datendienst darstellt, sowie die Clientdatendienstklassen, die Entitäten darstellen.  Weitere Informationen finden Sie unter [Generieren der Datendienst\-Clientbibliothek](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).  
  
 Es stehen Programmierbibliotheken zur Verfügung, mit denen Sie einen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feed in anderen Arten von Clientanwendungen verwenden können.  Weitere Informationen finden Sie unter [OData SDK](http://go.microsoft.com/fwlink/?LinkId=185796).  
  
## Siehe auch  
 [Zugreifen auf Datendienstressourcen](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)   
 [Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)