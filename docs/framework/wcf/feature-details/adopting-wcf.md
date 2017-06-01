---
title: "&#220;bernehmen von Windows Communication Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# &#220;bernehmen von Windows Communication Foundation
Sie können sich für den Einsatz von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] für eine Neuentwicklung entscheiden, während Sie Ihre vorhandenen Anwendungen, die über ASP.NET entwickelt wurden, weiterhin pflegen.Da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] darauf ausgerichtet ist, in jedem Szenario die passende Wahl für eine Erleichterung der Kommunikation mit Anwendungen, die mit .NET Framework erstellt wurden, darzustellen, kann es auch als eine Art Standardtool für das Lösen vieler verschiedener Softwarekommunikationsprobleme dienen, wie es ASP.NET nicht könnte.  
  
 Neue [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendungen können auf den gleichen Computern wie vorhandene ASP.NET\-Webdienste bereitgestellt werden.Wenn die vorhandenen ASP.NET\-Webdienste eine Version von .NET Framework vor Version 2.0 verwenden, setzen Sie das ASP.NET IIS Registration Tool ein, um wahlweise das .NET Framework 2.0 auf IIS\-Anwendungen einzusetzen, in denen die neuen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendungen gehostet werden.Das Tool wird unter [ASP.NET IIS Registration Tool \(Aspnet\_regiis.exe\)](http://go.microsoft.com/fwlink/?LinkId=94687) \(möglicherweise in englischer Sprache\) dokumentiert und besitzt eine Benutzeroberfläche, die in die IIS 6.0\-Managementkonsole integriert ist.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kann genutzt werden, um vorhandenen ASP.NET\-Webdiensten neue Funktionen hinzuzufügen, indem in IIS vorhandene ASP.NET\-Webdienstanwendungen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensten hinzugefügt werden, die für eine Ausführung im ASP.NET\-Kompatibilitätsmodus konfiguriert sind.Aufgrund des ASP.NET\-Kompatibilitätsmodus kann der Code für die neuen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienste auf die gleichen Anwendungsstatusinformationen wie der zuvor vorhandene ASP.NET\-Code zugreifen und sie aktualisieren; für beides wird die Klasse <xref:System.Web.HttpContext> verwendet.Außerdem können sich die Anwendungen die gleichen Klassenbibliotheken teilen.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clients können ASP.NET Webdienste benutzen.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienste, die über <xref:System.ServiceModel.BasicHttpBinding> konfiguriert sind, können von ASP.NET\-Webdienstclients verwendet werden.ASP.NET\-Webdienste können zusammen mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendungen existieren, und [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kann sogar benutzt werden, um vorhandenen ASP.NET\-Webdiensten Funktionen hinzuzufügen.Unter Berücksichtigung all dieser Möglichkeiten, wie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] und ASP.NET\-Webdienste zusammen eingesetzt werden können, sollten Sie nur von ASP.NET\-Webdiensten auf [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] migrieren, wenn Sie Funktionen benötigen, die nur von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] und nicht von ASP.NET\-Webdiensten geboten werden.  
  
 Selbst in den wenigen Fällen, in denen dies notwendig ist, sollten Sie sich darüber im Klaren sein, dass die Migration von Code von einer Technologie auf eine andere selten der richtige Ansatz ist.Der Grund der Übernahme der neuen Technologie ist die Erfüllung neuer Anforderungen, die von der früheren Technologie nicht erfüllt werden können; in diesem Fall ist die richtige Vorgehensweise, eine neue Lösung zu entwerfen, die den neuen, erweiterten Satz an Anforderungen erfüllt.Das neue Design profitiert von Ihren Erfahrungen mit dem vorhandenen System und von den Einsichten, die seit dem Design des neuen Systems gewonnen wurden.Das neue Design kann außerdem die Fähigkeiten der neuen Technologien komplett ausreizen, anstatt das alte Design auf der neuen Plattform zu reproduzieren.Indem Schlüsselelemente des neuen Designs zu Prototypen gemacht werden, wird es einfacher, Code aus dem vorhandenen System innerhalb des neuen Systems wiederzuverwerten.  
  
 In den wenigen Fällen, in denen eine Portierung von ASP.NET\-Webdiensten nach [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die richtige Lösung ist, bietet der folgende Abschnitt Hilfe dazu, wie man fortfahren sollte.Er gibt Ratschläge zum Migrieren von Diensten und zum Migrieren von Clients.  
  
 Eine komplette Analyse der Migration von vorhandenen ASP.NET\-Webdiensten nach WCF finden Sie unter [ASP.NET Web Services und die Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkID=71761) \(möglicherweise in englischer Sprache\).Dieser Abschnitt beschreibt, wie man einen kompatiblen WCF\-Dienst aus den Metadaten des ASP.NET\-Webdiensts implementiert und wie ASP.NET\-Webdienst\- und Clientcode nach [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] migriert werden.  
  
## Siehe auch  
 [Vorgehensweise: Abrufen von Metadaten und Implementieren eines kompatiblen Diensts](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)   
 [Vorgehensweise: Migrieren von ASP.NET\-Webdienstcode zu Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)   
 [Vorgehensweise: Migrieren von ASP.NET\-Webdienstcode zu Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)