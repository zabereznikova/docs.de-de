---
title: Zusätzliche Tools für .NET Core
description: Eine Übersicht über zusätzliche Tools, die die .NET Core-Funktionalität unterstützen und erweitern.
author: mlacouture
ms.author: johalex
ms.date: 01/19/2018
ms.custom: mvc
ms.openlocfilehash: ba63ef6cdc092d06e267637112070e7cd5133a45
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511753"
---
# <a name="net-core-additional-tools"></a>Zusätzliche Tools für .NET Core

In diesem Abschnitt werden Tools aufgelistet, die die .NET Core-Funktionalität zusätzlich zu den [.NET Core-CLI-Tools](..\tools\index.md) unterstützen und erweitern.

## <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[WCF Web Service Reference-Tool](wcf-web-service-reference-guide.md)

Bei WCF Web Service Reference handelt es sich um einen mit Visual Studio verbundenen Dienstanbieter, der zuerst in [Visual Studio 2017 Version 15.5](https://visualstudio.microsoft.com/news/releasenotes/vs2017-relnotes#WCFTools) enthalten war. Dieses Tool ruft Metadaten von einem Webdienst in der aktuellen Projektmappe von einer Netzwerkadresse oder aus einer WSDL-Datei ab und generiert eine mit .NET Core kompatible Quelldatei, die eine WCF-Proxyklasse mit Methoden definiert, die Sie verwenden können, um auf die Webdienstvorgänge zuzugreifen.

## <a name="wcf-dotnet-svcutil-tooldotnet-svcutil-guidemd"></a>[WCF-Tool dotnet-svcutil](dotnet-svcutil-guide.md)

Das WCF-Tool „dotnet-svcutil“ ist ein .NET Core-CLI-Tool, das Metadaten von einem Webdienst aus einem Netzwerkspeicherort oder einer WSDL-Datei abruft und eine mit .NET Core kompatible Quelldatei generiert, die eine WCF-Proxyklasse mit Methoden definiert, die Sie verwenden können, um auf die Webdienstvorgänge zuzugreifen. Das Tool **dotnet-svcutil** ist eine alternative Option zum mit Visual Studio verbundenen Dienstanbieter [**WCF Web Service Reference**](wcf-web-service-reference-guide.md), der zuerst in Visual Studio 2017 Version15.5 enthalten war. Das Tool **dotnet-svcutil** ist plattformübergeifend als .NET Core-CLI-Tool unter Linux, macOS und Windows verfügbar.

## <a name="xml-serializer-generatorxml-serializer-generatormd"></a>[XML Serializer Generator](xml-serializer-generator.md)

Das NuGet-Paket [Microsoft.XmlSerializer.Generator](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) gilt (wie der [XML Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) für .NET Framework) für .NET Core- und .NET Standard-Bibliotheken. Es erstellt eine XML-Serialisierungsassembly für Typen, die in einer Assembly vorhanden sind, um die Startleistung der XML-Serialisierung zu verbessern, wenn Objekte dieser Typen mithilfe von <xref:System.Xml.Serialization.XmlSerializer> serialisiert oder deserialisiert werden.