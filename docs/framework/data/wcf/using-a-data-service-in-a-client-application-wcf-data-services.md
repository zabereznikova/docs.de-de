---
title: Verwenden eines Datendiensts in einer Clientanwendung (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, getting started
ms.assetid: 90872d0c-e989-4490-b3e9-54afb10d33d4
ms.openlocfilehash: ccf003b915876a30eeb27b39066168fb22950292
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975097"
---
# <a name="using-a-data-service-in-a-client-application-wcf-data-services"></a>Verwenden eines Datendiensts in einer Clientanwendung (WCF Data Services)
Sie können auf einen Dienst zugreifen, der einen Open Data Protocol (odata)-Feed verfügbar macht, indem Sie einen URI an einen Webbrowser bereitstellen. Der URI stellt die Adresse einer Ressource bereit, und Anforderungsnachrichten werden an diese Adressen gesendet, um auf die zugrunde liegenden Daten, die die Ressource darstellt, zuzugreifen oder um diese zu ändern. Der Browser gibt einen HTTP GET-Befehl aus und gibt die angeforderte Ressource als odata-Feed zurück. Weitere Informationen finden Sie unter [zugreifen auf den Dienst über einen Webbrowser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
 Obwohl ein Webbrowser nützlich sein kann, um zu testen, ob ein odata-Dienst die erwarteten Daten zurückgibt, wird in den odata-Produktions Diensten, die es Ihnen ermöglichen, auch Daten zu erstellen, zu aktualisieren und zu löschen, in der Regel über Anwendungscode oder Skriptsprachen auf einer Webseite zugegriffen. Dieses Thema enthält eine Übersicht über den Zugriff auf odata-Feeds über eine Client Anwendung.  
  
## <a name="accessing-and-changing-data-using-rest-semantics"></a>Zugreifen auf und Ändern von Daten mit REST-Semantik  
 Odata gewährleistet die Interoperabilität zwischen Diensten, die odata-Feeds und Anwendungen verfügbar machen, die odata-Feeds nutzen. Anwendungen greifen auf Daten in einem odata-basierten Dienst zu und ändern diese durch das Senden von Anforderungs Nachrichten einer bestimmten http-Aktion und mit einem URI, der eine Entitäts Ressource adressiert, für die die Aktion ausgeführt werden soll. Erforderliche Entitätsdaten werden als speziell codierte Nutzlast im Nachrichtentext angegeben.  
  
### <a name="http-actions"></a>HTTP-Aktionen  
 Odata unterstützt die folgenden HTTP-Aktionen zum Ausführen von CREATE-, Read-, Update-und DELETE-Vorgängen für die Entitäts Daten, die die adressierte Ressource darstellt:  
  
- **HTTP Get** : Dies ist die Standardaktion, wenn auf eine Ressource über einen Browser zugegriffen wird. In der Anforderungsnachricht wird keine Nutzlast angegeben, und es wird eine Antwortmethode mit einer Nutzlast zurückgegeben, die die angeforderten Daten enthält.  
  
- **Http Post** : fügt neue Entitäts Daten in die angegebene Ressource ein. Einzufügende Daten werden in der Nutzlast der Anforderungsnachricht angegeben. Die Nutzlast der Antwortnachricht enthält die Daten für die neu erstellte Entität. Dazu gehören auch alle automatisch generierten Schlüsselwerte. Der Header enthält auch den URI, der die neue Entitätsressource adressiert.  
  
- **HTTP DELETE** : Löscht die Entitäts Daten, die die angegebene Ressource darstellt. Eine Nutzlast ist in der Anforderungs- oder Antwortnachricht nicht vorhanden.  
  
- **Http Put** -ersetzt vorhandene Entitäts Daten bei der angeforderten Ressource durch neue Daten, die in der Nutzlast der Anforderungs Nachricht angegeben werden.  
  
- **Http Merge** : aufgrund der Ineffizienzen beim Ausführen eines Löschvorgangs, gefolgt von einer Einfügung in der Datenquelle, nur um Entitäts Daten zu ändern, führt odata eine neue http-Merge-Aktion ein. Die Nutzlast der Anforderungsnachricht enthält die Eigenschaften, die für die adressierte Entitätsressource geändert werden müssen. Da HTTP Merge nicht in der HTTP-Spezifikation definiert ist, ist möglicherweise eine zusätzliche Verarbeitung erforderlich, um eine HTTP Merge-Anforderung über nicht odata-fähige Server weiterzuleiten.  
  
 Weitere Informationen finden Sie unter [odata: Vorgänge](https://go.microsoft.com/fwlink/?LinkId=185792).  
  
### <a name="payload-formats"></a>Nutzlastformate  
 Für eine HTTP PUT-, HTTP POST- oder HTTP MERGE-Anforderung enthält die Nutzlast einer Anforderungsnachricht die Entitätsdaten, die Sie an den Datendienst senden. Der Inhalt der Nutzlast hängt vom Datenformat der Nachricht ab. Die HTTP-Antworten auf alle Aktionen außer DELETE enthalten auch eine entsprechende Nutzlast. Odata unterstützt die folgenden Nutz Last Formate zum Zugreifen auf und Ändern von Daten mit dem Dienst:  
  
- **Atom** : eine XML-basierte Nachrichten Codierung, die von odata als Erweiterung des Atom Publishing Protocol (AtomPub) definiert wird, um den Datenaustausch über HTTP für Webfeeds, Podcasts, Wikis und XML-basierte Internet Funktionalität zu ermöglichen. Weitere Informationen finden Sie unter [odata: Atom-Format](https://go.microsoft.com/fwlink/?LinkId=185794).  
  
- **JSON** -JavaScript Object Notation (JSON) ist ein schlankes Datenaustauschformat, das auf einer Teilmenge der Programmiersprache JavaScript basiert. Weitere Informationen finden Sie unter [odata: JSON-Format](https://go.microsoft.com/fwlink/?LinkId=185795).  
  
 Das Nachrichtenformat der Nutzlast wird im Header der HTTP-Anforderungsnachricht angefordert. Weitere Informationen finden Sie unter [odata: Vorgänge](https://go.microsoft.com/fwlink/?LinkID=185792).  
  
## <a name="accessing-and-changing-data-using-client-libraries"></a>Zugreifen auf und Ändern von Daten mit Clientbibliotheken  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] umfasst Client Bibliotheken, die es Ihnen ermöglichen, einen odata-Feed von .NET Framework und Silverlight-basierten Client Anwendungen aus leichter zu nutzen. Diese Bibliotheken vereinfachen das Senden und Empfangen von HTTP-Nachrichten. Sie übersetzen außerdem die Nachrichtennutzlast in CLR-Objekte, die Entitätsdaten darstellen. Die Clientbibliotheken enthalten die beiden Kernklassen <xref:System.Data.Services.Client.DataServiceContext> und <xref:System.Data.Services.Client.DataServiceQuery%601>. Diese Klassen ermöglichen es Ihnen, einen Datendienst abzufragen und dann die zurückgegebenen Entitätsdaten als CLR-Objekte zu verarbeiten. Weitere Informationen finden Sie unter [WCF Data Services Client Bibliothek](wcf-data-services-client-library.md) und [WCF Data Services (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95)).  
  
 Sie können das Dialogfeld " **Dienstverweis hinzufügen** " in Visual Studio verwenden, um einen Verweis auf einen Datendienst hinzuzufügen. Dieses Tool fordert die Dienstmetadaten von einem Datendienst an, auf den verwiesen wird, und generiert den <xref:System.Data.Services.Client.DataServiceContext>, der einen Datendienst darstellt, sowie die Clientdatendienstklassen, die Entitäten darstellen. Weitere Informationen finden Sie unter [Erstellen der Datendienst-Client Bibliothek](generating-the-data-service-client-library-wcf-data-services.md).  
  
 Es stehen Programmierbibliotheken zur Verfügung, mit denen Sie einen odata-Feed in anderen Arten von Client Anwendungen nutzen können. Weitere Informationen finden Sie unter [odata SDK](https://go.microsoft.com/fwlink/?LinkId=185796).  
  
## <a name="see-also"></a>Siehe auch

- [Zugreifen auf Datendienstressourcen](accessing-data-service-resources-wcf-data-services.md)
- [Schnellstart](quickstart-wcf-data-services.md)
