---
title: Verwenden eines Datendiensts in einer Clientanwendung (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, getting started
ms.assetid: 90872d0c-e989-4490-b3e9-54afb10d33d4
ms.openlocfilehash: b25489de9a64ba4f1938e4d52c1cc677a218495b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365292"
---
# <a name="using-a-data-service-in-a-client-application-wcf-data-services"></a>Verwenden eines Datendiensts in einer Clientanwendung (WCF Data Services)
Sie erreichen einen Dienst, der verfügbar macht eine [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed von einem Webbrowser einen URI angeben. Der URI stellt die Adresse einer Ressource bereit, und Anforderungsnachrichten werden an diese Adressen gesendet, um auf die zugrunde liegenden Daten, die die Ressource darstellt, zuzugreifen oder um diese zu ändern. Der Browser gibt einen HTTP GET-Befehl aus und gibt die angeforderte Ressource als [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feed zurück. Weitere Informationen finden Sie unter [Zugriff auf den Dienst über einen Webbrowser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
 Zwar kann ein Webbrowser nützlich sein kann, um zu testen, ob ein [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Dienst die erwarteten Daten zurückgibt. Allerdings wird auf [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Produktionsdienste, die zusätzlich das Erstellen, Aktualisieren und Löschen von Daten ermöglichen, in der Regel mithilfe von Anwendungscode oder Skriptsprachen einer Webseite zugegriffen. Dieses Thema bietet eine Übersicht über Zugriff auf [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds aus einer Clientanwendung.  
  
## <a name="accessing-and-changing-data-using-rest-semantics"></a>Zugreifen auf und Ändern von Daten mit REST-Semantik  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] unterstützt die Gewährleistung der Interoperabilität zwischen Diensten, die verfügbar machen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Feeds und Anwendungen, die nutzen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds. Anwendungen Zugriff auf und Ändern von Daten in eine [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-basierten Dienst durch Senden von Anforderungsnachrichten einer bestimmten HTTP-Aktion und mit einem URI, der eine Entitätsressource adressiert, für die die Aktion ausgeführt werden soll. Erforderliche Entitätsdaten werden als speziell codierte Nutzlast im Nachrichtentext angegeben.  
  
### <a name="http-actions"></a>HTTP-Aktionen  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] unterstützt die folgenden HTTP-Aktionen zum Erstellen, Lesen, Aktualisieren und Löschen von Entitätsdaten, die die adressierte Ressource darstellt:  
  
-   **HTTP GET** -Dies ist die Standardaktion, wenn eine Ressource über einen Browser zugegriffen wird. In der Anforderungsnachricht wird keine Nutzlast angegeben, und es wird eine Antwortmethode mit einer Nutzlast zurückgegeben, die die angeforderten Daten enthält.  
  
-   **HTTP POST** -fügt neue Entitätsdaten in die angegebene Ressource. Einzufügende Daten werden in der Nutzlast der Anforderungsnachricht angegeben. Die Nutzlast der Antwortnachricht enthält die Daten für die neu erstellte Entität. Dazu gehören auch alle automatisch generierten Schlüsselwerte. Der Header enthält auch den URI, der die neue Entitätsressource adressiert.  
  
-   **HTTP DELETE** -löscht die Entitätsdaten, die die angegebene Ressource darstellt. Eine Nutzlast ist in der Anforderungs- oder Antwortnachricht nicht vorhanden.  
  
-   **HTTP PUT** – ersetzt vorhandene Entitätsdaten in der angeforderten Ressource mit neuen Daten, die in der Nutzlast der Anforderungsnachricht angegeben werden.  
  
-   **HTTP MERGE** – da es ineffizient auszuführen, einen Löschvorgang gefolgt von einer INSERT-Anweisung in der Datenquelle nur um Entitätsdaten zu ändern [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] eine neue HTTP MERGE-Aktion eingeführt. Die Nutzlast der Anforderungsnachricht enthält die Eigenschaften, die für die adressierte Entitätsressource geändert werden müssen. Da HTTP MERGE nicht in der HTTP-Spezifikation definiert ist, ist möglicherweise eine zusätzliche Verarbeitung zum Weiterleiten einer HTTP MERGE-Anforderung durch Server erforderlich, die [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] nicht unterstützen.  
  
 Weitere Informationen finden Sie unter [OData: Vorgänge](http://go.microsoft.com/fwlink/?LinkId=185792).  
  
### <a name="payload-formats"></a>Nutzlastformate  
 Für eine HTTP PUT-, HTTP POST- oder HTTP MERGE-Anforderung enthält die Nutzlast einer Anforderungsnachricht die Entitätsdaten, die Sie an den Datendienst senden. Der Inhalt der Nutzlast hängt vom Datenformat der Nachricht ab. Die HTTP-Antworten auf alle Aktionen außer DELETE enthalten auch eine entsprechende Nutzlast. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] unterstützt die folgenden Nutzlastformate zum Zugreifen auf und Ändern von Daten mit dem Dienst:  
  
-   **Atom** -eine XML-basierte nachrichtencodierung durch definierten [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] als Erweiterung der Atom Publishing Protocol (AtomPub) Datenaustausch über HTTP zu ermöglichen, für Webfeeds, Podcasts, Wikis und XML-basierte Internetfunktionalität. Weitere Informationen finden Sie unter [OData: Atom-Format](http://go.microsoft.com/fwlink/?LinkId=185794).  
  
-   **JSON** -JavaScript Object Notation (JSON) ist ein einfaches Datenaustauschformat, das auf eine Teilmenge der Programmiersprache JavaScript basiert. Weitere Informationen finden Sie unter [OData: JSON-Format](http://go.microsoft.com/fwlink/?LinkId=185795).  
  
 Das Nachrichtenformat der Nutzlast wird im Header der HTTP-Anforderungsnachricht angefordert. Weitere Informationen finden Sie unter [OData: Vorgänge](http://go.microsoft.com/fwlink/?LinkID=185792).  
  
## <a name="accessing-and-changing-data-using-client-libraries"></a>Zugreifen auf und Ändern von Daten mit Clientbibliotheken  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] enthält Clientbibliotheken, die Ihnen ermöglichen, leichter nutzen eine [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Feeds aus .NET Framework und Silverlight-basierte Clientanwendungen. Diese Bibliotheken vereinfachen das Senden und Empfangen von HTTP-Nachrichten. Sie übersetzen außerdem die Nachrichtennutzlast in CLR-Objekte, die Entitätsdaten darstellen. Die Clientbibliotheken enthalten die beiden Kernklassen <xref:System.Data.Services.Client.DataServiceContext> und <xref:System.Data.Services.Client.DataServiceQuery%601>. Diese Klassen ermöglichen es Ihnen, einen Datendienst abzufragen und dann die zurückgegebenen Entitätsdaten als CLR-Objekte zu verarbeiten. Weitere Informationen finden Sie unter [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md) und [WCF Data Services (Silverlight)](http://msdn.microsoft.com/library/c0cd9f4b-1372-48e4-9935-c8421239da30).  
  
 Sie können die **Hinzufügen eines Dienstverweises** Dialogfeld in Visual Studio einen Verweis an einen Datendienst hinzufügen. Dieses Tool fordert die Dienstmetadaten von einem Datendienst an, auf den verwiesen wird, und generiert den <xref:System.Data.Services.Client.DataServiceContext>, der einen Datendienst darstellt, sowie die Clientdatendienstklassen, die Entitäten darstellen. Weitere Informationen finden Sie unter [Generieren der Datendienst-Clientbibliothek](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).  
  
 Es stehen Programmierbibliotheken zur Verfügung, die Sie verwenden können, verwenden eine [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in anderen Arten von Clientanwendungen. Weitere Informationen finden Sie unter der [OData SDK](http://go.microsoft.com/fwlink/?LinkId=185796).  
  
## <a name="see-also"></a>Siehe auch  
 [Zugreifen auf Datendienstressourcen](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)  
 [Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
