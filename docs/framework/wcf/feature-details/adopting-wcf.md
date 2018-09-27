---
title: Übernehmen von Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
ms.openlocfilehash: 5773d2687eb06cfc562dbe25fa9b94864b1b3a49
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47232962"
---
# <a name="adopting-windows-communication-foundation"></a>Übernehmen von Windows Communication Foundation

Sie können auch Windows Communication Foundation (WCF) für neue Entwicklungen verwenden Sie beim Verwalten von vorhandener Anwendungen weiterhin über ASP.NET entwickelt wurden. Da WCF die beste Wahl für die Erleichterung der Kommunikation mit Anwendungen, die mit .NET Framework in jedem Szenario erstellt werden soll, kann als ein Standardtool für eine Vielzahl von Software von Kommunikationsproblemen auf eine Weise zu lösen, die von ASP.NET dienen ist nicht möglich.

Neue WCF-Anwendungen können auf denselben Computern wie vorhandene ASP.NET-Webdienste bereitgestellt werden. Wenn die vorhandenen ASP.NET-Webdienste eine Version von .NET Framework vor Version 2.0 verwenden, klicken Sie dann können das ASP.NET IIS Registration Tool Sie .NET Framework 2.0 auf IIS-Anwendungen bereitzustellen in der neue WCF-Anwendungen sind, gehostet werden. Dieses Tool finden Sie unter [ASP.NET IIS-Registrierungstool (Aspnet_regiis.exe)](https://go.microsoft.com/fwlink/?LinkId=94687), und verfügt über eine Benutzeroberfläche, die in der IIS 6.0-Verwaltungskonsole integriert.

WCF kann verwendet werden, um vorhandenen ASP.NET-Webdiensten neue Funktionen hinzugefügt, durch das Hinzufügen von WCF-Dienste, die so konfiguriert, dass vorhandene ASP.NET-Webdienstanwendungen in IIS im ASP.NET-Kompatibilitätsmodus ausgeführt werden kann. Aufgrund der ASP.NET-Kompatibilitätsmodus, der Code für die neuen WCF-Dienste kann zugreifen und diese aktualisieren die gleichen anwendungsstatusinformationen wie der zuvor vorhandene ASP.NET-Code mithilfe der <xref:System.Web.HttpContext> Klasse. Außerdem können sich die Anwendungen die gleichen Klassenbibliotheken teilen.

WCF-Clients können ASP.NET-Webdienste verwenden. WCF-Dienste, die mit konfiguriert werden die <xref:System.ServiceModel.BasicHttpBinding> können von ASP.NET-Webdienstclients verwendet werden. ASP.NET Web Services können mit WCF-Anwendungen gemeinsam vorliegen, und WCF kann auch verwendet werden, um vorhandenen ASP.NET-Webdiensten Funktionen hinzuzufügen. Wenn alle der folgenden Methoden, die in denen WCF und ASP.NET Web Services zusammen verwendet werden können, sollten Sie migrieren von ASP.NET-Webdiensten zu WCF, nur dann, wenn Sie Funktionen benötigen, die von WCF und nicht von ASP.NET Web Services bereitgestellt werden.

Auch in den wenigen Fällen, in denen es erforderlich ist, ist die Migrieren von Code von einer Technologie in eine andere selten der richtige Ansatz. Der Grund der Übernahme der neuen Technologie ist die Erfüllung neuer Anforderungen, die von der früheren Technologie nicht erfüllt werden können; in diesem Fall ist die richtige Vorgehensweise, eine neue Lösung zu entwerfen, die den neuen, erweiterten Satz an Anforderungen erfüllt. Das neue Design profitiert von Ihren Erfahrungen mit dem vorhandenen System und von den Einsichten, die seit dem Design des neuen Systems gewonnen wurden. Das neue Design kann außerdem die Fähigkeiten der neuen Technologien komplett ausreizen, anstatt das alte Design auf der neuen Plattform zu reproduzieren. Indem Schlüsselelemente des neuen Designs zu Prototypen gemacht werden, wird es einfacher, Code aus dem vorhandenen System innerhalb des neuen Systems wiederzuverwerten.

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Abrufen von Metadaten und Implementieren eines kompatiblen Diensts](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
