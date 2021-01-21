---
title: Allgemeine Anleitung
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Allgemeine Anleitung
ms.date: 01/13/2021
ms.openlocfilehash: 4fd2d936c524cb3e5ae463038eaffe88b459d2bd
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98187950"
---
# <a name="general-guidance"></a>Allgemeine Anleitung

Dieser Abschnitt enthält eine Zusammenfassung darüber, wann .NET 5 bzw. .NET Framework verwendet werden sollte. In den folgenden Abschnitten werden weitere Informationen dazu bereitgestellt.

Verwenden Sie .NET 5 mit Linux- oder Windows-Containern in den folgenden Fällen für Ihre containerisierte Docker-Serveranwendung:

- Es bestehen plattformübergreifende Anforderungen. Sie beispielsweise Linux- und Windows-Container verwenden möchten

- Die Architektur Ihrer Anwendung auf Microservices basiert

- Sie Container schnell starten müssen und den Ressourcenbedarf pro Container gering halten möchten, um eine höhere Dichte oder mehr Container pro Hardwareeinheit zu erreichen und Ihre Kosten zu senken

Kurz gesagt sollte Ihre Wahl immer auf .NET 5 fallen, wenn Sie neue .NET-Containeranwendungen erstellen. .NET Core weist viele Vorteile auf und entspricht dem Konzept und der Arbeitsweise von Containern am besten.

Ein zusätzlicher Vorteil bei der Verwendung von .NET 5 besteht darin, dass Sie verschiedene Versionen von .NET für Anwendungen auf dem gleichen Computer parallel ausführen können. Dieser Vorteil ist wichtiger für Server oder virtuelle Computer, die keine Container verwenden, da durch Container die Versionen von .NET isoliert werden, die für die App erforderlich sind. (Solange diese mit dem zugrunde liegenden Betriebssystem kompatibel sind)

Verwenden Sie .NET Framework für Ihre containerisierte Docker-Serveranwendung, wenn:

- Ihre Anwendung derzeit .NET Framework verwendet und starke Abhängigkeiten von Windows aufweist

- Sie Windows-APIs verwenden müssen, die von .NET 5 nicht unterstützt werden

- Sie .NET-Bibliotheken von Drittanbietern oder NuGet-Pakete verwenden müssen, die für .NET 5 nicht verfügbar sind

Das Verwenden von .NET Framework auf Docker kann Ihre Bereitstellungen verbessern, indem Bereitstellungsprobleme reduziert werden. Dieses [Lift & Shift-Szenario](https://aka.ms/liftandshiftwithcontainersebook) ist wichtig für das Containerisieren von veralteten Anwendungen, die ursprünglich mit dem herkömmlichen .NET Framework entwickelt wurden, z.B. mit ASP.NET WebForms, MVC-Web-Apps oder WCF-Diensten (Windows Communication Foundation).

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **E-Book: Modernize existing .NET Framework applications with Azure and Windows Containers** (E-Book: Modernisieren vorhandener .NET Framework-Anwendungen mit Azure und Windows-Containern)  
    <https://aka.ms/liftandshiftwithcontainersebook>

- **Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers** (Beispiel-Apps: Modernisieren von veralteten ASP.NET-Web-Apps mithilfe von Windows-Containern)  
    <https://aka.ms/eshopmodernizing>

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](net-core-container-scenarios.md)
