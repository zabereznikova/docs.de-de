---
title: Übernehmen von Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
ms.openlocfilehash: bcd6543e6cd47dc723b308acebec6f492fa14fb1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="adopting-windows-communication-foundation"></a>Übernehmen von Windows Communication Foundation
Sie können auswählen, verwenden Sie Windows Communication Foundation (WCF) für Neuentwicklungen, während Sie den Vorgang fortsetzen, vorhandene Anwendungen zu verwalten über ASP.NET entwickelt wurden. Da WCF die passende Wahl für die Erleichterung der Kommunikation mit Clientanwendungen mit .NET Framework in allen Szenarien erstellt werden soll, kann als ein Standardtool zur Lösung von einer Vielzahl von softwarekommunikationsprobleme auf eine Weise, dass ASP.NET dienen ist nicht möglich.  
  
 Neue WCF-Anwendungen können auf den gleichen Computern wie vorhandene ASP.NET-Webdienste bereitgestellt werden. Wenn die vorhandenen ASP.NET-Webdienste eine Version von .NET Framework vor Version 2.0 verwenden, können Sie das ASP.NET IIS Registration-Tool verwenden, selektiv .NET Framework 2.0 auf IIS-Anwendungen bereitgestellt und in der neue WCF-Anwendungen gehostet werden. Dieses Tool finden Sie unter [ASP.NET IIS-Registrierungstool (Aspnet_regiis.exe)](http://go.microsoft.com/fwlink/?LinkId=94687), und verfügt über eine Benutzeroberfläche, die in der IIS 6.0-Verwaltungskonsole integriert.  
  
 WCF kann verwendet werden, um vorhandenen ASP.NET-Webdiensten neue Funktionen hinzugefügt, durch Hinzufügen von WCF-Diensten, die Ausführung im ASP.NET-Kompatibilitätsmodus vorhandener ASP.NET-Webdienstanwendungen in IIS konfiguriert werden. Aufgrund der ASP.NET-Kompatibilitätsmodus, der Code für die neuen WCF-Dienste kann zugreifen und diese aktualisieren die gleichen anwendungsstatusinformationen wie der zuvor vorhandene ASP.NET-Code mithilfe der <xref:System.Web.HttpContext> Klasse. Außerdem können sich die Anwendungen die gleichen Klassenbibliotheken teilen.  
  
 WCF-Clients können ASP.NET-Webdienste benutzen. WCF-Dienste, die mit konfiguriert werden die <xref:System.ServiceModel.BasicHttpBinding> können von ASP.NET-Webdienstclients verwendet werden. ASP.NET-Webdienste können zusammen mit WCF-Anwendungen vorhanden sein, und WCF kann sogar benutzt werden, um vorhandenen ASP.NET-Webdiensten Funktionen hinzuzufügen. Wenn alle der folgenden Weisen in denen WCF und ASP.NET Web Services zusammen verwendet werden können, sollten Sie ASP.NET-Webdiensten zu WCF migrieren, nur dann, wenn Sie Funktionen benötigen, die von WCF und nicht von ASP.NET Web-Dienste bereitgestellt werden.  
  
 Selbst in den wenigen Fällen, in denen dies notwendig ist, sollten Sie sich darüber im Klaren sein, dass die Migration von Code von einer Technologie auf eine andere selten der richtige Ansatz ist. Der Grund der Übernahme der neuen Technologie ist die Erfüllung neuer Anforderungen, die von der früheren Technologie nicht erfüllt werden können; in diesem Fall ist die richtige Vorgehensweise, eine neue Lösung zu entwerfen, die den neuen, erweiterten Satz an Anforderungen erfüllt. Das neue Design profitiert von Ihren Erfahrungen mit dem vorhandenen System und von den Einsichten, die seit dem Design des neuen Systems gewonnen wurden. Das neue Design kann außerdem die Fähigkeiten der neuen Technologien komplett ausreizen, anstatt das alte Design auf der neuen Plattform zu reproduzieren. Indem Schlüsselelemente des neuen Designs zu Prototypen gemacht werden, wird es einfacher, Code aus dem vorhandenen System innerhalb des neuen Systems wiederzuverwerten.  
  
 Für die wenigen Fällen Portieren von ASP.NET-Webdiensten zu WCF ist die richtige Lösung ist, enthält der folgende Abschnitt hilfreiche Informationen zur Vorgehensweise. Er gibt Ratschläge zum Migrieren von Diensten und zum Migrieren von Clients.  
  
 Eine vollständige Analyse zum Migrieren von vorhandenen ASP.NET-Webdiensten zu WCF finden Sie unter [ASP.NET-Webdienste und Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkID=71761). In diesem Abschnitt wird beschrieben, wie einen kompatiblen WCF-Dienst aus den Metadaten für ASP.NET-Webdiensts implementiert und wie ASP.NET Web-Dienst und Client-Code zu WCF migrieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Abrufen von Metadaten und Implementieren eines kompatiblen Diensts](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)  
 [Vorgehensweise: Migrieren von ASP.NET-Webdienstcode zu Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)  
 [Vorgehensweise: Migrieren von ASP.NET-Webdienst-Clientcode zu Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
