---
title: Verwenden eines Datendiensts in einer Clientanwendung (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, getting started
ms.assetid: 90872d0c-e989-4490-b3e9-54afb10d33d4
ms.openlocfilehash: 050c1a67a367a6dd5175c535fe89fb0010ae8cbc
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790285"
---
# <a name="using-a-data-service-in-a-client-application-wcf-data-services"></a>Verwenden eines Datendiensts in einer Clientanwendung (WCF Data Services)
Sie können auf einen Dienst zugreifen, der [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] einen-Feed verfügbar macht, indem Sie einen URI für einen Webbrowser bereitstellen. Der URI stellt die Adresse einer Ressource bereit, und Anforderungsnachrichten werden an diese Adressen gesendet, um auf die zugrunde liegenden Daten, die die Ressource darstellt, zuzugreifen oder um diese zu ändern. Der Browser gibt einen HTTP GET-Befehl aus und gibt die angeforderte Ressource als [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feed zurück. Weitere Informationen finden Sie unter [zugreifen auf den Dienst über einen Webbrowser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
 Zwar kann ein Webbrowser nützlich sein kann, um zu testen, ob ein [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Dienst die erwarteten Daten zurückgibt. Allerdings wird auf [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Produktionsdienste, die zusätzlich das Erstellen, Aktualisieren und Löschen von Daten ermöglichen, in der Regel mithilfe von Anwendungscode oder Skriptsprachen einer Webseite zugegriffen. Dieses Thema enthält eine Übersicht über den Zugriff [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] auf Feeds von einer Client Anwendung aus.  
  
## <a name="accessing-and-changing-data-using-rest-semantics"></a>Zugreifen auf und Ändern von Daten mit REST-Semantik  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]unterstützt die Interoperabilität zwischen Diensten, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] die Feeds und Anwendungen verfügbar [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] machen, die Feeds nutzen. Anwendungen greifen auf Daten in einem [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-basierten Dienst zu und ändern Sie durch Senden von Anforderungs Nachrichten einer bestimmten http-Aktion und mit einem URI, der eine Entitäts Ressource adressiert, für die die Aktion ausgeführt werden soll. Erforderliche Entitätsdaten werden als speziell codierte Nutzlast im Nachrichtentext angegeben.  
  
### <a name="http-actions"></a>HTTP-Aktionen  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] unterstützt die folgenden HTTP-Aktionen zum Erstellen, Lesen, Aktualisieren und Löschen von Entitätsdaten, die die adressierte Ressource darstellt:  
  
- **HTTP Get** : Dies ist die Standardaktion, wenn auf eine Ressource über einen Browser zugegriffen wird. In der Anforderungsnachricht wird keine Nutzlast angegeben, und es wird eine Antwortmethode mit einer Nutzlast zurückgegeben, die die angeforderten Daten enthält.  
  
- **Http Post** : fügt neue Entitäts Daten in die angegebene Ressource ein. Einzufügende Daten werden in der Nutzlast der Anforderungsnachricht angegeben. Die Nutzlast der Antwortnachricht enthält die Daten für die neu erstellte Entität. Dazu gehören auch alle automatisch generierten Schlüsselwerte. Der Header enthält auch den URI, der die neue Entitätsressource adressiert.  
  
- **HTTP DELETE** : Löscht die Entitäts Daten, die die angegebene Ressource darstellt. Eine Nutzlast ist in der Anforderungs- oder Antwortnachricht nicht vorhanden.  
  
- **Http Put** -ersetzt vorhandene Entitäts Daten bei der angeforderten Ressource durch neue Daten, die in der Nutzlast der Anforderungs Nachricht angegeben werden.  
  
- **Http Merge** : aufgrund der Ineffizienzen beim Ausführen eines Löschvorgangs, gefolgt von einer Einfügung in der Datenquelle, nur [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] um Entitäts Daten zu ändern, führt eine neue http-Merge-Aktion ein. Die Nutzlast der Anforderungsnachricht enthält die Eigenschaften, die für die adressierte Entitätsressource geändert werden müssen. Da HTTP MERGE nicht in der HTTP-Spezifikation definiert ist, ist möglicherweise eine zusätzliche Verarbeitung zum Weiterleiten einer HTTP MERGE-Anforderung durch Server erforderlich, die [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] nicht unterstützen.  
  
 Weitere Informationen finden [Sie unter odata: Vorgänge](https://go.microsoft.com/fwlink/?LinkId=185792).  
  
### <a name="payload-formats"></a>Nutzlastformate  
 Für eine HTTP PUT-, HTTP POST- oder HTTP MERGE-Anforderung enthält die Nutzlast einer Anforderungsnachricht die Entitätsdaten, die Sie an den Datendienst senden. Der Inhalt der Nutzlast hängt vom Datenformat der Nachricht ab. Die HTTP-Antworten auf alle Aktionen außer DELETE enthalten auch eine entsprechende Nutzlast. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]unterstützt die folgenden Nutz Last Formate zum Zugreifen auf und Ändern von Daten mit dem Dienst:  
  
- **Atom** : eine XML-basierte Nachrichten Codierung, die von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] als Erweiterung des Atom Publishing Protocol (AtomPub) definiert wird, um den Datenaustausch über HTTP für Webfeeds, Podcasts, Wikis und XML-basierte Internet Funktionalität zu ermöglichen. Weitere Informationen finden [Sie unter odata: Atom-](https://go.microsoft.com/fwlink/?LinkId=185794)Format.  
  
- **JSON** -JavaScript Object Notation (JSON) ist ein schlankes Datenaustauschformat, das auf einer Teilmenge der Programmiersprache JavaScript basiert. Weitere Informationen finden [Sie unter odata: JSON-](https://go.microsoft.com/fwlink/?LinkId=185795)Format.  
  
 Das Nachrichtenformat der Nutzlast wird im Header der HTTP-Anforderungsnachricht angefordert. Weitere Informationen finden [Sie unter odata: Vorgänge](https://go.microsoft.com/fwlink/?LinkID=185792).  
  
## <a name="accessing-and-changing-data-using-client-libraries"></a>Zugreifen auf und Ändern von Daten mit Clientbibliotheken  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]umfasst Client Bibliotheken, die es Ihnen ermöglichen, einen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Feed von .NET Framework und Silverlight-basierten Client Anwendungen zu nutzen. Diese Bibliotheken vereinfachen das Senden und Empfangen von HTTP-Nachrichten. Sie übersetzen außerdem die Nachrichtennutzlast in CLR-Objekte, die Entitätsdaten darstellen. Die Clientbibliotheken enthalten die beiden Kernklassen <xref:System.Data.Services.Client.DataServiceContext> und <xref:System.Data.Services.Client.DataServiceQuery%601>. Diese Klassen ermöglichen es Ihnen, einen Datendienst abzufragen und dann die zurückgegebenen Entitätsdaten als CLR-Objekte zu verarbeiten. Weitere Informationen finden Sie unter [WCF Data Services Client Bibliothek](wcf-data-services-client-library.md) und [WCF Data Services (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95)).  
  
 Sie können das Dialogfeld " **Dienstverweis hinzufügen** " in Visual Studio verwenden, um einen Verweis auf einen Datendienst hinzuzufügen. Dieses Tool fordert die Dienstmetadaten von einem Datendienst an, auf den verwiesen wird, und generiert den <xref:System.Data.Services.Client.DataServiceContext>, der einen Datendienst darstellt, sowie die Clientdatendienstklassen, die Entitäten darstellen. Weitere Informationen finden Sie unter [Erstellen der Datendienst-Client Bibliothek](generating-the-data-service-client-library-wcf-data-services.md).  
  
 Es stehen Programmierbibliotheken zur Verfügung, mit denen Sie einen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] -Feed in anderen Arten von Client Anwendungen nutzen können. Weitere Informationen finden Sie unter [odata SDK](https://go.microsoft.com/fwlink/?LinkId=185796).  
  
## <a name="see-also"></a>Siehe auch

- [Zugreifen auf Datendienstressourcen](accessing-data-service-resources-wcf-data-services.md)
- [Schnellstart](quickstart-wcf-data-services.md)
