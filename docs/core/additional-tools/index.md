---
title: Zusätzliche Tools für .NET Core
description: Eine Übersicht über zusätzliche Tools, die die .NET Core-Funktionalität unterstützen und erweitern.
author: mlacouture
ms.author: johalex
ms.date: 01/19/2018
ms.custom: mvc
ms.openlocfilehash: 578d42e5a0a11ae76410289142d47c8d65abe7aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="net-core-additional-tools"></a><span data-ttu-id="37e44-103">Zusätzliche Tools für .NET Core</span><span class="sxs-lookup"><span data-stu-id="37e44-103">.NET Core additional tools</span></span>

<span data-ttu-id="37e44-104">In diesem Abschnitt werden Tools aufgelistet, die die .NET Core-Funktionalität zusätzlich zu den [.NET Core-CLI-Tools](..\tools\index.md) unterstützen und erweitern.</span><span class="sxs-lookup"><span data-stu-id="37e44-104">This section compiles a list of tools that support and extend the .NET Core functionality, in addition to the [.NET Core command-line interface (CLI)](..\tools\index.md) tools.</span></span>

## <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[<span data-ttu-id="37e44-105">WCF Web Service Reference-Tool</span><span class="sxs-lookup"><span data-stu-id="37e44-105">WCF Web Service Reference Tool</span></span>](wcf-web-service-reference-guide.md)

<span data-ttu-id="37e44-106">Bei WCF Web Service Reference handelt es sich um einen mit Visual Studio verbundenen Dienstanbieter, der zuerst in [Visual Studio 2017 Version 15.5](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes#WCFTools) enthalten war.</span><span class="sxs-lookup"><span data-stu-id="37e44-106">The WCF Web Service Reference is a Visual Studio connected service provider that made its debut in [Visual Studio 2017 version 15.5](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes#WCFTools).</span></span> <span data-ttu-id="37e44-107">Dieses Tool ruft Metadaten von einem Webdienst in der aktuellen Projektmappe, von einer Netzwerkadresse oder aus einer WSDL-Datei ab und generiert eine mit .NET Core kompatible Quelldatei. Diese enthält den Proxycode des WCF-Clients (Windows Communication Foundation), den Sie verwenden können, um auf einen Webdienst zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="37e44-107">This tool retrieves metadata from a web service in the current solution, on a network location, or from a WSDL file, and generates a .NET Core compatible source file containing Windows Communication Foundation (WCF) client proxy code that you can use to access the web service.</span></span>

## <a name="xml-serializer-generatorxml-serializer-generatormd"></a>[<span data-ttu-id="37e44-108">XML Serializer Generator</span><span class="sxs-lookup"><span data-stu-id="37e44-108">XML Serializer Generator</span></span>](xml-serializer-generator.md)

<span data-ttu-id="37e44-109">Das NuGet-Paket [Microsoft.XmlSerializer.Generator](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) gilt (wie der [XML Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) für .NET Framework) für .NET Core- und .NET Standard-Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="37e44-109">Like the [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) for the .NET Framework, the [Microsoft.XmlSerializer.Generator NuGet package](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) is the solution for .NET Core and .NET Standard libraries.</span></span> <span data-ttu-id="37e44-110">Es erstellt eine XML-Serialisierungsassembly für Typen, die in einer Assembly vorhanden sind, um die Startleistung der XML-Serialisierung zu verbessern, wenn Objekte dieser Typen mithilfe von <xref:System.Xml.Serialization.XmlSerializer> serialisiert oder deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="37e44-110">It creates an XML serialization assembly for types contained in an assembly to improve the startup performance of XML serialization when serializing or de-serializing objects of those types using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>