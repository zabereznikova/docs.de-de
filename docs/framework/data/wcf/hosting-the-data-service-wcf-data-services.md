---
title: Hosting des Datendiensts (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, Windows Communication Foundation
ms.assetid: b48f42ce-22ce-4f8d-8f0d-f7ddac9125ee
ms.openlocfilehash: 5dfa1d9f02f660b55ecf6598ef5012174a1ba853
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172592"
---
# <a name="hosting-the-data-service-wcf-data-services"></a>Hosting des Datendiensts (WCF Data Services)

Mithilfe WCF Data Services können Sie einen Dienst erstellen, der Daten als Open Data Protocol (odata)-Feed verfügbar macht. Dieser Datendienst wird als Klasse definiert, die von <xref:System.Data.Services.DataService%601> erbt. Diese Klasse stellt die Funktionalität bereit, die erforderlich ist, um Anforderungs Nachrichten zu verarbeiten, Updates für die Datenquelle auszuführen und Antwort Nachrichten zu generieren, die von odata benötigt werden. Ein Datendienst kann jedoch Netzwerksockets für eingehende HTTP-Anforderungen weder binden noch diese überwachen. Für diese erforderliche Funktion benötigt der Datendienst eine Hostingkomponente.

 Der Datendiensthost führt die folgenden Aufgaben im Namen des Datendiensts aus:

- Lauscht auf Anforderungen und leitet diese an den Datendienst weiter.

- Erstellt für jede Anforderung eine Instanz des Datendiensts.

- Fordert an, dass der Datendienst die eingehende Anforderung verarbeitet.

- Sendet die Antwort im Namen des Datendiensts.

 Um das Hosting eines Daten Diensts zu vereinfachen, ist WCF Data Services für die Integration in Windows Communication Foundation (WCF) konzipiert. Der Datendienst bietet eine WCF-Standard Implementierung, die in einer ASP.NET-Anwendung als Datendienst Host fungiert. Daher können Sie einen Datendienst in einer der folgenden Methoden hosten:

- In einer ASP.NET-Anwendung.

- In einer verwalteten Anwendung, die selbst gehostete WCF-Dienste unterstützt.

- In einem anderen benutzerdefinierten Datendiensthost.

## <a name="hosting-a-data-service-in-an-aspnet-application"></a>Hosten eines Datendiensts in einer ASP.NET-Anwendung

Wenn Sie das Dialogfeld **Neues Element hinzufügen** in Visual Studio 2015 verwenden, um einen Datendienst in einer ASP.NET-Anwendung zu definieren, generiert das Tool zwei neue Dateien im Projekt. Die erste Datei verfügt über die `.svc`-Erweiterung und weist die WCF-Laufzeit an, wie der Datendienst instanziiert werden soll. Im folgenden finden Sie ein Beispiel für diese Datei für den Northwind-Beispiel Datendienst, der erstellt wird, wenn Sie den [Schnellstart](quickstart-wcf-data-services.md)ausführen:

```aspx-csharp
<%@ ServiceHost Language="C#"
    Factory="System.Data.Services.DataServiceHostFactory,
            System.Data.Services, Version=4.0.0.0,
            Culture=neutral, PublicKeyToken=b77a5c561934e089"
    Service="NorthwindService.Northwind" %>
```

 Diese Direktive weist die Anwendung an, den Diensthost für die benannte Datendienstklasse mithilfe der <xref:System.Data.Services.DataServiceHostFactory>-Klasse zu erstellen.

 Die CodeBehind-Seite für die `.svc`-Datei enthält die Klasse, bei der es sich um die Implementierung des Datendiensts selbst handelt und die für den Northwind-Beispieldatendienst folgendermaßen definiert wird:

 [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
 [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

 Da sich ein Datendienst wie ein WCF-Dienst verhält, wird der Datendienst in ASP.NET integriert und folgt dem WCF-webprogrammier Modell. Weitere Informationen finden Sie unter [WCF-Dienste und ASP.net](../../wcf/feature-details/wcf-services-and-aspnet.md) und [WCF-Web-HTTP-Programmiermodell](../../wcf/feature-details/wcf-web-http-programming-model.md).

## <a name="self-hosted-wcf-services"></a>Selbst gehostete WCF-Dienste

 Da Sie eine WCF-Implementierung beinhaltet, wird WCF Data Services das Self-Hosting eines Daten Diensts als WCF-Dienst unterstützen. Ein Dienst kann in jeder .NET Framework Anwendung, z. b. einer Konsolenanwendung, selbstgeh ostet werden. Die <xref:System.Data.Services.DataServiceHost>-Klasse, die von <xref:System.ServiceModel.Web.WebServiceHost> erbt, wird verwendet, um den Datendienst bei einer bestimmten Adresse zu instanziieren.

 Selbsthosting kann für die Entwicklung und für Tests verwendet werden, da die Bereitstellung und Problembehandlung vereinfacht wird. Diese Art von Hosting stellt jedoch nicht die erweiterten Hosting-und Verwaltungsfunktionen bereit, die von ASP.net oder Internetinformationsdienste (IIS) bereitgestellt werden. Weitere Informationen finden Sie unter [Hosting in einer verwalteten Anwendung](../../wcf/feature-details/hosting-in-a-managed-application.md).

## <a name="defining-a-custom-data-service-host"></a>Definieren eines benutzerdefinierten Datendiensthosts

 Wenn die WCF-Hostimplementierung zu restriktiv ist, können Sie für einen Datendienst auch einen benutzerdefinierten Host definieren. Alle Klassen, die eine <xref:System.Data.Services.IDataServiceHost>-Schnittstelle implementieren, können für einen Datendienst als Netzwerkhost verwendet werden. Ein benutzerdefinierter Host muss die <xref:System.Data.Services.IDataServiceHost>-Schnittstelle implementieren und in der Lage sein, die folgenden grundlegenden Aufgaben des Datendiensthosts zu übernehmen:

- Bereitstellen des Dienststammpfads für den Datendienst

- Verarbeiten der Anforderungs- und Antwortheaderinformationen für die entsprechende <xref:System.Data.Services.IDataServiceHost>-Memberimplementierung

- Behandeln der vom Datendienst ausgelösten Ausnahmen

- Überprüfen der Parameter in der Abfragezeichenfolge

## <a name="see-also"></a>Weitere Informationen

- [Definieren von WCF Data Services](defining-wcf-data-services.md)
- [Verfügbarmachen Ihrer Daten als Dienst](exposing-your-data-as-a-service-wcf-data-services.md)
- [Konfigurieren des Datendiensts](configuring-the-data-service-wcf-data-services.md)
