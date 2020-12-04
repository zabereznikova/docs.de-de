---
title: Tools und Diagnose in .net
author: IEvangelist
description: Erfahren Sie mehr über die Entwicklungs-und Diagnosetools für .NET-Entwickler.
ms.author: dapine
ms.date: 10/21/2020
ms.topic: overview
ms.openlocfilehash: 07c1a161a0bb429403db6852fe77749d83c19ec0
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "96592011"
---
# <a name="tools-and-diagnostics-in-net"></a>Tools und Diagnose in .net

In diesem Artikel erfahren Sie mehr über die verschiedenen Tools, die .NET-Entwicklern zur Verfügung stehen. Mit .net verfügen Sie über eine robuste Software Development Kit (SDK), die eine Befehlszeilenschnittstelle (Command-Line Interface, CLI) umfasst. Die .net-CLI ermöglicht viele der Funktionen in. NET Ready Integrated Development Environment (IDES). Außerdem bietet dieser Artikel Ressourcen zu Produktivitäts Funktionen, wie z. b. .net CLI-Tools für die Diagnose von Leistungsproblemen, Speicher Verlusten, hoher CPU, Deadlocks und Tool Unterstützung für die Code Analyse.

## <a name="net-sdk"></a>.NET SDK

Das .NET SDK umfasst sowohl die .NET-Laufzeit als auch die .net-CLI. Sie können das [.NET SDK](https://dotnet.microsoft.com/download) für Windows, Linux, macOS oder docker herunterladen. Weitere Informationen finden Sie unter [Übersicht über das .NET SDK](../core/sdk.md).

## <a name="net-cli"></a>.NET CLI

Die .net-CLI ist eine plattformübergreifende Toolkette zum entwickeln, entwickeln, ausführen und Veröffentlichen von .NET-Anwendungen. Die .NET-CLI ist im .NET SDK enthalten. Weitere Informationen finden Sie unter [Übersicht über die .net-CLI](../core/tools/index.md).

## <a name="ides"></a>IDEs

Sie können .NET-Anwendungen in [Visual Studio Code](https://code.visualstudio.com/docs), [Visual Studio](/visualstudio/windows)oder [Visual Studio für Mac](/visualstudio/mac)schreiben. Informationen zu cloudgestützten Entwicklungsumgebungen finden Sie unter [Visual Studio-Code Spaces](/visualstudio/codespaces/overview/what-is-vsonline).

## <a name="additional-tools"></a>Weitere Tools

Zusätzlich zu den gängigeren Tools stellt .net auch Tools für bestimmte Szenarien bereit. Zu den Anwendungsfällen gehören das Deinstallieren des .NET SDK oder der .NET-Laufzeit, das Abrufen von Windows Communication Foundation (WCF)-Metadaten, das Erstellen von Proxy Quellcode und das Serialisieren von XML. Weitere Informationen finden Sie unter [Übersicht über .net-zusätzliche Tools](../core/additional-tools/index.md).

## <a name="diagnostics-and-instrumentation"></a>Diagnose und Instrumentation

Als .NET-Entwickler können Sie gängige Leistungs Diagnosetools nutzen, um die APP-Leistung zu überwachen, Apps mit Ablauf Verfolgung zu erstellen, Leistungsmetriken zu erfassen und Dumpdateien zu analysieren. Sie erfassen Leistungsmetriken mit Ereignis Indikatoren und nutzen Profil Erstellungs Tools, um Einblicke in die Leistung von apps zu erhalten. Weitere Informationen finden Sie unter [.net-Diagnosetools](../core/diagnostics/index.md).

## <a name="code-analysis"></a>Codeanalyse

Die Analysen der .net-compilerplattform (Roslyn) untersuchen ihren c#-oder Visual Basic Code auf Codequalität und Probleme im Code Stil. Weitere Informationen finden Sie unter [Übersicht über die .net-Quell Code Analyse](code-analysis/overview.md).
