---
title: Zusätzliche Tools für .NET Core
description: Eine Übersicht über zusätzliche Tools, die die .NET Core-Funktionalität unterstützen und erweitern.
author: mlacouture
manager: wpickett
ms.author: johalex
ms.date: 01/19/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.custom: mvc
ms.workload:
- dotnetcore
ms.openlocfilehash: 2e33cdbcbe9c81e6c3af84f8f2795ee3dc6e28ae
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="net-core-additional-tools"></a>Zusätzliche Tools für .NET Core

In diesem Abschnitt werden Tools aufgelistet, die die .NET Core-Funktionalität zusätzlich zu den [.NET Core-CLI-Tools](..\tools\index.md) unterstützen und erweitern.

## <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[WCF Web Service Reference-Tool](wcf-web-service-reference-guide.md)

Bei WCF Web Service Reference handelt es sich um einen mit Visual Studio verbundenen Dienstanbieter, der zuerst in [Visual Studio 2017 Version 15.5](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes#WCFTools) enthalten war. Dieses Tool ruft Metadaten von einem Webdienst in der aktuellen Projektmappe, von einer Netzwerkadresse oder aus einer WSDL-Datei ab und generiert eine mit .NET Core kompatible Quelldatei. Diese enthält den Proxycode des WCF-Clients (Windows Communication Foundation), den Sie verwenden können, um auf einen Webdienst zuzugreifen.

## <a name="xml-serializer-generatorxml-serializer-generatormd"></a>[XML Serializer Generator](xml-serializer-generator.md)

Das NuGet-Paket [Microsoft.XmlSerializer.Generator](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) gilt (wie der [XML Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) für .NET Framework) für .NET Core- und .NET Standard-Bibliotheken. Es erstellt eine XML-Serialisierungsassembly für Typen, die in einer Assembly vorhanden sind, um die Startleistung der XML-Serialisierung zu verbessern, wenn Objekte dieser Typen mithilfe von <xref:System.Xml.Serialization.XmlSerializer> serialisiert oder deserialisiert werden.