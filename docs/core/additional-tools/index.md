---
title: Weitere Tools
description: Eine Übersicht über zusätzliche Tools, die Sie zum Unterstützen und Erweitern der .NET Core-Funktionalität installieren können.
author: mlacouture
ms.date: 02/13/2020
ms.custom: mvc
ms.openlocfilehash: f563dff312442cbf068d52d08992621e3d6f1460
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699000"
---
# <a name="net-core-additional-tools-overview"></a>Zusätzliche .NET Core-Tools – Übersicht

In diesem Abschnitt werden Tools aufgelistet, die die .NET Core-Funktionalität zusätzlich zur .NET Core-CLI unterstützen und erweitern.

## <a name="net-core-uninstall-tool"></a>.NET Core-Deinstallationstool

Mit dem [.NET Core-Deinstallationstool](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) können Sie veranlassen, dass alle auf einem System installierten .NET Core SDKs und Runtimes entfernt werden, die nicht den angegebenen Versionen entsprechen. Hierfür stehen Ihnen verschiedene Optionen zur Verfügung.

## <a name="net-core-diagnostic-tools"></a>.NET Core-Diagnosetools

[dotnet-counters](../diagnostics/dotnet-counters.md) ist ein Tool zur Leistungsüberwachung der Integrität auf erster Ebene und zur Leistungsuntersuchung.

Mit dem Tool [dotnet-dump](../diagnostics/dotnet-dump.md) können Sie Windows- und Linux-Kernspeicherabbilder ohne einen nativen Debugger erfassen und analysieren.

Mit [dotnet-gcdump](../diagnostics/dotnet-gcdump.md) können Sie GC-Speicherabbilder (Garbage Collector) aus .NET-Liveprozessen erfassen.

[dotnet-trace](../diagnostics/dotnet-trace.md) erfasst Profilerstellungsdaten von Ihrer App, die Sie in Szenarien unterstützen können, in denen Sie die Ursachen für eine langsame App-Ausführung herausfinden müssen.

## <a name="wcf-web-service-reference-tool"></a>WCF Web Service Reference-Tool

Das [WCF Web Service Reference-Tool](wcf-web-service-reference-guide.md) (Windows Communication Foundation) ist ein mit Visual Studio verbundener Dienstanbieter, der mit [Visual Studio 2017, Version 15.5](/visualstudio/releasenotes/vs2017-relnotes-v15.5#WCFTools) eingeführt wurde. Mit diesem Tool werden Metadaten aus einem Webdienst in der aktuellen Lösung, aus einem Netzwerkspeicherort oder aus einer WSDL-Datei abgerufen. Es generiert eine Quelldatei, die mit .NET Core kompatibel ist, und definiert eine WCF-Proxyklasse mit Methoden, die Sie für den Zugriff auf die Webdienstvorgänge verwenden können.

## <a name="wcf-dotnet-svcutil-tool"></a>WCF-Tool „dotnet-svcutil“

Das WCF-Tool [dotnet-svcutil](dotnet-svcutil-guide.md) ist ein .NET-Tool, das Metadaten aus einem Webdienst in einem Netzwerk oder aus einer WSDL-Datei abruft. Es generiert eine Quelldatei, die mit .NET Core kompatibel ist, und definiert eine WCF-Proxyklasse mit Methoden, die Sie für den Zugriff auf die Webdienstvorgänge verwenden können.

Das Tool **dotnet-svcutil** ist eine Alternative zum mit Visual Studio verbundenen Dienstanbieter [**WCF Web Service Reference**](wcf-web-service-reference-guide.md), der erstmals in Visual Studio 2017, Version 15.5 enthalten war. Das .NET-Tool **dotnet-svcutil** ist für Linux, macOS und Windows verfügbar.

## <a name="wcf-dotnet-svcutilxmlserializer-tool"></a>WCF-Tool „dotnet-svcutil.xmlserializer“

Im .NET Framework können sie mit dem svcutil-Tool vorab eine Serialisierungsassembly generieren. Das WCF-Tool [dotnet-svcutil.xmlserializer](dotnet-svcutil.xmlserializer-guide.md) bietet eine ähnliche Funktionalität für .NET Core. Es generiert vorab C#-Serialisierungscode für die Typen in der Clientanwendung, die vom WCF-Dienstvertrag verwendet werden und über <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können. Dies verbessert die Startleistung der XML-Serialisierung beim Serialisieren oder Deserialisieren von Objekten dieser Typen.

## <a name="xml-serializer-generator"></a>XML Serializer Generator

Das NuGet-Paket [Microsoft.XmlSerializer.Generator](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) gilt (wie der [XML Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) für .NET Framework) für .NET Core- und .NET Standard-Bibliotheken. Es erstellt eine XML-Serialisierungsassembly für Typen, die in einer Assembly vorhanden sind, um die Startleistung der XML-Serialisierung zu verbessern, wenn Objekte dieser Typen mithilfe von <xref:System.Xml.Serialization.XmlSerializer> serialisiert oder deserialisiert werden.

## <a name="generating-self-signed-certificates"></a>Generieren von selbstsignierten Zertifikaten

Sie können [dotnet dev-certs](self-signed-certificates-guide.md) verwenden, um selbstsignierte Zertifikate für Entwicklungs- und Testszenarios zu erstellen.
