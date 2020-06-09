---
title: Allgemeine Anleitung
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Allgemeine Anleitung
ms.date: 09/11/2018
ms.openlocfilehash: 6e63d7804abc1703f17378584d58d66a933022c7
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "84306876"
---
# <a name="general-guidance"></a>Allgemeine Anleitung

Dieser Abschnitt enthält eine Zusammenfassung darüber, wann .NET Core bzw. .NET Framework verwendet werden sollte. In den folgenden Abschnitten werden weitere Informationen dazu bereitgestellt.

Verwenden Sie .NET Core mit Linux- oder Windows-Containern für Ihre containerisierte Docker-Serveranwendung, wenn:

- Es bestehen plattformübergreifende Anforderungen. Sie beispielsweise Linux- und Windows-Container verwenden möchten

- Die Architektur Ihrer Anwendung auf Microservices basiert

- Sie Container schnell starten müssen und den Ressourcenbedarf pro Container gering halten möchten, um eine höhere Dichte oder mehr Container pro Hardwareeinheit zu erreichen und Ihre Kosten zu senken

Kurz gesagt sollte Ihre Wahl standardmäßig auf .NET Core fallen, wenn Sie neue .NET-Containeranwendungen erstellen. .NET Core weist viele Vorteile auf und entspricht dem Konzept und der Arbeitsweise von Containern am besten.

Ein zusätzlicher Vorteil bei der Verwendung von .NET Core besteht darin, dass Sie verschiedene Versionen von .NET für Anwendungen auf dem gleichen Computer parallel ausführen können. Dieser Vorteil ist wichtiger für Server oder virtuelle Computer, die keine Container verwenden, da durch Container die Versionen von .NET isoliert werden, die für die App erforderlich sind. (Solange diese mit dem zugrunde liegenden Betriebssystem kompatibel sind)

Verwenden Sie .NET Framework für Ihre containerisierte Docker-Serveranwendung, wenn:

- Ihre Anwendung derzeit .NET Framework verwendet und starke Abhängigkeiten von Windows aufweist

- Sie Windows-APIs verwenden müssen, die von .NET Core nicht unterstützt werden

- Sie .NET-Bibliotheken von Drittanbietern oder NuGet-Pakete verwenden müssen, die für .NET Core nicht verfügbar sind

Das Verwenden von .NET Framework auf Docker kann Ihre Bereitstellungen verbessern, indem Bereitstellungsprobleme reduziert werden. Dieses [Lift & Shift-Szenario](https://aka.ms/liftandshiftwithcontainersebook) ist wichtig für das Containerisieren von veralteten Anwendungen, die ursprünglich mit dem herkömmlichen .NET Framework entwickelt wurden, z.B. mit ASP.NET WebForms, MVC-Web-Apps oder WCF-Diensten (Windows Communication Foundation).

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **E-Book: Modernize existing .NET Framework applications with Azure and Windows Containers** (E-Book: Modernisieren vorhandener .NET Framework-Anwendungen mit Azure und Windows-Containern)  
    <https://aka.ms/liftandshiftwithcontainersebook>

- **Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers** (Beispiel-Apps: Modernisieren von veralteten ASP.NET-Web-Apps mithilfe von Windows-Containern)  
    <https://aka.ms/eshopmodernizing>

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](net-core-container-scenarios.md)
