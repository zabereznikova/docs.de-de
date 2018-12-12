---
title: Zusätzliche .NET Core-CLI-Tools
description: Eine Übersicht über zusätzliche Tools, die Sie zum Unterstützen und Erweitern der .NET Core-Funktionalität installieren können.
author: mlacouture
ms.date: 11/27/2018
ms.custom: mvc, seodec18
ms.openlocfilehash: 5f42cddc31204bba2aafaee0b909bbf92d232fde
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243587"
---
# <a name="net-core-additional-tools-overview"></a>Zusätzliche .NET Core-Tools – Übersicht

In diesem Abschnitt werden Tools aufgelistet, die die .NET Core-Funktionalität zusätzlich zu den [.NET Core-CLI-Tools](../tools/index.md) unterstützen und erweitern.

## <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[WCF Web Service Reference-Tool](wcf-web-service-reference-guide.md)

Bei WCF Web Service Reference handelt es sich um einen mit Visual Studio verbundenen Dienstanbieter, der zuerst in [Visual Studio 2017 Version 15.5](/visualstudio/releasenotes/vs2017-relnotes-v15.5#WCFTools) enthalten war. Dieses Tool ruft Metadaten von einem Webdienst in der aktuellen Projektmappe von einer Netzwerkadresse oder aus einer WSDL-Datei ab und generiert eine mit .NET Core kompatible Quelldatei, die eine WCF-Proxyklasse mit Methoden definiert, die Sie verwenden können, um auf die Webdienstvorgänge zuzugreifen.

## <a name="wcf-dotnet-svcutil-tooldotnet-svcutil-guidemd"></a>[WCF-Tool dotnet-svcutil](dotnet-svcutil-guide.md)

Das WCF-Tool „dotnet-svcutil“ ist ein .NET Core-CLI-Tool, das Metadaten von einem Webdienst aus einem Netzwerkspeicherort oder einer WSDL-Datei abruft und eine mit .NET Core kompatible Quelldatei generiert, die eine WCF-Proxyklasse mit Methoden definiert, die Sie verwenden können, um auf die Webdienstvorgänge zuzugreifen.
Das Tool **dotnet-svcutil** ist eine alternative Option zum mit Visual Studio verbundenen Dienstanbieter [**WCF Web Service Reference**](wcf-web-service-reference-guide.md), der zuerst in Visual Studio 2017 Version15.5 enthalten war. Das Tool **dotnet-svcutil** ist plattformübergeifend als .NET Core-CLI-Tool unter Linux, macOS und Windows verfügbar.

## <a name="wcf-dotnet-svcutilxmlserializer-tooldotnet-svcutilxmlserializer-guidemd"></a>[WCF dotnet-svcutil.xmlserializer-Tool](dotnet-svcutil.xmlserializer-guide.md)

Im .NET Framework können sie mit dem svcutil-Tool vorab eine Serialisierungsassembly generieren. Das NuGet-Paket „dotnet-svcutil.xmlserializer“ bietet eine ähnliche Funktionalität in .NET Core. Es generiert vorab C#-Serialisierungscode für die Typen in der Clientanwendung, die vom WCF-Dienstvertrag verwendet werden und über <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können. Dies verbessert die Startleistung der XML-Serialisierung beim Serialisieren oder Deserialisieren von Objekten dieser Typen.

## <a name="xml-serializer-generatorxml-serializer-generatormd"></a>[XML Serializer Generator](xml-serializer-generator.md)

Das NuGet-Paket [Microsoft.XmlSerializer.Generator](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) gilt (wie der [XML Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) für .NET Framework) für .NET Core- und .NET Standard-Bibliotheken. Es erstellt eine XML-Serialisierungsassembly für Typen, die in einer Assembly vorhanden sind, um die Startleistung der XML-Serialisierung zu verbessern, wenn Objekte dieser Typen mithilfe von <xref:System.Xml.Serialization.XmlSerializer> serialisiert oder deserialisiert werden.