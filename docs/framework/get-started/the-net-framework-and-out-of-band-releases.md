---
title: .NET Framework und Out-of-Band-Releases
ms.date: 10/10/2018
ms.assetid: 721f10fa-3189-4124-a00d-56ddabd889b3
ms.openlocfilehash: 058bc1a5180060d3c3c6ba4ead1f074a14336b53
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181566"
---
# <a name="net-framework-and-out-of-band-releases"></a>.NET Framework und Out-of-Band-Releases

.NET Framework hat sich entwickelt, um verschiedene Plattformen wie UWP-Apps und herkömmliche Desktop- und Web-Apps aufzunehmen und die Wiederverwendung von Code zu maximieren. Neben regelmäßigen .NET Framework-Versionen werden neue Funktionen out-of-band (OOB) veröffentlicht, um die plattformübergreifende Entwicklung zu verbessern oder neue Funktionalität einzuführen.

## <a name="advantages-of-oob-releases"></a>Vorteile von OOB-Versionen

Durch die „out-of-band“-Herausgabe neuer Komponenten oder Updates für Komponenten kann Microsoft Updates für .NET Framework häufiger bereitstellen. Außerdem kann somit Kundenfeedback schneller eingeholt und darauf reagiert werden.

Wenn Sie eine OOB-Funktion in Ihrer App verwenden, müssen Benutzer zum Ausführen der App nicht die neueste Version von .NET Framework installieren, da die OOB-Assemblys mit dem App-Paket bereitgestellt werden.

## <a name="how-oob-packages-are-distributed"></a>Wie OOB-Pakete verteilt werden

OOB-Releases für Kernkomponenten der Common Language Runtime (CLR) werden über [NuGet](https://www.nuget.org/) verteilt. Dabei handelt es sich um den Paket-Manager für .NET. Mit NuGet können Sie Bibliotheken auf einfache Weise in Visual Studio durchsuchen und Ihren .NET Framework-Projekten hinzufügen. Der NuGet-Paket-Manager ist bei allen Editionen von Visual Studio ab Visual Studio 2012 enthalten. Suchen Sie nach **NuGet-Paket-Manager** im Menü **Tools** in Visual Studio. Wenn er nicht installiert ist, folgen Sie den Anweisungen unter [Installieren von NuGet](/nuget/install-nuget-client-tools). Weitere Informationen zu NuGet finden Sie in den [NuGet-Dokumentationen](/nuget).

## <a name="use-a-nuget-oob-package"></a>Verwenden eines OOB-Pakets von NuGet

Wenn der NuGet-Paket-Manager installiert ist, können Sie die NuGet-Pakete mithilfe des Projektmappen-Explorers in Visual Studio durchsuchen und Verweise auf sie hinzufügen:

1. Öffnen Sie das Kontextmenü für Ihr Projekt in Visual Studio, und wählen Sie dann **NuGet-Pakete verwalten** aus. (Diese Option ist auch im Menü **Projekt** verfügbar.)

2. Wählen Sie im linken Bereich **Online** aus.

3. Wenn Sie Vorabversionspakete verwenden möchten, wählen Sie im Dropdown-Listenfeld im mittleren Bereich **Vorabversion einschließen** anstelle von **Nur stabil** aus.

4. Verwenden Sie im rechten Bereich das Feld **Suchen**, um das gewünschte Paket zu suchen. Einige Microsoft-Pakete sind mit dem Microsoft .NET Framework-Logo gekennzeichnet, und für alle ist Microsoft als Herausgeber angegeben.

![Der NuGet-Paket-Manager.](./media/the-net-framework-and-out-of-band-releases/nuget-package-manager-dialog.png)

Wie bereits erwähnt, werden die OOB-Assemblys ins App-Paket eingeschlossen, wenn Sie eine App bereitstellen, die ein OOB-Paket verwendet.

## <a name="types-of-oob-releases"></a>Typen von OOB-Versionen

In der Regel umfasst ein OOB-Paket mindestens eine Vorabversion und eine stabile Version. Die Lizenz, die einer Vorabversion beiliegt, gestattet in der Regel keine Weiterverteilung. Sie können damit jedoch ein Paket testen und Feedback abgeben. Feedback ist in alle am Paket vorgenommenen Updates integriert. Eine endgültige Version wird als stabiles Paket mit NuGet verteilt und enthält eine Lizenz, mit der Sie das NuGet-Paket mit Ihrer App weiter verteilen können. Stabile Pakete werden von Microsoft unterstützt. Microsoft bietet IntelliSense-Unterstützung sowie andere Arten der Dokumentation, wie z. B. Blogbeiträge und Forumantworten, für alle Pakete. Darüber hinaus steht Quellcode bei einigen, jedoch nicht bei allen Paketen zur Verfügung. Sie können den [.NET Framework-Blog](https://devblogs.microsoft.com/dotnet/) abonnieren, um Ankündigungen zu neuen und aktualisierten Paketen zu erhalten.

Wählen Sie **Vorabversion einschließen** im NuGet-Paket-Manager aus, um nach Vorabversionen und stabilen Paketen zu suchen.

## <a name="see-also"></a>Siehe auch

- [Erste Schritte](index.md)
