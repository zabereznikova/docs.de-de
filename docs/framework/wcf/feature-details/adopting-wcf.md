---
title: Übernehmen von Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
ms.openlocfilehash: 53f51c6a93d4768d3aa158d44cb7d20f945393f5
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964254"
---
# <a name="adopting-windows-communication-foundation"></a>Übernehmen von Windows Communication Foundation

Sie können für die neue Entwicklung Windows Communication Foundation (WCF) verwenden, während Sie weiterhin vorhandene Anwendungen verwalten, die mit ASP.net entwickelt wurden. Da WCF für die Kommunikation mit Anwendungen, die mit dem .NET Framework in jedem Szenario erstellt wurden, die geeignetste Wahl sein soll, kann es als Standard Tool dienen, um eine Vielzahl von Software Kommunikationsproblemen auf eine Weise zu lösen, die ASP.net gar.

Neue WCF-Anwendungen können auf denselben Computern wie vorhandene ASP.NET-Webdienste bereitgestellt werden. Wenn die vorhandenen ASP.NET-Webdienste eine Version des .NET Framework vor Version 2,0 verwenden, können Sie das Registrierungs Tool "ASP.NET IIS" verwenden, um die .NET Framework 2,0 selektiv für IIS-Anwendungen bereitzustellen, in denen neue WCF-Anwendungen gehostet werden sollen. Dieses Tool ist unter [ASP.NET IIS Registration Tool (Aspnet_regiis. exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/k6h9cz8h(v=vs.90))dokumentiert und verfügt über eine Benutzeroberfläche, die in die IIS 6,0-Verwaltungskonsole integriert ist.

WCF kann zum Hinzufügen neuer Funktionen zu vorhandenen ASP.NET-Webdiensten verwendet werden, indem WCF-Dienste, die für die Verwendung im ASP.NET-Kompatibilitätsmodus konfiguriert sind, zu vorhandenen ASP.NET-Webdienst Anwendungen in IIS hinzu Aufgrund des ASP.NET-Kompatibilitätsmodus kann der Code für die neuen WCF-Dienste auf die gleichen Anwendungs Zustandsinformationen wie der bereits vorhandene ASP.NET-Code zugreifen und diese aktualisieren, indem die <xref:System.Web.HttpContext>-Klasse verwendet wird. Außerdem können sich die Anwendungen die gleichen Klassenbibliotheken teilen.

WCF-Clients können ASP.NET-Webdienste verwenden. WCF-Dienste, die mit dem-<xref:System.ServiceModel.BasicHttpBinding> konfiguriert sind, können von ASP.NET-Webdienst Clients verwendet werden. ASP.NET Webdienste können gemeinsam mit WCF-Anwendungen verwendet werden, und WCF kann sogar zum Hinzufügen von Features zu vorhandenen ASP.NET-Webdiensten verwendet werden. Wenn Sie alle diese Methoden verwenden können, um WCF-und ASP.NET-Webdienste zu verwenden, sollten Sie ASP.NET-Webdienste nur zu WCF migrieren, wenn Sie Funktionen benötigen, die von WCF und nicht von ASP.NET-Webdiensten bereitgestellt werden.

Auch in den wenigen Fällen, in denen es erforderlich ist, ist die Migration von Code von einer Technologie zu einer anderen selten der richtige Ansatz. Der Grund der Übernahme der neuen Technologie ist die Erfüllung neuer Anforderungen, die von der früheren Technologie nicht erfüllt werden können; in diesem Fall ist die richtige Vorgehensweise, eine neue Lösung zu entwerfen, die den neuen, erweiterten Satz an Anforderungen erfüllt. Das neue Design profitiert von Ihren Erfahrungen mit dem vorhandenen System und von den Einsichten, die seit dem Design des neuen Systems gewonnen wurden. Das neue Design kann außerdem die Fähigkeiten der neuen Technologien komplett ausreizen, anstatt das alte Design auf der neuen Plattform zu reproduzieren. Indem Schlüsselelemente des neuen Designs zu Prototypen gemacht werden, wird es einfacher, Code aus dem vorhandenen System innerhalb des neuen Systems wiederzuverwerten.

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Abrufen von Metadaten und Implementieren eines kompatiblen Diensts](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
