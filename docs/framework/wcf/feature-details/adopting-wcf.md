---
title: Übernehmen von Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
ms.openlocfilehash: a31bd5382e67565bd54272c5c7f400eacd5297d6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576537"
---
# <a name="adopt-windows-communication-foundation"></a>Windows Communication Foundation übernehmen

Sie können Windows Communication Foundation (WCF) für die neue Entwicklung verwenden und dabei weiterhin vorhandene Anwendungen verwalten, die mit ASP.net entwickelt wurden. Da WCF die geeignetste Wahl ist, um die Kommunikation mit Anwendungen, die mit dem .NET Framework in jedem Szenario erstellt wurden, zu vereinfachen, kann es als Standard Tool dienen, um eine Vielzahl von Software Kommunikationsproblemen auf eine Weise zu lösen, die ASP.net nicht.

Neue WCF-Anwendungen können auf denselben Computern wie vorhandene ASP.NET-Webdienste bereitgestellt werden. Wenn die vorhandenen ASP.NET-Webdienste eine Version des .NET Framework vor Version 2,0 verwenden, können Sie das Registrierungs Tool "ASP.NET IIS" verwenden, um die .NET Framework 2,0 selektiv für IIS-Anwendungen bereitzustellen, in denen neue WCF-Anwendungen gehostet werden sollen. Dieses Tool ist unter [ASP.NET IIS Registration Tool (Aspnet_regiis. exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/k6h9cz8h(v=vs.90))dokumentiert und verfügt über eine Benutzeroberfläche, die in die IIS 6,0-Verwaltungskonsole integriert ist.

WCF kann zum Hinzufügen neuer Funktionen zu vorhandenen ASP.NET-Webdiensten verwendet werden, indem WCF-Dienste, die für die Verwendung im ASP.NET-Kompatibilitätsmodus konfiguriert sind, zu vorhandenen ASP.NET-Webdienst Anwendungen in IIS hinzu Aufgrund des ASP.NET-Kompatibilitätsmodus kann der Code für die neuen WCF-Dienste mithilfe der-Klasse auf die gleichen Anwendungs Zustandsinformationen wie der bereits vorhandene ASP.NET-Code zugreifen und diese aktualisieren <xref:System.Web.HttpContext> . Außerdem können sich die Anwendungen die gleichen Klassenbibliotheken teilen.

WCF-Clients können ASP.NET-Webdienste verwenden. WCF-Dienste, die mit konfiguriert sind, <xref:System.ServiceModel.BasicHttpBinding> können von ASP.NET-Webdienst Clients verwendet werden. ASP.NET-Webdienste können mit WCF-Anwendungen koexistieren, und WCF kann sogar zum Hinzufügen von Features zu vorhandenen ASP.NET-Webdiensten verwendet werden. Wenn Sie alle diese Methoden verwenden können, um WCF-und ASP.NET-Webdienste zu verwenden, sollten Sie ASP.NET-Webdienste nur zu WCF migrieren, wenn Sie Funktionen benötigen, die von WCF und nicht von ASP.NET-Webdiensten bereitgestellt werden.

Auch in den wenigen Fällen, in denen es erforderlich ist, ist die Migration von Code von einer Technologie zu einer anderen selten der richtige Ansatz. Der Grund für die Einführung der neuen Technologie besteht darin, neue Anforderungen zu erfüllen, die mit der früheren Technologie nicht erfüllt werden können. in diesem Fall muss eine neue Lösung entworfen werden, um die neu erweiterten Anforderungen zu erfüllen. Das neue Design profitiert von Ihren Erfahrungen mit dem vorhandenen System und von den Einsichten, die seit dem Design des neuen Systems gewonnen wurden. Das neue Design kann außerdem die Fähigkeiten der neuen Technologien komplett ausreizen, anstatt das alte Design auf der neuen Plattform zu reproduzieren. Nach dem Erstellen von Prototypen für wichtige Elemente des neuen Entwurfs ist es einfacher, Code aus dem vorhandenen System innerhalb der neuen zu verwenden.

## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Abrufen von Metadaten und Implementieren eines kompatiblen Diensts](how-to-retrieve-metadata-and-implement-a-compliant-service.md)
