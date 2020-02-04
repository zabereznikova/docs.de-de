---
title: Weitere Tools
description: Eine Übersicht über zusätzliche Tools, die Sie zum Unterstützen und Erweitern der .NET Core-Funktionalität installieren können.
author: mlacouture
ms.date: 12/02/2019
ms.custom: mvc
ms.openlocfilehash: 23b94ceef729cdc3d83032e3897312eb1d1afd79
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920931"
---
# <a name="net-core-additional-tools-overview"></a>Zusätzliche .NET Core-Tools – Übersicht

In diesem Abschnitt werden Tools aufgelistet, die die .NET Core-Funktionalität zusätzlich zur .NET Core-CLI unterstützen und erweitern.

## <a name="net-core-uninstall-tooluninstall-toolmd"></a>[.NET Core-Deinstallationstool](uninstall-tool.md)

Mit dem [.NET Core-Deinstallationstool](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) können Sie veranlassen, dass alle auf einem System installierten .NET Core SDKs und Runtimes entfernt werden, die nicht den angegebenen Versionen entsprechen. Hierfür stehen Ihnen verschiedene Optionen zur Verfügung.

## <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[WCF Web Service Reference-Tool](wcf-web-service-reference-guide.md)

Bei WCF Web Service Reference handelt es sich um einen mit Visual Studio verbundenen Dienstanbieter, der zuerst in [Visual Studio 2017 Version 15.5](/visualstudio/releasenotes/vs2017-relnotes-v15.5#WCFTools) enthalten war. Mit diesem Tool werden Metadaten aus einem Webdienst in der aktuellen Lösung, aus einem Netzwerkspeicherort oder aus einer WSDL-Datei abgerufen. Es generiert eine Quelldatei, die mit .NET Core kompatibel ist, und definiert eine WCF-Proxyklasse mit Methoden, die Sie für den Zugriff auf die Webdienstvorgänge verwenden können.

## <a name="wcf-dotnet-svcutil-tooldotnet-svcutil-guidemd"></a>[WCF-Tool dotnet-svcutil](dotnet-svcutil-guide.md)

Das WCF-Tool (Windows Communication Foundation) „dotnet-svcutil“ ist ein .NET-Tool, das Metadaten aus einem Webdienst in einem Netzwerk oder aus einer WSDL-Datei abruft. Es generiert eine Quelldatei, die mit .NET Core kompatibel ist, und definiert eine WCF-Proxyklasse mit Methoden, die Sie für den Zugriff auf die Webdienstvorgänge verwenden können.

Das Tool **dotnet-svcutil** ist eine alternative Option zum mit Visual Studio verbundenen Dienstanbieter [**WCF Web Service Reference**](wcf-web-service-reference-guide.md), der zuerst in Visual Studio 2017 Version 15.5 enthalten war. Das .NET-Tool **dotnet-svcutil** ist plattformübergreifend für Linux, macOS und Windows verfügbar.

## <a name="wcf-dotnet-svcutilxmlserializer-tooldotnet-svcutilxmlserializer-guidemd"></a>[WCF dotnet-svcutil.xmlserializer-Tool](dotnet-svcutil.xmlserializer-guide.md)

Im .NET Framework können sie mit dem svcutil-Tool vorab eine Serialisierungsassembly generieren. Das NuGet-Paket „dotnet-svcutil.xmlserializer“ bietet eine ähnliche Funktionalität in .NET Core. Es generiert vorab C#-Serialisierungscode für die Typen in der Clientanwendung, die vom WCF-Dienstvertrag verwendet werden und über <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können. Dies verbessert die Startleistung der XML-Serialisierung beim Serialisieren oder Deserialisieren von Objekten dieser Typen.

## <a name="xml-serializer-generatorxml-serializer-generatormd"></a>[XML Serializer Generator](xml-serializer-generator.md)

Das NuGet-Paket [Microsoft.XmlSerializer.Generator](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) gilt (wie der [XML Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) für .NET Framework) für .NET Core- und .NET Standard-Bibliotheken. Es erstellt eine XML-Serialisierungsassembly für Typen, die in einer Assembly vorhanden sind, um die Startleistung der XML-Serialisierung zu verbessern, wenn Objekte dieser Typen mithilfe von <xref:System.Xml.Serialization.XmlSerializer> serialisiert oder deserialisiert werden.
