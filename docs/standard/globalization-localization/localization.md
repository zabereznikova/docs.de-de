---
title: Lokalisierung
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- culture, localization
- application development [.NET Framework], localization
- globalization [.NET Framework], localization
- code blocks
- international applications [.NET Framework], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET Framework], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
ms.openlocfilehash: 68e877088c5c3d17b368561b563b4cb17d004e75
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84278024"
---
# <a name="localization"></a>Lokalisierung

Unter Lokalisierung versteht man den Vorgang, bei dem Anwendungsressourcen in lokalisierte Versionen für sämtliche von der Anwendung unterstützten Kulturen übersetzt werden. Sie sollten erst nach Durchführung des Schritts [Überprüfung der Lokalisierbarkeit](localizability-review.md) mit dem Lokalisierungsschritt fortfahren, um sicherzustellen, dass die globalisierte Anwendung für die Lokalisierung bereit ist.

Eine zur Lokalisierung bereitstehende Anwendung wird in zwei grundlegende Blöcke unterteilt: einen Block, der alle Elemente der Benutzeroberfläche enthält, und einen Block mit ausführbarem Code. Der Benutzeroberflächenblock enthält nur lokalisierbare Benutzeroberflächenelemente für die neutrale Kultur, z.B. Zeichenfolgen, Fehlermeldungen, Dialogfelder, Menüs und eingebettete Objektressourcen. Der Codeblock enthält nur den Anwendungscode, der von allen unterstützten Kulturen verwendet werden soll. Die Common Language Runtime unterstützt ein Satellitenassembly-Ressourcenmodell, das ausführbaren Code einer Anwendung von den jeweiligen Ressourcen trennt. Weitere Informationen zur Implementierung dieses Modells finden Sie unter [Ressourcen in .NET-Apps](../../framework/resources/index.md).

Fügen Sie für jede lokalisierte Version Ihrer Anwendung eine neue Satellitenassembly hinzu, die den lokalisierten Benutzeroberflächenblock enthält, der in der entsprechenden Sprache für die Zielkultur übersetzt wurde. Der Codeblock aller Kulturen sollte identisch sein. Durch die Kombination einer lokalisierten Version des Benutzeroberflächenblocks mit dem Codeblock erzeugen Sie eine lokalisierte Version Ihrer Anwendung.

Das Windows Software Development Kit (SDK) stellt den Windows Forms-Ressourcen-Editor (Winres.exe) bereit, mit dem Sie im Handumdrehen Windows Forms für Zielkulturen lokalisieren können. Informationen zur Verwendung dieses Tools finden Sie unter [Winres.exe (Windows Forms-Ressourcen-Editor)](../../framework/tools/winres-exe-windows-forms-resource-editor.md).

## <a name="see-also"></a>Siehe auch

- [Globalisierung und Lokalisierung](index.md)
- [Überprüfung der Lokalisierbarkeit](localizability-review.md)
- [Globalisierung](globalization.md)
- [Ressourcen in Desktop-Apps](../../framework/resources/index.md)
